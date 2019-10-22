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
translation-type: tm+mt
source-git-commit: 96001355220a9dd0cd3851d3f7de9f4dc8ea2782

---


# A propos de la messagerie in-app{#about-in-app-messaging}

La messagerie in-app est un canal de messagerie qui permet d'afficher un message lorsque l'utilisateur est actif dans l'application mobile. Ce type de message complète les notifications push qui sont diffusées au centre de notification du téléphone de l'utilisateur. Pour plus d'informations sur le canal Notification push, consultez cette [section](../../channels/using/about-push-notifications.md).

Pour ce canal, les applications mobiles doivent être intégrées avec le SDK Adobe Experience Platform. Ces applications doivent être activées dans Adobe Experience Platform Launch avant d'être disponibles dans Adobe Campaign pour les diffusions In-App.

![](assets/launch_campaign.png)

Pour commencer à envoyer des messages In-App sur des applications mobiles en utilisant le SDK Experience Platform, vous devez remplir les conditions préalables suivantes :

1. Dans Adobe Campaign, vérifiez que vous pouvez accéder au canal **[!UICONTROL In-App]**. Si vous ne pouvez pas accéder à ces canaux, contactez l'équipe de votre compte.

1. Pour tirer parti des cas d’utilisation mobile dans Adobe Campaign Standard avec une application SDK Experience Cloud, une application mobile doit être créée dans Adobe Experience Platform Launch et configurée dans Adobe Campaign Standard. Pour le guide détaillé, reportez-vous à cette [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

1. Une fois configuré, vous pouvez désormais préparer votre message in-app. Voir à ce propos [cette page](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Vous pouvez ensuite décider d’envoyer un message [](../../channels/using/customizing-an-in-app-message.md) in-app ou une [personnalisation du type](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)d’un message de notification local.

1. Votre livraison est maintenant prête à être envoyée. Pour en savoir plus, consultez cette [page](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Contenu connexe :**

* [Rapport In-App](../../reporting/using/in-app-report.md)
* [FAQ push et in-app](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Cas d’utilisation mobile pris en charge dans Adobe Campaign Standard](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
