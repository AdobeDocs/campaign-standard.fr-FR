---
title: API externe
description: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: externalAPI,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3bd2fdb56fc94cef4e9c21466a33cdad7ac825d2
workflow-type: tm+mt
source-wordcount: '1758'
ht-degree: 94%

---


# API externe {#external-api}

## Description {#description}

![](assets/wf_externalAPI.png)

L’activité **[!UICONTROL API externe]** récupère des données dans le workflow d’un **système externe** via un appel **API HTTP**.

Les points d’entrée de système externes peuvent être des point d’entrée API publics, des systèmes de gestion des clients ou des instances d’application sans serveur (ex. : [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html)), pour ne citer que quelques catégories.

>[!NOTE]
>
>Pour des raisons de sécurité, l’utilisation de JSSP n’est pas prise en charge dans Campaign Standard. Si vous devez exécuter du code, vous pouvez appeler une instance Runtime Adobe I/O via l’activité API externe.

Les principales caractéristiques de cette activité sont les suivantes :

* Capacité de transmettre des données dans un format JSON à un point d’entrée API REST tiers
* Capacité de recevoir une réponse JSON, de la mapper sur des tables de sortie et de la transmettre en aval à d’autres activités de workflow
* Gestion des échecs avec une transition spécifique sortante

### Transition de la version bêta à la version GA {#from-beta-to-ga}

Avec Campaign Standard version 20.3, la fonctionnalité API externe est passée de la version bêta à la version GA (General Availability).

>[!CAUTION]
>
>Par conséquent, si vous utilisiez les activités API externe bêta, vous devez les remplacer par des activités API externe GA dans tous les workflows.  Les worfklows qui utilisent la version bêta de l’API externe cesseront de fonctionner à partir de la version 20.3.

Lorsque vous remplacez les activité API externe, ajoutez la nouvelle activité API externe au workflow, copiez manuellement les détails de la configuration, puis supprimez l&#39;ancienne activité.

>[!NOTE]
>
>Vous ne pourrez pas copier sur les valeurs de l’en-tête, car elles sont masquées dans l’activité.

Ensuite, reconfigurez d’autres activités dans le workflow qui pointent vers et/ou utilisent les données de l’activité API externe bêta pour pointer vers et/ou utiliser les données de la nouvelle activité API externe à la place. Exemples d’activités : diffusion email (champs de personnalisation), activité d’enrichissement, etc.

### Limitations et garde-fous {#guardrails}

Les garde-fous suivants s&#39;appliquent à cette activité :

* Taille limite de 50 Mo de données de réponse http (5 Mo recommandés)
* Le timeout des demandes est de 10 minutes
* Les redirections HTTP ne sont pas autorisées
* Les URL autres que HTTPS sont rejetées
* L’en-tête de demande &quot;Accept: application/json&quot; et l’en-tête de réponse &quot;Content-Type: application/json&quot; sont autorisés

>[!NOTE]
>
>A compter de la version Campaign 20.4, la limite de taille des données de réponse http et les garde-fous de délai d’expiration de réponse seront abaissés à 5 Mo et 1 minute, respectivement.  Bien que cette modification n&#39;affecte que les nouvelles activités d&#39;API externe, il est fortement recommandé que les mises en oeuvre actuelles de l&#39;activité d&#39;API externe s&#39;alignent sur ces nouvelles garde-fous pour suivre les meilleures pratiques.

Des garde-fous spécifiques ont été mis en place pour le JSON :

* **Profondeur JSON maximale** : limite la profondeur maximale d’un code JSON imbriqué personnalisé qui peut être traité à 10 niveaux.
* **Longueur de clé JSON maximale** : limite la longueur maximale de la clé interne générée à 255. Cette clé est associée à l’ID de colonne.
* **Nombre maximum de clés JSON autorisées** :  limite à 150 le nombre total maximum de noms de propriétés JSON dupliqués, qui sont utilisés comme ID de colonne.

