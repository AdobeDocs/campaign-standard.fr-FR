---
title: A propos des notifications push
description: Découvrez les spécificités principales du canal Notification push dans Adobe Campaign.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1301'
ht-degree: 100%

---


# A propos des notifications push{#about-push-notifications}

>[!CAUTION]
>
>L’implémentation des notifications push doit être réalisée par des utilisateurs experts. Si vous avez besoin d’aide, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels. Le canal Notification push est une fonctionnalité en option. Vérifiez votre contrat de licence et contactez votre chargé de compte pour l’activer.

Adobe Campaign vous permet d’envoyer des notifications push personnalisées et segmentées à des appareils mobiles iOS et Android.

Ces messages sont reçus sur des applications mobiles que vous configurez dans Adobe Campaign à l’aide du SDK Experience Platform. Voir à ce propos [Configuration d’une application mobile à l’aide des SDK Experience Platform](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html).

Dans Adobe Campaign, les données d’attributs de profil mobile envoyées depuis un appareil mobile sont stockées dans la ressource **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]** qui permet de définir les données que vous souhaitez collecter auprès des abonnés de vos applications.

Cette ressource doit être étendue pour collecter les données que vous avez l’intention d’envoyer depuis d’appareil mobile vers Adobe Campaign. Consultez à ce propos cette [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).

Dans Adobe Campaign, deux types de notification push sont disponibles :

* **[!UICONTROL Les notifications de type Alerte/Message/Badge]** vous permettent d’envoyer des messages texte standard avec des contenus supplémentaires (son, badge, lien profond, etc.) définissables dans la section **[!UICONTROL Options avancées]**.

   Ces types de notification permettent d’ajouter un titre et un message dans lequel l’utilisation des champs de personnalisation est possible. Pour personnaliser votre message, veillez à sélectionner le modèle **[!UICONTROL Diffuser par notification push (vers profils)]**.

* **[!UICONTROL Les notifications de type Notification silencieuse]** sont utilisées pour avertir de façon silencieuse l’application sans message ni contenu pour l’utilisateur final. Un cas pratique classique de ce type de message est d’avertir l’application de la disponibilité de contenu à télécharger depuis le serveur.

Certaines configurations spécifiques peuvent être paramétrées pour définir le comportement des notifications. Voir à ce propos [cette section](../../channels/using/customizing-a-push-notification.md).

