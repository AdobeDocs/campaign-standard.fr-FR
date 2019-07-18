---
title: A propos des notifications push
seo-title: A propos des notifications push
description: A propos des notifications push
seo-description: Découvrez les spécificités principales du canal Notification push dans Adobe Campaign.
page-status-flag: jamais activé
uuid: 961 aaeb 5-6948-4 fd 2-b 8 d 7-de 4510 c 10566
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canaux
content-type: référence
topic-tags: notifications Push
discoiquuid: 23 b 4212 e-e 878-4922-be 20-50 fb 7 fa 88 ae 8
context-tags: Mobileapp, présentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 80e65c3fedc5452105c296144a683948daa69150

---


# A propos des notifications push{#about-push-notifications}

>[!CAUTION]
>
>L'implémentation des notifications push doit être réalisée par des utilisateurs experts. Si vous avez besoin d'aide, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels. Le canal Notification push est une fonctionnalité en option. Vérifiez votre contrat de licence et contactez votre chargé de compte pour l'activer.

Adobe Campaign vous permet d'envoyer des notifications push personnalisées et segmentées à des appareils mobiles iOS et Android.

Ces messages sont reçus sur des applications mobiles que vous configurez dans Adobe Campaign à l'aide des SDK V4 ou Experience Platform. Pour plus d'informations, consultez les sections [Configuration d'une application mobile à l'aide du SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) et [Configuration d'une application mobile à l'aide des SDK Adobe Experience Platform](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Dans Adobe Campaign, les données d'attributs de profil mobile envoyées depuis un appareil mobile sont stockées dans la ressource **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]** qui permet de définir les données que vous souhaitez collecter auprès des abonnés de vos applications.

Cette ressource doit être étendue pour collecter les données que vous avez l'intention d'envoyer depuis d'appareil mobile vers Adobe Campaign. Consultez à ce propos cette [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).

Dans Adobe Campaign, deux types de notification push sont disponibles :

* **[!UICONTROL Les notifications de type Alerte/Message/Badge]** vous permettent d'envoyer des messages texte standard avec des contenus supplémentaires (son, badge, lien profond, etc.) définissables dans la section **[!UICONTROL Options avancées].**

   Ces types de notification permettent d'ajouter un titre et un message dans lequel l'utilisation des champs de personnalisation est possible. Pour personnaliser votre message, veillez à sélectionner le modèle **[!UICONTROL Diffuser par notification push (vers profils)].**

* **[!UICONTROL Les notifications de type Notification silencieuse]** sont utilisées pour avertir de façon silencieuse l'application sans message ni contenu pour l'utilisateur final. Un cas pratique classique de ce type de message est d'avertir l'application de la disponibilité de contenu à télécharger depuis le serveur.

Certaines configurations spécifiques peuvent être paramétrées pour définir le comportement des notifications. Voir à ce propos [cette section](../../channels/using/customizing-a-push-notification.md).

En tant qu'utilisateur expert, reportez-vous aux [technotes](https://helpx.adobe.com/campaign/kb/acs-article-list.html) des applications mobiles pour définir ces configurations spécifiques.

>[!NOTE]
>
>Les lois sur la vie privée diffèrent d'un pays à l'autre. Certains pays exigent que vous informiez les utilisateurs des types de données collectées via les applications mobiles. Veuillez vous informer sur les lois en vigueur dans votre pays en ce qui concerne les applications mobiles. Vous devez vous assurer que les notifications push envoyées vers les applications mobiles sont conformes aux pré-requis et aux conditions définis par Apple (Apple Push Notification Service) et Google (Google Cloud Messaging ou Firebase Cloud Messaging).

**Contenu connexe :**

* [Préparation et envoi d'une notification push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Création d'une notification push multilingue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Envoi d'une notification push dans un workflow](../../automating/using/push-notification-delivery.md)
* [FAQ sur les notifications Push et In-App](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## Prérequis {#prerequisites}

>[!NOTE]
>Pour tirer parti de la fonctionnalité de notification Push de Campaign, vous devez fournir un certificat Push valide au format. pem sans mot de passe.
Si vous disposez d'un certificat p 12 valide, vous pouvez le convertir facilement en fichier. pem à l'aide de ressources en ligne.

Tout d'abord, pour pouvoir envoyer des notifications push, vous devez configurer votre application mobile à l'aide du SDK V4. Vous pouvez également configurer votre application mobile à l'aide des SDK Experience Platform. Pour plus d'informations à ce propos, consultez [cette page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Avant d'envoyer les notifications push, vous devez effectuer les opérations suivantes :

1. Vérifiez que vous avez accès au canal **[!UICONTROL Application mobile]dans Adobe Campaign.**
1. Configurez votre application mobile dans :

   * Adobe Campaign
   * L'interface Adobe Mobile Services

1. Effectuer la configuration spécifique de l'application mobile :

   * Intégrez le fichier de configuration téléchargé à partir de l'interface Adobe Mobile Services avec l'application mobile.
   * Intégrez le SDK d'Experience Cloud Mobile dans votre application mobile.

1. Définissez les données à collecter auprès des abonnés de vos applications. Les abonnés de l'application mobile dont le profil se trouve dans la base de données Adobe Campaign sont réconciliés en fonction des critères que vous avez définis.

Après avoir configuré votre application mobile, vous pouvez commencer à préparer et envoyer vos messages in-app. Voir à ce propos la section [Préparation et envoi d'une notification push](../../channels/using/preparing-and-sending-a-push-notification.md).