L’activité n’est pas prise en charge par la structure JSON en tant que :

* Combinaison d’un objet de tableau avec d’autres éléments non issus de tableaux
* L’objet de tableau JSON est imbriqué dans un ou plusieurs objets de tableau intermédiaire.

>[!CAUTION]
>
>L’activité API externe est destinée à la récupération des données à l’échelle de la campagne (dernier ensemble d’offres, derniers scores, etc.), et non à la récupération d’informations spécifiques pour chaque profil, ce qui peut entraîner le transfert de grandes quantités de données. Si le cas pratique requiert cela, la recommandation consiste à utiliser l’activité [Transfert de fichier](../../automating/using/transfer-file.md).

## Configuration {#configuration}

Placez une activité **[!UICONTROL API externe]** dans votre workflow et ouvrez l’activité pour commencer la configuration.

### Mapping entrant

Le mapping entrant est un tableau temporaire généré par une activité entrante précédente qui sera affichée et envoyée sous forme de code JSON dans l’interface utilisateur.
Selon ce tableau temporaire, l’utilisateur peut apporter des modifications aux données entrantes.

![](assets/externalAPI-inbound.png)

La liste déroulante **Ressource entrante** permet de sélectionner l’activité de requête qui crée le tableau temporaire.

La case à cocher **Ajouter un paramètre de comptage** ajoutera une valeur numérique pour chaque ligne provenant du tableau temporaire. Cette case à cocher est disponible uniquement si l’activité entrante génère un tableau temporaire.

La section **Colonnes entrantes** permet à l’utilisateur d’ajouter n’importe quel champ du tableau de transition entrante. Les colonnes sélectionnées sont les clés de l’objet de données. L’objet de données du code JSON est une liste de tableaux contenant les données des colonnes sélectionnées de chaque ligne du tableau de transition entrante.

La zone de texte **Personnaliser le paramètre** permet d’ajouter un code JSON valide avec des données additionnelles requises par l’API externe. Ces données additionnelles seront ajoutées à l’objet params du code JSON généré.

### Mapping sortant

Cet onglet permet de définir l’exemple de **structure JSON** renvoyé par l’appel API.

![](assets/externalAPI-outbound.png)