En tant qu’utilisateur expert, reportez-vous aux [technotes](https://helpx.adobe.com/fr/campaign/kb/acs-article-list.html) des applications mobiles pour définir ces configurations spécifiques.

>[!NOTE]
>
>Les lois sur la vie privée diffèrent d’un pays à l’autre. Certains pays exigent que vous informiez les utilisateurs des types de données collectées via les applications mobiles. Veuillez vous informer sur les lois en vigueur dans votre pays en ce qui concerne les applications mobiles. Vous devez vous assurer que les notifications push envoyées vers les applications mobiles sont conformes aux pré-requis et aux conditions définis par Apple (Apple Push Notification Service) et Google (Google Cloud Messaging ou Firebase Cloud Messaging).

**Contenu connexe:**

* [Préparation et envoi d’une notification push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Création d’une notification push multilingue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Rapport des notifications push (Push notification)](../../reporting/using/push-notification-report.md)
* [Guide Campaign Standard Mobile](https://helpx.adobe.com/fr/campaign/kb/acs-mobile.html)

## Prérequis {#prerequisites}

>[!NOTE]
>Pour tirer parti de la fonctionnalité de notification push de Campaign, vous devez fournir un certificat push valide au format. pem sans mot de passe.
>
>Si vous disposez d’un certificat p12 valide, vous pouvez le convertir facilement en fichier. pem à l’aide de ressources en ligne.

Avant d’envoyer les notifications push, vous devez effectuer les opérations suivantes :

1. Dans Adobe Campaign, vérifiez que vous pouvez accéder au canal **[!UICONTROL Notification Push]**. Si vous ne pouvez pas accéder à ces canaux, contactez l&#39;équipe de votre compte.

1. Vérifiez que votre utilisateur dispose des autorisations nécessaires dans Adobe Campaign Standard et Experience Platform Launch.

1. Dans Experience Platform Launch, créez une propriété mobile. Pour plus d’informations, voir [Configuration d’une propriété mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. Dans Experience Platform Launch, installez l’extension **[!UICONTROL Adobe Campaign Standard]**.

1. Dans Adobe Campaign Standard, configurez la propriété mobile que vous avez créée dans Experience Platform Launch. Pour plus d’informations, voir [Configuration de votre application Experience Platform Launch dans Adobe Campaign](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign).

1. Ajoutez la configuration spécifique au canal à votre configuration d’application mobile. Pour plus d&#39;informations, reportez-vous à la section [Configuration de l&#39;application spécifique au canal dans Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Pour prendre en charge les mises en œuvre de cas d’utilisation mobile, reportez-vous aux instructions détaillées sur les extensions, les règles Experience Platform Launch et l’implémentation de SDK dans la section [Cas d’utilisation mobile pris en charge dans Adobe Campaign Standard avec utilisation des SDK Adobe Experience Platform](https://helpx.adobe.com/fr/campaign/kb/configure-launch-rules-acs-use-cases.html).

## FAQ sur les notifications push {#push-faq}

### Quelles seraient les recommandations utiles en ce qui concerne les ressources pour en savoir plus sur le canal push ? {#resource-push}

Consultez les ressources ci-dessous :

* [Tutoriels vidéos](https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Documentation du produit](../../channels/using/about-push-notifications.md)
* Configuration à l’aide de la [documentation](../../administration/using/configuring-a-mobile-application.md) du SDK AEP
* [Page de la communauté](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### Que dois-je faire pour acquérir un jeton push dans Campaign ? {#push-token-acquisition}

Vérifiez que l’équipe chargée de l’approvisionnement a terminé l’approvisionnement du canal push dans Adobe Campaign Standard. Mettez en œuvre l’API setPushIdentifier à partir du SDK. Pour plus d’informations à ce propos, consultez cette [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

### Une fois que je dispose d’un jeton push et d’un ECID dans Campaign, que dois-je faire pour envoyer une notification push ? {#sending-push}

Les clients doivent fournir un certificat push valide au format .pem pour envoyer une notification push. Vous n’avez pas besoin d’un mot de passe pour ce certificat.

### Que faire si je dispose d’un certificat .p12 au lieu d’un certificat .pem ? {#certificates}

Vous pouvez convertir un certificat .p12 en certificat .pem en exécutant la commande ci-dessous dans un terminal. Plusieurs ressources en ligne sont également disponibles pour les instructions de conversion.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### Comment savoir si le téléchargement du certificat a réussi ? {#certificate-upload}

Le message suivant s’affiche.

![](assets/faq_2.png)

### Puis-je télécharger simultanément des certificats Production et Sandbox pour l’application iOS (s/o pour Android) ? {#prod-sandbox-certificate}

Non, les applications fonctionnent en mode sandbox ou de production et leur mode ne peut pas être changé (c’est-à-dire sandbox en application de production) une fois configurées. Nous vous recommandons de tester d’abord votre application en mode sandbox, puis de passer en mode de production.

Pour passer en mode de production, vous devez créer une autre application. Veillez également à ne pas cocher la case sandbox et à télécharger un certificat de production.

### Puis-je télécharger simultanément les informations d’identification iOS et Android ? {#ios-android-credentials}

Oui, Campaign prend en charge les deux plates-formes en même temps et vous permet de télécharger des informations d’identification pour les deux plates-formes.

### J’ai téléchargé les certificats push avec succès, mais aucun message push n’est envoyé. {#push-certificates-upload}

Vérifiez que vos certificats push sont valides en les testant [ici](https://pushtry.com/).

### Je peux envoyer des notifications push avec succès depuis pushtry.com mais pas via Campaign. {#push-not-sending}

Vérifiez que vous suivez bien les instructions de payload push fournies [ici](../../administration/using/push-payload.md).

Notez que pour Android, Campaign ne prend en charge que la payload de données et non celle de notification.

### J’ai configuré une application dans la section Administration d’Adobe Campaign Standard, mais l’application mobile n’est pas disponible dans les propriétés de diffusion. {#mobile-app-unavailable}

Un certificat push valide doit également être téléchargé pour qu’une application puisse être disponible dans les propriétés de diffusion.

### J&#39;ai suivi toutes les instructions de cette page et pourtant je ne parviens pas à envoyer une notification push depuis Campaign. {#push-troubleshoot}

Veuillez faire une demande d&#39;Assistance clientèle.

### Les notifications push sont diffusées depuis Campaign mais le fichier multimédia ne s’affiche pas.{#media-file-unavailable}

Les développeurs d’application mobile doivent gérer la prise en charge des fichiers multimédia dans l’application. Parfois, la bande passante du réseau peut également empêcher le rendu d’un fichier multimédia. Reportez-vous à cette [page](../../administration/using/image-push-notification.md) pour des pointeurs additionnels.

### Que dois-je faire pour activer le reporting push dans Campaign ? {#push-reporting-enable}

Procédez comme suit :

* Configurez un postback de tracking push. Les instructions se trouvent [ici](../../administration/using/configuring-a-mobile-application.md).
* Implémentez l’API trackAction à partir de Mobile Core. Voir cette [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) pour plus d’informations.

Vous trouverez des instructions plus détaillées sur cette [page](../../administration/using/push-tracking.md).

### Quels rapports sont disponibles pour le canal push ? {#push-report-available}

Un rapport d’usine est disponible dans Adobe Campaign pour le canal push. Consultez cette [documentation](../../reporting/using/push-notification-report.md).

Consultez cette [page](../../reporting/using/indicator-calculation.md#push-notification-delivery) pour comprendre comment est calculée chaque mesure push.

### Les liens profonds sont-ils pris en charge dans les messages push et In-App ? {#deeplink-push}

Oui, les liens profonds sont pris en charge dans les messages push. Les liens profonds doivent inclure les éléments suivants :

* Un langage indiquant que le tracking des diffusions doit être désactivé pour que les liens profonds fonctionnent.
* Apflyer avec Branch en tant que partenaires pouvant effectuer le tracking de liens profonds. Pour plus d&#39;informations sur l&#39;intégration de Branch et Adobe Campaign Standard, consultez cette [page](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
