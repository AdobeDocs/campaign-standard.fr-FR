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
source-git-commit: 6f7f4f3d81f4e6a540b3317f283c1e2311ccc65a

---


# API externe {#external-api}

## Description {#description}

![](assets/wf_externalAPI.png)

L&#39;activité **[!UICONTROL API externe]**récupère des données dans le workflow d&#39;un** système externe **via un appel** API REST **.

Les points d&#39;entrée REST peuvent être un système de gestion client, une instance [Runtime Adobe I/O](https://www.adobe.io/apis/experienceplatform/runtime.html) ou un point d&#39;entrée REST Experience Cloud (Data Platform, Target, Analytics, Campaign, etc.).

>[!NOTE]
>
>Pour des raisons de sécurité, l&#39;utilisation de JSSP n&#39;est pas prise en charge dans Campaign Standard. Si vous devez exécuter du code, vous pouvez appeler une instance Runtime Adobe I/O via l&#39;activité API externe.

>[!IMPORTANT]
>
>Cette fonctionnalité est actuellement en version bêta. Vous devez accepter les termes du contrat d&#39;utilisation avant de commencer à utiliser l&#39;activité API externe. Notez que cette fonctionnalité bêta n’ayant pas encore été commercialisée par Adobe, elle n’est pas prise en charge par le service à la clientèle d’Adobe. Elle peut contenir des erreurs et ne pas fonctionner, ainsi que d’autres fonctionnalités publiées.

Les principales caractéristiques de cette activité sont les suivantes :

* Capacité de transmettre des données dans un format JSON à un point d&#39;entrée API REST tiers
* Capacité de recevoir une réponse JSON, de la mapper sur des tables de sortie et de la transmettre en aval à d&#39;autres activités de workflow
* Gestion des échecs avec une transition spécifique sortante

Les protections suivantes ont été mises en place pour cette activité :

* Limite de 5 Mo pour la taille des données de réponse http
* Délai d&#39;attente de la demande de 60 secondes
* Les redirections HTTP ne sont pas autorisées
* Les URL autres que HTTPS sont rejetées
* L&#39;en-tête de demande &quot;Accept: application/json&quot; et l&#39;en-tête de réponse &quot;Content-Type: application/json&quot; sont autorisés

>[!CAUTION]
>
>Notez que l&#39;activité est destinée à récupérer des données à l&#39;échelle de la campagne (dernier ensemble d&#39;offres, derniers scores, etc.) et non des informations spécifiques pour chaque profil, car cela peut entraîner le transfert de grandes quantités de données. Si le cas pratique requiert cela, la recommandation consiste à utiliser l&#39;activité [Transfert de fichier](../../automating/using/transfer-file.md).

## Configuration {#configuration}

Placez une activité **[!UICONTROL API externe]**dans votre workflow et ouvrez l&#39;activité pour commencer la configuration.

### Mapping entrant

Le mapping entrant est un tableau temporaire généré par une activité entrante précédente qui sera affichée et envoyée sous forme de code JSON dans l&#39;interface utilisateur.
Selon ce tableau temporaire, l&#39;utilisateur peut apporter des modifications aux données entrantes.

![](assets/externalAPI-inbound.png)

La liste déroulante **Ressource entrante** permet de sélectionner l&#39;activité de requête qui crée le tableau temporaire.

La case à cocher **Ajouter un paramètre de comptage** est une valeur numérique pour chaque ligne provenant du tableau temporaire. Cette case à cocher est disponible uniquement si l&#39;activité entrante génère un tableau temporaire.

La section **Colonnes entrantes** permet à l&#39;utilisateur d&#39;ajouter n&#39;importe quel champ du tableau de transition entrante. Les colonnes sélectionnées sont les clés de l&#39;objet de données. L&#39;objet de données du code JSON est une liste de tableaux contenant les données des colonnes sélectionnées de chaque ligne du tableau de transition entrante.

La zone de texte **Personnaliser le paramètre** permet d&#39;ajouter un code JSON valide avec des données additionnelles requises par l&#39;API externe. Ces données additionnelles seront ajoutées à l&#39;objet params du code JSON généré.

### Mapping sortant

Cet onglet permet de définir l&#39;exemple de **structure JSON** renvoyé par l&#39;appel API.