L’analyseur JSON est conçu pour s’adapter aux types de motifs de structure JSON standard, à quelques exceptions près. Voici un exemple de modèle standard :`{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

L’exemple de définition JSON doit présenter les **caractéristiques suivantes** :

* Les **éléments de tableau** doivent contenir des propriétés de premier niveau (les niveaux plus profonds ne sont pas pris en charge).
   Les **noms de propriété** deviennent des noms de colonne pour le schéma de sortie du tableau temporaire de sortie.
* Les **éléments JSON** à capturer doivent être imbriqués à 10 niveaux ou moins dans la réponse JSON.
* La définition du **nom de colonne** repose sur le premier élément du tableau &quot;data&quot;.
La définition des colonnes (ajout/suppression) et la valeur de type de la propriété peuvent être éditées dans l’onglet **Définition des colonnes**.

Comportement de la **case à cocher Aplatir** :

La case à cocher Aplatir (par défaut : non cochée) est fournie pour indiquer si le fichier JSON doit être aplati ou non sur une carte clé/valeur.

* Lorsque la **case à cocher est désactivée** (non cochée), l’exemple JSON est analysé pour la recherche d’un objet de tableau. L’utilisateur devra fournir une version abrégée du format JSON d’exemple de réponse de l’API afin qu’Adobe Campaign puisse déterminer exactement le tableau que l’utilisateur souhaite utiliser. Au moment de la création du workflow, le chemin d’accès à l’objet de tableau imbriqué sera déterminé et enregistré, de sorte qu’il puisse être utilisé au moment de l’exécution pour accéder à cet objet de tableau à partir du corps de réponse JSON reçu de l’appel API.

* Lorsque la **case à cocher est activée** (cochée), l’exemple JSON est aplati et toutes les propriétés spécifiées dans l’exemple JSON fourni sont utilisées pour créer des colonnes du tableau temporaire de sortie et affichées dans l’onglet Définitions des colonnes. Notez que s’il existe un objet de tableau dans l’exemple JSON, tous les éléments de ces objets de tableau seront également aplatis.


Si l’**analyse est validée**, un message s’affiche. Il vous invite à personnaliser le mappage des données dans l’onglet « Définition des colonnes ». Dans d’autres cas, un message d’erreur s’affiche.

### Exécution

Cet onglet vous permet de définir le **point d’entrée HTTPS** qui enverra des données à ACS. Au besoin, vous pouvez saisir des informations d’authentification dans les champs ci-dessous.
![](assets/externalAPI-execution.png)

### Propriétés

Cet onglet permet de contrôler les **propriétés générales** de l’activité API externe, comme le libellé affiché dans l’interface utilisateur. L’identifiant interne n’est pas personnalisable.

![](assets/externalAPI-properties.png)

### Définition de colonne

>[!NOTE]
>
>Cet onglet s’affiche lorsque le **format des données de réponse** est complété et validé dans l’onglet Mapping sortant.

L’onglet **Définition des colonnes** vous permet de définir précisément la structure des données de chaque colonne pour importer des données qui ne contiennent pas d’erreur et les faire correspondre aux types pré-existants de la base Adobe Campaign pour des opérations ultérieures.

![](assets/externalAPI-column.png)

Vous pouvez par exemple modifier le libellé d’une colonne, sélectionner son type (chaîne, nombre entier, date, etc.) ou encore définir le traitement des erreurs.

Pour plus d’informations, consultez la section [Chargement de fichier](../../automating/using/load-file.md).

### Transition

Cet onglet permet d’activer la **transition sortante** et son libellé. Cette transition spécifique est utile si le **délai d’expiration** ou la payload dépasse la **limite de taille des données**.

![](assets/externalAPI-transition.png)

### Options d’exécution

Cet onglet est disponible dans la plupart des activités de workflow. Pour plus d’informations, consultez la section [Propriétés d’une activité](../../automating/using/activity-properties.md).

![](assets/externalAPI-options.png)

## Résolution des problèmes

Deux types de messages de log ont été ajoutés à cette nouvelle activité de workflow : informations et erreurs. Ils peuvent vous aider à résoudre les problèmes potentiels.

### Informations

Ces messages de log sont utilisés pour consigner des informations sur les points de contrôle utiles lors de l’exécution de l’activité de workflow. En particulier, les messages de log suivants sont utilisés pour consigner la première tentative et une tentative de reprise (et la raison de l’échec de la première tentative) d’accès à l’API.

<table> 
 <thead> 
  <tr> 
   <th> Format du message<br /> </th> 
   <th> Exemple<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Appel de l’URL d’API ’%s’.</td> 
   <td> <p>Appel de l’URL d’API ’https://example.com/api/v1/web-coupon?count=2’.</p></td> 
  </tr> 
  <tr> 
   <td> Reprise de l’URL d’API ’%s’, la tentative précédente a échoué (’%s’).</td> 
   <td> <p>Reprise de l’URL d’API https://example.com/api/v1/web-coupon?count=2’, la tentative précédente a échoué (’HTTP - 401’).</p></td>
  </tr> 
  <tr> 
   <td> Transfert du contenu depuis ’%s’(%s / %s).</td> 
   <td> <p>Transfert du contenu depuis ’https://example.com/api/v1/web-coupon?count=2’ (1234/1234).</p></td> 
  </tr>
 </tbody> 
</table>

### Erreurs

Ces messages de log sont utilisés pour consigner des informations sur des conditions d’erreur inattendues peuvent entraîner l’échec de l’activité de workflow.

<table> 
 <thead> 
  <tr> 
   <th> Code - Format du message<br /> </th> 
   <th> Exemple<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - Le corps de la demande d’API a dépassé la limite (limite : ’%d’).</td> 
   <td> <p>Le corps de la demande d’API a dépassé la limite (limite : ’5242880’).</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 - La réponse de l’API a dépassé la limite (limite : ’%d’).</td> 
   <td> <p>La réponse de l’API a dépassé la limite (limite : ’5242880’).</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - L’URL de l’API n’a pas pu être analysée (erreur : ’%d’).</td> 
   <td> <p>L’URL de l’API n’a pas pu être analysée (erreur : -2010’).</p>
   <p> Remarque : cette erreur est consignée lorsque l’URL d’API échoue aux règles de validation.</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - L’hôte d’URL de l’API ne doit pas être ’localhost’ ni un littéral d’adresse IP (hôte d’URL : ’%s’).</td> 
   <td> <p>L’hôte d’URL de l’API ne doit pas être ’localhost’ ni un littéral d’adresse IP (hôte d’URL : ’localhost’).</p>
    <p>L’hôte d’URL de l’API ne doit pas être ’localhost’ ni un littéral d’adresse IP (hôte d’URL : ’192.168.0.5’).</p>
    <p>L’hôte d’URL de l’API ne doit pas être ’localhost’ ni un littéral d’adresse IP (hôte d’URL : ’[2001]’).</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - L’URL d’API doit être une URL (https) sécurisée (URL demandée : ’%s’).</td> 
   <td> <p>L’URL d’API doit être une URL (https) sécurisée (URL demandée : ’https://example.com/api/v1/web-coupon?count=2’).</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 - Echec de la création du JSON du corps de la demande. Erreur lors de l’ajout de ’%s’.</td> 
   <td> <p>Echec de la création du JSON du corps de la demande. Erreur lors de l’ajout de ’params’.</p>
    <p>Echec de la création du JSON du corps de la demande. Erreur lors de l’ajout de ’data’.</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - La clé de l’en-tête HTTP est incorrecte (clé de l’en-tête : ’%s’).</td> 
   <td> <p>La clé de l’en-tête HTTP est incorrecte (clé de l’en-tête : ’%s’).</p>
   <p> Remarque : cette erreur est consignée lorsque la clé d’en-tête personnalisée échoue à la validation selon les <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a>.</p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - La clé de l’en-tête HTTP n’est pas autorisée (clé de l’en-tête : ’%s’).</td> 
   <td> <p>La clé de l’en-tête HTTP n’est pas autorisée (clé de l’en-tête : ’Accept’).</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - La valeur de l’en-tête HTTP est incorrecte (valeur de l’en-tête : ’%s’).</td> 
   <td> <p>La valeur de l’en-tête HTTP est incorrecte (valeur de l’en-tête : ’%s’). </p>
    <p>Remarque : cette erreur est consignée lorsque la valeur d’en-tête personnalisée échoue à la validation selon les <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a>.</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - La propriété ’%s’ de la payload JSON est incorrecte.</td> 
   <td> <p>La propriété ’blah’ de la payload JSON est incorrecte.</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - Elément JSON incorrect ou format inacceptable.</td> 
   <td> <p>Elément JSON incorrect ou format inacceptable.</p>
   <p>Remarque : ce message s’applique uniquement à l’analyse du corps de la réponse de l’API externe. Il est consigné lors de la tentative de validation de la conformité du corps de la réponse au format JSON mandaté par cette activité.</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 - Echec de l’activité (motif : ’%s’).</td> 
   <td> <p>Lorsque l’activité échoue en raison de la réponse d’erreur HTTP 401 - Echec de l’activité (motif : ’HTTP - 401’)</p>
        <p>Lorsque l’activité échoue en raison d’un appel interne en échec - Echec de l’activité (motif : ’iRc - -Nn’).</p>
        <p>Lorsque l’activité échoue en raison d’un en-tête Content-Type non valide. - Echec de l’activité (motif : ’Content-Type - application/html’).</p></td> 
  </tr>
 </tbody> 
</table>

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
