---
title: A propos de la messagerie in-app
description: Affichez un message ou une alerte dans l'application mobile avec la messagerie in-app.
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
source-git-commit: 501ba6f97a86076116d4d84f43df674536e12f6a

---


# A propos de la messagerie in-app{#about-in-app-messaging}

La messagerie in-app est un canal de messagerie qui permet d&#39;afficher un message lorsque l&#39;utilisateur est actif dans l&#39;application mobile. Ce type de message complète les notifications push qui sont diffusées au centre de notification du téléphone de l&#39;utilisateur. Pour plus d&#39;informations sur le canal Notification push, consultez cette [section](../../channels/using/about-push-notifications.md).

Pour ce canal, les applications mobiles doivent être intégrées avec le SDK Adobe Experience Platform. Ces applications doivent être activées dans Adobe Experience Platform Launch avant d&#39;être disponibles dans Adobe Campaign pour les diffusions In-App.

![](assets/launch_campaign.png)

Pour commencer à envoyer des messages In-App sur des applications mobiles en utilisant le SDK Experience Platform, vous devez remplir les conditions préalables suivantes :

1. Dans Adobe Campaign, vérifiez que vous pouvez accéder au canal **[!UICONTROL In-App]**. Si vous ne pouvez pas accéder à ces canaux, contactez l&#39;équipe de votre compte.

1. Pour tirer parti des cas pratiques mobiles dans Adobe Campaign Standard avec une application SDK Experience Cloud, une application mobile doit être créée dans Adobe Experience Platform Launch et configurée dans Adobe Campaign. Pour consulter le guide détaillé, reportez-vous à cette [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

1. Une fois la configuration effectuée, vous pouvez préparer votre message in-app. Pour plus d&#39;informations à ce propos, Voir à ce propos consultez [cette page](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Vous pouvez ensuite décider d&#39;envoyer un [message in-app](../../channels/using/customizing-an-in-app-message.md) ou de [personnaliser un type de message de notification locale](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

1. Votre diffusion est maintenant prête à être envoyée. Pour en savoir plus, consultez cette [page](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Contenu connexe :**

* [Rapport In-App](../../reporting/using/in-app-report.md)
* [FAQ sur les notifications push et les messages In-App](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Cas pratiques mobiles pris en charge dans Adobe Campaign Standard](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
* [Guide d&#39;Adobe Campaign Standard Mobile](https://helpx.adobe.com/campaign/kb/acs-mobile.html)