![](assets/externalAPI-outbound.png)

Le modèle de structure JSON est le suivant : `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

L&#39;exemple de définition JSON doit présenter les **caractéristiques suivantes** :

* **data** est un nom de propriété obligatoire dans le code JSON. Le contenu de &quot;data&quot; est un tableau JSON.
* Les **éléments de tableau** doivent contenir des propriétés de premier niveau (les niveaux plus profonds ne sont pas pris en charge).
   Les **noms de propriété** deviennent des noms de colonne pour le schéma de sortie du tableau temporaire de sortie.
* La définition du **nom de colonne** repose sur le premier élément du tableau &quot;data&quot;.
La définition des colonnes (ajout/suppression) et la valeur de type de la propriété peuvent être éditées dans l&#39;onglet **Définition des colonnes**.

Si l&#39;**analyse est validée**, un message s&#39;affiche. Il vous invite à personnaliser le mappage des données dans l&#39;onglet &quot;Définition des colonnes&quot;. Dans d&#39;autres cas, un message d&#39;erreur s&#39;affiche.

### Exécution

Cet onglet vous permet de définir le **point d&#39;entrée HTTPS** qui enverra des données à ACS. Au besoin, vous pouvez saisir des informations d&#39;authentification dans les champs ci-dessous.
![](assets/externalAPI-execution.png)

### Propriétés

Cet onglet permet de contrôler les **propriétés générales** de l&#39;activité API externe, comme le libellé affiché dans l&#39;interface utilisateur. L&#39;identifiant interne n&#39;est pas personnalisable.

![](assets/externalAPI-properties.png)

### Définition de colonne

>[!NOTE]
>
>Cet onglet s&#39;affiche lorsque le **format des données de réponse** est complété et validé dans l&#39;onglet Mapping sortant.

L&#39;onglet **Définition des colonnes** vous permet de définir précisément la structure des données de chaque colonne pour importer des données qui ne contiennent pas d&#39;erreur et les faire correspondre aux types pré-existants de la base Adobe Campaign pour des opérations ultérieures.

![](assets/externalAPI-column.png)

Vous pouvez par exemple modifier le libellé d&#39;une colonne, sélectionner son type (chaîne, nombre entier, date, etc.) ou encore définir le traitement des erreurs.

Pour plus d&#39;informations, consultez la section [Chargement de fichier](../../automating/using/load-file.md).

### Transition

Cet onglet permet d&#39;activer la **transition sortante** et son libellé. Cette transition spécifique est utile si le **délai d&#39;expiration** ou la payload dépasse la **limite de taille des données**.

![](assets/externalAPI-transition.png)

### Options d&#39;exécution

Cet onglet est disponible dans la plupart des activités de workflow. Pour plus d&#39;informations, consultez la section [Propriétés d&#39;une activité](../../automating/using/executing-a-workflow.md#activity-properties).

![](assets/externalAPI-options.png)

## Résolution des problèmes

Deux types de messages de log ont été ajoutés à cette nouvelle activité de workflow : informations et erreurs. Ils peuvent vous aider à résoudre les problèmes potentiels.

### Informations

Ces messages de log sont utilisés pour consigner des informations sur les points de contrôle utiles lors de l&#39;exécution de l&#39;activité de workflow. En particulier, les messages de log suivants sont utilisés pour consigner la première tentative et une tentative de reprise (et la raison de l&#39;échec de la première tentative) d&#39;accès à l&#39;API.

<table> 
 <thead> 
  <tr> 
   <th> Format du message<br /> </th> 
   <th> Exemple<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Appel de l'URL d'API '%s'.</td> 
   <td> <p>Appel de l'URL d'API 'https://example.com/api/v1/web-coupon?count=2'.</p></td> 
  </tr> 
  <tr> 
   <td> Reprise de l'URL d'API '%s', la tentative précédente a échoué ('%s').</td> 
   <td> <p>Reprise de l'URL d'API https://example.com/api/v1/web-coupon?count=2', la tentative précédente a échoué ('HTTP - 401').</p></td>
  </tr> 
  <tr> 
   <td> Transfert du contenu depuis '%s'(%s / %s).</td> 
   <td> <p>Transfert du contenu depuis 'https://example.com/api/v1/web-coupon?count=2' (1234/1234).</p></td> 
  </tr>
 </tbody> 
</table>

### Erreurs

Ces messages de log sont utilisés pour consigner des informations sur des conditions d&#39;erreur inattendues peuvent entraîner l&#39;échec de l&#39;activité de workflow.

<table> 
 <thead> 
  <tr> 
   <th> Code - Format du message<br /> </th> 
   <th> Exemple<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - Le corps de la demande d'API a dépassé la limite (limite : '%d').</td> 
   <td> <p>Le corps de la demande d'API a dépassé la limite (limite : '5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 - La réponse de l'API a dépassé la limite (limite : '%d').</td> 
   <td> <p>La réponse de l'API a dépassé la limite (limite : '5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - L'URL de l'API n'a pas pu être analysée (erreur : '%d').</td> 
   <td> <p>L'URL de l'API n'a pas pu être analysée (erreur : -2010').</p>
   <p> Remarque : cette erreur est consignée lorsque l'URL d'API échoue aux règles de validation.</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - L'hôte d'URL de l'API ne doit pas être 'localhost' ni un littéral d'adresse IP (hôte d'URL : '%s').</td> 
   <td> <p>L'hôte d'URL de l'API ne doit pas être 'localhost' ni un littéral d'adresse IP (hôte d'URL : 'localhost').</p>
    <p>L'hôte d'URL de l'API ne doit pas être 'localhost' ni un littéral d'adresse IP (hôte d'URL : '192.168.0.5').</p>
    <p>L'hôte d'URL de l'API ne doit pas être 'localhost' ni un littéral d'adresse IP (hôte d'URL : '[2001]').</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - L'URL d'API doit être une URL (https) sécurisée (URL demandée : '%s').</td> 
   <td> <p>L'URL d'API doit être une URL (https) sécurisée (URL demandée : 'https://example.com/api/v1/web-coupon?count=2').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 - Echec de la création du JSON du corps de la demande. Erreur lors de l'ajout de '%s'.</td> 
   <td> <p>Echec de la création du JSON du corps de la demande. Erreur lors de l'ajout de 'params'.</p>
    <p>Echec de la création du JSON du corps de la demande. Erreur lors de l'ajout de 'data'.</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - La clé de l'en-tête HTTP est incorrecte (clé de l'en-tête : '%s').</td> 
   <td> <p>La clé de l'en-tête HTTP est incorrecte (clé de l'en-tête : '%s').</p>
   <p> Remarque : cette erreur est consignée lorsque la clé d'en-tête personnalisée échoue à la validation selon les <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a>.</p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - La clé de l'en-tête HTTP n'est pas autorisée (clé de l'en-tête : '%s').</td> 
   <td> <p>La clé de l'en-tête HTTP n'est pas autorisée (clé de l'en-tête : 'Accept').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - La valeur de l'en-tête HTTP est incorrecte (valeur de l'en-tête : '%s').</td> 
   <td> <p>La valeur de l'en-tête HTTP est incorrecte (valeur de l'en-tête : '%s'). </p>
    <p>Remarque : cette erreur est consignée lorsque la valeur d'en-tête personnalisée échoue à la validation selon les <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a>.</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - La propriété '%s' de la payload JSON est incorrecte.</td> 
   <td> <p>La propriété 'blah' de la payload JSON est incorrecte.</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - Elément JSON incorrect ou format inacceptable.</td> 
   <td> <p>Elément JSON incorrect ou format inacceptable.</p>
   <p>Remarque : ce message s'applique uniquement à l'analyse du corps de la réponse de l'API externe. Il est consigné lors de la tentative de validation de la conformité du corps de la réponse au format JSON mandaté par cette activité.</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 - Echec de l'activité (motif : '%s').</td> 
   <td> <p>Lorsque l'activité échoue en raison de la réponse d'erreur HTTP 401 - Echec de l'activité (motif : 'HTTP - 401')</p>
        <p>Lorsque l'activité échoue en raison d'un appel interne en échec - Echec de l'activité (motif : 'iRc - -Nn').</p>
        <p>Lorsque l'activité échoue en raison d'un en-tête Content-Type non valide. - Echec de l'activité (motif : 'Content-Type - application/html').</p></td> 
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
