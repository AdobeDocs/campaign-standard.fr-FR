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
internal: n
snippet: y
translation-type: ht
source-git-commit: 8111dfd2fd3cf254f73d0b01917d606b0a70aa84

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

**Contenu connexe :**

* [Préparation et envoi d’une notification push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Création d’une notification push multilingue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Rapport des notifications push (Push notification)](../../reporting/using/push-notification-report.md)
* [Guide Campaign Standard Mobile](https://helpx.adobe.com/fr/campaign/kb/acs-mobile.html)

## Prérequis {#prerequisites}

>[!NOTE]
>Pour tirer parti de la fonctionnalité de notification push de Campaign, vous devez fournir un certificat push valide au format. pem sans mot de passe.
Si vous disposez d’un certificat p12 valide, vous pouvez le convertir facilement en fichier. pem à l’aide de ressources en ligne.

Avant d’envoyer les notifications push, vous devez effectuer les opérations suivantes :

1. Dans Adobe Campaign, vérifiez que vous pouvez accéder au canal **[!UICONTROL Notification Push]**. Si vous ne pouvez pas accéder à ces canaux, contactez l&#39;équipe de votre compte.

1. Vérifiez que votre utilisateur dispose des autorisations nécessaires dans Adobe Campaign Standard et Experience Platform Launch.

1. Dans Experience Platform Launch, créez une propriété mobile. Pour plus d’informations, voir [Configuration d’une propriété mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. Dans Experience Platform Launch, installez l’extension **[!UICONTROL Adobe Campaign Standard]**.

1. Dans Adobe Campaign Standard, configurez la propriété mobile que vous avez créée dans Experience Platform Launch. Pour plus d’informations, voir [Configuration de votre application Experience Platform Launch dans Adobe Campaign](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign).

1. Ajoutez la configuration spécifique au canal à votre configuration d’application mobile. Pour plus d&#39;informations, reportez-vous à la section [Configuration de l&#39;application spécifique au canal dans Adobe Campaign](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

1. Pour prendre en charge les mises en œuvre de cas d’utilisation mobile, reportez-vous aux instructions détaillées sur les extensions, les règles Experience Platform Launch et l’implémentation de SDK dans la section [Cas d’utilisation mobile pris en charge dans Adobe Campaign Standard avec utilisation des SDK Adobe Experience Platform](https://helpx.adobe.com/fr/campaign/kb/configure-launch-rules-acs-use-cases.html).