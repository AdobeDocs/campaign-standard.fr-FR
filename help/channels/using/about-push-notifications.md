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
translation-type: tm+mt
source-git-commit: 5ed46987a3778dfa100639de8be9b6d5ac5348b4

---


# A propos des notifications push{#about-push-notifications}

>[!CAUTION]
>
>L&#39;implémentation des notifications push doit être réalisée par des utilisateurs experts. Si vous avez besoin d&#39;aide, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels. Le canal Notification push est une fonctionnalité en option. Vérifiez votre contrat de licence et contactez votre chargé de compte pour l&#39;activer.

Adobe Campaign vous permet d&#39;envoyer des notifications push personnalisées et segmentées à des appareils mobiles iOS et Android.

Ces messages sont reçus sur les applications mobiles que vous configurez dans  Adobe Campaign en exploitant le SDK de la plateforme d’expérience. For more information on this, refer to [Configuring a mobile application using Adobe Experience Platform SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

Cette ressource doit être étendue pour collecter les données que vous avez l&#39;intention d&#39;envoyer depuis d&#39;appareil mobile vers Adobe Campaign. Consultez à ce propos cette [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).

Dans Adobe Campaign, deux types de notification push sont disponibles :

* **[!UICONTROL Alert/Message/Badge]** les notifications de type vous permettent d’envoyer des messages texte standard avec du contenu supplémentaire (son, badge, lien profond, etc.) que vous pouvez définir dans la **[!UICONTROL Advanced options]** section.

   Ces types de notification permettent d&#39;ajouter un titre et un message dans lequel l&#39;utilisation des champs de personnalisation est possible. To be able to personalize your message, make sure you select the **[!UICONTROL Send push on profiles]** template.

* **[!UICONTROL Silent push]** les notifications de type sont utilisées pour avertir l’application sans message ni contenu pour l’utilisateur final. Un cas pratique classique de ce type de message est d&#39;avertir l&#39;application de la disponibilité de contenu à télécharger depuis le serveur.

Certaines configurations spécifiques peuvent être paramétrées pour définir le comportement des notifications. Voir à ce propos [cette section](../../channels/using/customizing-a-push-notification.md).

En tant qu&#39;utilisateur expert, reportez-vous aux [technotes](https://helpx.adobe.com/campaign/kb/acs-article-list.html) des applications mobiles pour définir ces configurations spécifiques.

>[!NOTE]
>
>Les lois sur la vie privée diffèrent d&#39;un pays à l&#39;autre. Certains pays exigent que vous informiez les utilisateurs des types de données collectées via les applications mobiles. Veuillez vous informer sur les lois en vigueur dans votre pays en ce qui concerne les applications mobiles. Vous devez vous assurer que les notifications push envoyées vers les applications mobiles sont conformes aux pré-requis et aux conditions définis par Apple (Apple Push Notification Service) et Google (Google Cloud Messaging ou Firebase Cloud Messaging).

**Contenu connexe :**

* [Préparation et envoi d&#39;une notification push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Création d&#39;une notification push multilingue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Rapport des notifications push (Push notification)](../../reporting/using/push-notification-report.md)
* [Guide Campaign Standard Mobile](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Prérequis {#prerequisites}

>[!NOTE]
>Pour tirer parti de la fonctionnalité de notification push de Campaign, vous devez fournir un certificat push valide au format. pem sans mot de passe.
Si vous disposez d&#39;un certificat p12 valide, vous pouvez le convertir facilement en fichier. pem à l&#39;aide de ressources en ligne.

Tout d’abord, pour pouvoir  envoyer des notifications Push, vous devez configurer votre application mobile à l’aide des SDK de la plateforme d’expérience. Voir à ce propos [cette page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Avant d&#39;envoyer les notifications push, vous devez effectuer les opérations suivantes :

1. Vérifiez que vous avez accès au canal **[!UICONTROL Mobile app]** dans Adobe Campaign.
1. Configurez votre application mobile dans :

   * Adobe Campaign
   * L&#39;interface Adobe Mobile Services

1. Effectuer la configuration spécifique de l&#39;application mobile :

   * Intégrez le fichier de configuration téléchargé à partir de l&#39;interface Adobe Mobile Services avec l&#39;application mobile.
   * Intégrez le SDK d&#39;Experience Cloud Mobile dans votre application mobile.

1. Définissez les données à collecter auprès des abonnés de vos applications. Les abonnés de l&#39;application mobile dont le profil se trouve dans la base de données Adobe Campaign sont réconciliés en fonction des critères que vous avez définis.

Après avoir configuré votre application mobile, vous pouvez commencer à préparer et envoyer vos messages in-app. Voir à ce propos la section [Préparation et envoi d&#39;une notification push](../../channels/using/preparing-and-sending-a-push-notification.md).
