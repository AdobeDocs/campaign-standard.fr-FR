---
solution: Campaign Standard
product: campaign
title: Cas pratiques des déclencheurs d'abandon
description: Découvrez comment utiliser l'intégration Triggers Experience Cloud grâce à ces différents cas pratiques.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '1022'
ht-degree: 100%

---


# Cas pratiques des déclencheurs d&#39;abandon{#abandonment-triggers-use-cases}

Cette section détaille divers cas pratiques qui peuvent être implémentés via l&#39;intégration entre Adobe Campaign et les Triggers Experience Cloud. Vous trouverez deux exemples de cas pratiques :

* [Déclencheur d&#39;abandon de navigation](#browse-abandonment-trigger) : envoyer une communication à des clients ayant abandonné leur visite sur votre site web.
* [Déclencheur d&#39;abandon de recherche](#search-abandonment-trigger) : reprendre le contact avec des visiteurs ayant effectué une recherche sur votre site web, mais sans faire d&#39;achat.

>[!NOTE]
>
>Les cas pratiques décrits dans cette section sont basés sur l&#39;Identifiant du visiteur Experience Cloud. Ils peuvent également être mis en œuvre avec le Declared ID Experience Cloud. Les identifiants de type Declared ID hachés et cryptés sont également pris en charge. Vous pouvez envoyer des emails/SMS à un profil qui n&#39;existe pas dans Campaign en décryptant directement l&#39;adresse email/le numéro de mobile cryptés. Dans ce cas, il n&#39;est toutefois pas possible d&#39;effectuer une personnalisation avec les données de profil.

## Conditions requises   {#pre-requisites}

Afin de pouvoir mettre en œuvre ces cas pratiques, vous devez avoir accès aux solutions/Core Services suivants :

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select ou Standard.
* Core Service Triggers Experience Cloud
* Core Service DTM Experience Cloud
* Identifiant du visiteur Experience Cloud et Core Service People Experience Cloud

Il vous faudra également un site web opérationnel.

Pour plus d&#39;informations, consultez [Configuration des solutions et services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Déclencheur d&#39;abandon de navigation {#browse-abandonment-trigger}

Dans ce cas pratique, nous allons créer un déclencheur simple qui se déclenchera à chaque fois qu&#39;un client abandonnera sa visite sur le site Web. Cet exemple part du principe que vous avez configuré DTM pour collecter et envoyer des données vers Adobe Marketing, et que tous vos événements sont déjà créés.

### Création d&#39;un déclencheur Experience Cloud   {#creating-an-experience-cloud-trigger}

1. Sélectionnez **[!UICONTROL Gérer les déclencheurs]** dans le menu Experience Cloud Activation Core Service.

   ![](assets/trigger_uc_browse_1.png)

1. Choisissez un type de déclencheur (**[!UICONTROL Abandon]**, dans ce cas pratique).

   ![](assets/trigger_uc_browse_2.png)

1. Pour ce cas pratique, il nous faut un déclencheur d&#39;abandon simple. L&#39;objectif métier est d&#39;identifier les visiteurs qui naviguent sur notre site Web de réservation de voyages et qui consultent la page « Offres » sans faire de réservation. Une fois cette audience identifiée, nous voulons les contacter rapidement. Dans cet exemple, nous avons choisi d&#39;envoyer le déclencheur après une période de 10 minutes.

   ![](assets/trigger_uc_browse_3.png)

### Utiliser le déclencheur dans Adobe Campaign   {#using-the-trigger-in-adobe-campaign}

Maintenant que nous avons créé un déclencheur Experience Cloud, nous allons l&#39;utiliser dans Adobe Campaign.

Dans Adobe Campaign, vous devez créer un déclencheur lié à celui créé dans Experience Cloud.

1. Pour créer le déclencheur dans Adobe Campaign, cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez **[!UICONTROL Plans marketing]** > **[!UICONTROL Messages transactionnels]** > **[!UICONTROL Triggers Experience Cloud]**.

   ![](assets/remarketing_1.png)

1. Cliquez sur **[!UICONTROL Créer]**.
1. Sélectionnez le déclencheur que vous avez créé précédemment et cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/trigger_uc_browse_5.png)

1. Sélectionnez le canal **[!UICONTROL Email]** et la dimension de ciblage **[!UICONTROL Evénement temps réel]**, puis cliquez sur **[!UICONTROL Créer]**.

   ![](assets/trigger_uc_browse_6bis.png)

1. Publiez le déclencheur dans Adobe Campaign. Ce processus créera toujours automatiquement un modèle de message transactionnel.

   ![](assets/trigger_uc_browse_6.png)

1. Pour afficher le modèle de message, cliquez sur le bouton **[!UICONTROL Autres choix]**, en haut à droite, puis sur **[!UICONTROL Modèle transactionnel de déclencheur]**.

1. Personnalisez son contenu et les données expéditeur.

   ![](assets/trigger_uc_browse_8.png)

1. Publiez le modèle de message. Le déclencheur est maintenant en ligne et opérationnel.

   ![](assets/trigger_uc_browse_0.png)

### Exécuter le scénario   {#running-the-scenario}

1. Ce cas pratique commence par un email initial envoyé à votre audience avec Adobe Campaign.

   ![](assets/trigger_uc_browse_9.png)

1. Le destinataire ouvre l&#39;email.

   ![](assets/trigger_uc_browse_10.png)

1. Il clique sur un lien qui ouvre une page de votre site Web. Dans cet exemple, la bannière dirige le destinataire vers la page d&#39;accueil du site Web de réservation de voyages.

   ![](assets/trigger_uc_browse_11.png)

1. Le destinataire se rend sur la page « Offres » mais interrompt brusquement sa visite. Après un délai de 10 minutes, Adobe Campaign déclenche l&#39;envoi du message transactionnel.

   ![](assets/trigger_uc_browse_12.png)

1. À tout moment, vous pouvez vérifier les logs Experience Cloud pour voir combien de fois le déclencheur s&#39;est lancé.

   ![](assets/trigger_uc_browse_13.png)

1. Vous pouvez également afficher le rapport de déclencheur Adobe Campaign.

   ![](assets/trigger_uc_browse_14.png)

## Déclencheur d&#39;abandon de recherche   {#search-abandonment-trigger}

Dans ce cas pratique, nous allons créer un déclencheur pour reprendre contact avec des visiteurs ayant visité notre site Web de réservation de voyages et qui, ayant cherché une destination sans trouver de résultats pertinents, n&#39;ont rien réservé. Le processus général est le même que pour le cas pratique précédent (voir [Déclencheur d&#39;abandon de navigation](#browse-abandonment-trigger)). Ici, nous allons nous focaliser sur la personnalisation de l&#39;email de remarketing.

### Création d&#39;un déclencheur Experience Cloud   {#creating-an-experience-cloud-trigger-1}

Suivez les étapes décrites dans le cas pratique précédent pour créer le déclencheur Experience Cloud. Voir [Créer un déclencheur Experience Cloud](#creating-an-experience-cloud-trigger). La différence principale est la définition du déclencheur.

![](assets/trigger_uc_search_1.png)

La section **[!UICONTROL Inclure les métadonnées]** vous permet de transférer toutes les données collectées via Analytics vers la payload de déclencheur. Dans cet exemple, nous allons créer un eVar personnalisé (eVar 3, par exemple) pour collecter le terme de recherche que le visiteur saisit. Ce terme sera ensuite utilisé dans l&#39;email transactionnel envoyé à ce même visiteur.

### Utiliser le déclencheur dans Adobe Campaign   {#using-the-trigger-in-adobe-campaign-1}

1. Suivez les étapes décrites dans le cas pratique précédent pour créer le déclencheur dans Adobe Campaign. Voir [Utiliser le déclencheur dans Adobe Campaign](#using-the-trigger-in-adobe-campaign). La différence principale est la manière dont, dans Adobe Campaign, nous accédons et utilisons les métadonnées transmises dans la payload de déclencheur.
1. Dans le déclencheur d&#39;abandon de recherche créé dans Adobe Campaign, cliquez sur l&#39;icône **[!UICONTROL Contenu et enrichissement de l&#39;événement]** pour voir la payload transmise à Adobe Campaign.

   ![](assets/trigger_uc_search_2.png)

1. Nous voyons que l&#39;eVar personnalisé est passé dans la payload de déclencheur et est associé à la table **Contexte de l&#39;événement** (ctx). Nous pouvons à présent y accéder pour personnaliser le message transactionnel.

   ![](assets/trigger_uc_search_3.png)

1. Dans cet exemple, nous avons choisi d&#39;inclure le terme de recherche de la destination dans l&#39;objet de l&#39;email et dans le corps de l&#39;émail.

   ![](assets/trigger_uc_search_4.png)

1. Lors de la sélection d&#39;un champ de personnalisation, cherchez les métadonnées de la payload dans la table **Evénement transactionnel** (rtEvent) puis dans la sous-table **Contexte de l&#39;événement** (ctx).

   ![](assets/trigger_uc_search_5.png)

### Exécuter le scénario   {#running-the-scenario-1}

1. Le visiteur se rend sur un site Web de réservation de voyages et lance une recherche pour une destination. Dans cet exemple, le visiteur cherche un voyage au Japon mais ne trouve aucun résultat. C&#39;est pour nous l&#39;occasion de contacter le visiteur pour lui recommander un projet de voyage alternatif.

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >Dans ce cas pratique, nous partons de l&#39;hypothèse selon laquelle le visiteur/destinataire a déjà ouvert et cliqué sur un email en provenance du même site Web. Cela nous permet d&#39;utiliser et de collecter l&#39;Identifiant du visiteur et de l&#39;associer au destinataire. Cette étape n&#39;est nécessaire qu&#39;une seule fois.

1. Quelques minutes plus tard, le même visiteur/destinataire reçoit un message remarketing. Ce message comprend la destination recherchée récemment.

   ![](assets/trigger_uc_search_7.png)

