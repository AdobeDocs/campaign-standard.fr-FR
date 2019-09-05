---
title: A propos de la messagerie in-app
seo-title: A propos de la messagerie in-app
description: A propos de la messagerie in-app
seo-description: Affichez un message ou une alerte dans l'application mobile avec la messagerie in-app.
page-status-flag: never-activated
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: delivery,triggers,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 74f037ba618639ab61edfb8311adeb44a7a99ebd

---


# A propos de la messagerie in-app{#about-in-app-messaging}

La messagerie in-app est un canal de messagerie qui permet d'afficher un message lorsque l'utilisateur est actif dans l'application mobile. Ce type de message complète les notifications push qui sont diffusées au centre de notification du téléphone de l'utilisateur. Pour plus d'informations sur le canal Notification push, consultez cette [section](../../channels/using/about-push-notifications.md).

Pour ce canal, les applications mobiles doivent être intégrées avec le SDK Adobe Experience Platform. Ces applications doivent être activées dans Adobe Experience Platform Launch avant d'être disponibles dans Adobe Campaign pour les diffusions In-App.

![](assets/launch_campaign.png)

Pour commencer à envoyer des messages In-App sur des applications mobiles en utilisant le SDK Experience Platform, vous devez remplir les conditions préalables suivantes :

1. Dans Adobe Campaign, vérifiez que vous pouvez accéder au canal **[!UICONTROL In-App]**. Si vous ne pouvez pas accéder à ces canaux, contactez l'équipe de votre compte.
1. Dans Experience Platform Launch, concevez l'application mobile en créant une propriété mobile et instrumentez-la avec le SDK Experience Platform.

   Pour plus d'informations, consultez la section sur la [configuration d'une application mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) dans la documentation Adobe Launch.

1. Dans Experience Platform Launch, installez l'extension **[!UICONTROL Adobe Campaign Standard]** pour votre application mobile :

   Pour plus d'informations sur les extensions, consultez la section [Configurer l'extension Campaign Standard dans Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) dans la documentation Experience Platform Launch.

1. Dans Experience Platform Launch, configurez les règles et les éléments de données pour votre application. Voir [Configurer votre application dans Experience Platform Launch](https://helpx.adobe.com/fr/campaign/kb/config-app-in-launch.html#Step1Createdataelements)

1. Configurez votre application Experience Platform Launch dans Adobe Campaign Standard. Voir [Configuration de votre application Experience Platform Launch dans Adobe Campaign](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).

Pour découvrir comment configurer les SDK Experience Platform, consultez cette [page](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html).

**Contenu connexe :**

* [Préparation et envoi d'un message In-App](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Personnalisation d'un message in-app](../../channels/using/customizing-an-in-app-message.md)
* [Personnaliser un type de message de notification locale ](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)
* [Envoi d'un message In-App dans un workflow](../../automating/using/in-app-delivery.md)
* [FAQ sur les notifications push et les messages In-App](https://helpx.adobe.com/fr/campaign/kb/push_inapp_faq.html)