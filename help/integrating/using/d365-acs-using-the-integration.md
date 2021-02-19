---
title: Utilisation de l’intégration de Microsoft Dynamics 365
description: Découvrez comment utiliser l’intégration de Microsoft Dynamics 365 avec Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 100%

---


# Utilisation de l’intégration de Microsoft Dynamics 365

Plusieurs flux de données sont effectuées par l&#39;intégration d&#39;Adobe Campaign Standard avec Microsoft Dynamics 365. Ces flux sont présentés dans [cette page](../../integrating/using/d365-acs-self-service-app-workflows.md).

Vous trouverez plus de détails sur les flux de données dans ce document de la section [Flux de données](#data-flows).

## Expérience utilisateur Adobe Campaign Standard

Lorsqu’un contact est créé, modifié, ou supprimé (si la suppression est activée) dans Microsoft Dynamics 365, il est envoyé à Campaign Standard. Ces contacts seront visibles dans l’écran Profils de Campaign et peuvent être ciblés dans les campagnes marketing. Voir l’écran Profils ci-dessous.

![](assets/MSdynamicsACS-usage1.png)

Lorsqu’un attribut d&#39;opt-out est modifié dans Campaign, la modification est prise en compte dans Dynamics 365 si vous avez sélectionné la configuration d&#39;opt-out **Unidirectionnelle (Campaign vers Microsoft Dynamics 365)** ou **Bidirectionnelle**, et si cet attribut spécifique est correctement mappé.

## Expérience utilisateur Microsoft Dynamics 365

Pour la sortie, les événements de marketing email suivants sont envoyés de Campaign vers Dynamics 365 et affichés dans la vue de chronologie Microsoft Dynamics 365 sous forme d’activités personnalisées :

*  Envoi d’email Adobe Campaign

*  Ouverture d’email Adobe Campaign

*  Clic sur une URL d’email Adobe Campaign

*  Email bounce Adobe Campaign

Pour voir la chronologie d’un contact, accédez à votre liste de contacts en cliquant sur Concentrateur des ventes dans le menu déroulant Dynamics 365. Cliquez ensuite sur Contacts dans la barre de menu de gauche et sélectionnez un contact.

>[!NOTE]
>
>L’application **Adobe Campaign Microsoft pour Dynamics 365** dans AppSource devra être installée dans votre instance Microsoft Dynamics 365 afin d’afficher ces événements. [En savoir plus](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Vous trouverez ci-dessous un une capture de l’écran Contact pour « Utilisateur Dynamics ». Dans la vue de la chronologie, vous remarquerez que l’utilisateur Dynamics a reçu un email associé au nom Campaign « 2019LoyaltyCamp » et au nom de diffusion « DM190 ». L’utilisateur Dynamics a ouvert l’email et a également cliqué sur une URL contenue dans celui-ci. Ces deux actions ont créé des événements également présentés ci-dessous. Si vous regardez dans le coin droit, vous verrez la carte de l’assistant de relations (AR) ; il contient actuellement une tâche de suivi de l’URL sur laquelle l’utilisateur a cliqué.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Reportez au gros plan ci-dessous de la vue de chronologie pour l’utilisateur Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Vous trouverez ci-dessous un gros plan de la vignette de l’assistant de relations (AR). L’application AppSource contient un workflow qui recherche un événement de clic sur l’URL de l’email Adobe. Lorsque cet événement se produit, il crée une tâche et définit une date d’échéance. Cela permet à la tâche de s’afficher dans la vignette de l’AR, ce qui lui donne une visibilité supplémentaire. Il existe un workflow similaire pour les événements Email bounce d’Adobe, qui ajoute une tâche pour réconcilier l’adresse email non valide. Ces workflows peuvent être désactivés dans la solution.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Si vous cliquez sur l&#39;objet de l’événement d’envoi, vous verrez un formulaire similaire à celui ci-dessous. Les formulaires pour les événements d’ouverture et de rebond sont similaires.

![](assets/do-not-localize/mirror_page_url_send.png)

Le formulaire pour les événements de clic sur l’URL d’un email ajoute un attribut supplémentaire pour l’URL sur laquelle l’utilisateur a cliqué :

![](assets/do-not-localize/mirror_page_url_click.png)

Voici une liste des attributs et une description :

* **Objet** : objet de l’événement ; composé de l’identifiant de campagne et de l’identifiant de diffusion de la diffusion email

* **Propriétaire** : utilisateur de l’application créé lors des étapes après l&#39;approvisionnement

* **Concernant** : nom du contact

* **Nom de la campagne** : identifiant de la campagne dans Campaign Standard

* **Nom de la diffusion** : identifiant de la diffusion dans Campaign Standard

* **Date d’envoi/d’ouverture/de clic/de bounce** : date/heure de création de l’événement

* **URL de tracking** : URL sur laquelle l’utilisateur a cliqué

* **URL de page miroir** : URL vers la page miroir de l’email envoyé/ouvert/sur lequel l’utilisateur a cliqué/de bounce. La période d’expiration de la page miroir d’email peut être modifiée dans l’écran de configuration de l’activité de canal email Campaign correspondante. [En savoir plus](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>En ce qui concerne l&#39;opt-out, lorsqu’un attribut d&#39;opt-out est modifié dans Microsoft Dynamics 365, la modification est prise en compte dans Campaign si vous avez sélectionné la configuration d&#39;opt-out **Unidirectionnelle (Campaign vers Microsoft Dynamics 365)** ou **Bidirectionnelle**, et si cet attribut spécifique est correctement mappé.

## Flux de données {#data-flows}

### Entrée de contact et d’entité personnalisée

Les enregistrements nouveaux, mis à jour et supprimés (la suppression doit être activée) sont envoyés de la table des contacts Microsoft Dynamics 365 à la table de profils Campaign.

Les mappages de tables peuvent être configurés dans l&#39;interface utilisateur de l&#39;application d&#39;intégration pour mapper les attributs de table Microsoft Dynamics 365 sur les attributs de table Campaign. Les mappages des tables peuvent être modifiés pour ajouter ou supprimer des attributs, si nécessaire.

L’exécution initiale du flux de données est conçue pour transférer tous les enregistrements mappés, y compris ceux marqués comme « inactifs ». Par la suite, l’intégration ne traitera que les mises à jour incrémentielles. L’exception à cette règle est le cas où les données sont relues ou un filtre est configuré. Des règles de filtrage de base basées sur des attributs peuvent être configurées pour déterminer les enregistrements à synchroniser avec Campaign.

Les règles de remplacement de base peuvent être configurées dans l&#39;interface utilisateur de l&#39;application d&#39;intégration pour remplacer une valeur d’attribut par une autre (par exemple, « vert » pour « #00FF00 », « F » pour 1, etc.).

En fonction du volume d’enregistrements, il se peut que votre stockage SFTP dans Campaign doive être utilisé pour le transfert initial de données. [En savoir plus](#initial-data-transfer).

L’attribut externalId de la table de profils Campaign doit être renseigné avec l’attribut de contact contactId Dynamics 365 pour que l’entrée de contact fonctionne. Les entités personnalisées Campaign doivent également être renseignées avec un attribut d’identifiant unique Dynamics 365 ; cependant, cet attribut peut être stocké dans n’importe quel attribut d’entité personnalisée Campaign (c.-à-d. qu’il n’est pas nécessaire qu’il s’agisse d’externalId).

>[!NOTE]
>
>Pour l’entrée d’entités personnalisées, le suivi des modifications doit être activé dans Dynamics 365 pour les entités personnalisées synchronisées.

#### Entités personnalisées

L’[intégration Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) prend en charge les entités personnalisées, ce qui permet de synchroniser les entités personnalisées de Dynamics 365 avec les ressources personnalisées correspondantes dans Campaign.

Les nouvelles données des ressources personnalisées peuvent être utilisées à plusieurs fins, notamment pour la segmentation et la personnalisation.

L’intégration prend en charge les tables liées et non liées. La liaison est prise en charge jusqu’à trois niveaux (niveau1->niveau2->niveau3).

>[!IMPORTANT]
>
>Si un enregistrement de ressource personnalisée Campaign contient des informations personnelles, des recommandations spécifiques s’appliquent. En savoir plus dans [cette section](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).


Lors de la configuration des flux de données d’entités personnalisées, il est important de tenir compte des points suivants :

* La création et la modification de ressources personnalisées Campaign sont des opérations délicates qui doivent être effectuées uniquement par des utilisateurs experts.
* Pour les flux de données d’entités personnalisées, le suivi des modifications doit être activé dans Dynamics 365 pour les entités personnalisées synchronisées.
* Si un enregistrement parent et et un enregistrement enfant lié sont créés presque au même moment dans Dynamics 365, en raison du traitement parallèle de l’intégration, il peut arriver qu’un nouvel enregistrement enfant soit créé dans Campaign avant l’enregistrement de son parent.

* Si les enregistrements parent et enfant sont liés du côté Campaign à l’aide de l’option **Lien simple de cardinalité 1**, l’enregistrement enfant reste masqué et inaccessible (via l’interface utilisateur ou l’API) jusqu’à ce que l’enregistrement parent arrive dans Campaign.

* (En supposant que le **lien simple de cardinalité 1** est présent dans Campaign) Si l’enregistrement enfant est mis à jour ou supprimé dans Dynamics 365 et que cette modification est écrite dans Campaign avant que l’enregistrement parent ne s’affiche dans Campaign (ce qui est peu probable, mais qui peut parfois arriver), cette mise à jour ou suppression ne sera pas traitée dans Campaign et une erreur sera générée. Dans le cas d’une mise à jour, l’enregistrement en question devra de nouveau être mis à jour dans Dynamics 365 pour synchroniser l’enregistrement mis à jour. Dans le cas de la suppression, l’enregistrement en question devra être pris en charge séparément du côté Campaign, car il n’y aura plus d’enregistrement dans Dynamics 365 à supprimer ou à mettre à jour.

* Si vous vous trouvez dans une situation où vous pensez avoir masqué des enregistrements enfants sans avoir aucun moyen d’y accéder, vous pouvez temporairement changer le type de lien de cardinalité en **lien simple de cardinalité 0 ou 1** pour accéder à ces enregistrements.

Vous trouverez une présentation plus exhaustive des ressources personnalisées de Campaign dans [cette section](../../developing/using/key-steps-to-add-a-resource.md).

### Flux d’événements de marketing par email{#email-marketing-event-flow}

Les événements de marketing email sont envoyés de Campaign vers Microsoft Dynamics 365 pour apparaître dans la vue Planning.

Types d’événements de marketing pris en charge :
* Envoi - email envoyé au destinataire
* Ouverture- email ouvert par le destinataire
* Clic - URL dans l’email sur lequel clique le destinataire
* Bounce - l’email envoyé au destinataire a fait l’objet d’un hard bounce

Les attributs des événements suivants sont affichés dans Dynamics 365 :
* Nom de la campagne marketing
* Nom de la diffusion Email
* Date et heure
* URL de la page miroir de l’email
* URL sur laquelle l’utilisateur a cliqué (événements de clic uniquement)

Les événements de marketing email peuvent être activés/désactivés par type (envoi, ouverture, clic, bounce) de sorte que seuls les types d’événements sélectionnés seront transmis à Dynamics 365.

### Flux d’opt-out {#opt-out-flow}

Les valeurs d’opt-out (par exemple, denyList) sont synchronisées entre les systèmes ; vous avez le choix entre les options suivantes lors de l’intégration :

* **Unidirectionnelle (Microsoft Dynamics 365 vers Campaign)** : Dynamics 365 est une source de vérité pour les opt-outs. Les attributs d&#39;opt-out seront synchronisés dans un sens de Dynamics 365 vers Campaign Standard.
* **Unidirectionnelle (Campaign vers Microsoft Dynamics 365)** : Campaign Standard est la source de vérité pour les opt-outs. Les attributs d’opt-out seront synchronisés dans un sens, de Campaign Standard vers Dynamics 365
* **Bidirectionnelle** : Dynamics 365 ET Campaign Standard sont deux sources de vérité. Les attributs d’opt-out seront synchronisés de façon bidirectionnelle entre Campaign Standard et Dynamics 365

Si vous disposez également d’un processus distinct pour gérer la synchronisation des opt-outs entre les systèmes, le flux de données d’opt-out de l’intégration peut être désactivé.

>[!NOTE]
>
>Dans l’interface utilisateur de l’application d’intégration, les cas pratique d’opt-out **Unidirectionnelle (Microsoft Dynamics 365 vers Campaign)** et **Bidirectionnelle** sont configurés dans un workflow d’opt-out distinct. [En savoir plus](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>Le cas pratique d’opt-out **Unidirectionnelle (Campaign vers Microsoft Dynamics 365)** est une exception ; il est configuré dans le workflow d’entrée (contact vers profil).


Le mappage de flux d’opt-out doit être spécifié par le client, car les besoins métier peuvent varier d’une société à l’autre. Du côté Campaign, seuls les attributs d’opt-out d’usine peuvent être utilisés pour le mappage d’opt-out :

* denyList
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

Dans Dynamics 365, la plupart des champs d’opt-out ont le préfixe « donot », toutefois, vous pouvez également utiliser d’autres attributs personnalisés à des fins d’opt-out si les types de données sont compatibles.

### Transfert initial de données {#initial-data-transfer}

Le transfert initial de données peut prendre un certain temps en fonction du nombre d&#39;enregistrements que vous ingérez à partir de Microsoft Dynamics 365. Après le transfert initial des données, l’intégration récupérera les mises à jour incrémentales.
