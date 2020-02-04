---
title: Configuration d'une application mobile
description: Découvrez comment configurer Adobe Campaign pour envoyer des notifications push ou des message In-App à l'aide du SDK V4 ou du SDK Experience Platform.
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e31e8c63fa94d190211c7a51e7f1091657c9f479

---


# Configuration d&#39;une application mobile{#configuring-a-mobile-application}

Les notifications push et les messages In-App sont reçus sur les applications mobiles qui doivent d&#39;abord être configurées dans Adobe Campaign, selon le canal que vous souhaitez utiliser.

Pour envoyer des messages In-App et des notifications push, les applications mobiles doivent être configurées dans Adobe Campaign en utilisant les SDK Adobe Experience Platform. Voir [Utilisation du SDK Adobe Experience Platform](#using-adobe-experience-platform-sdk).

Une fois vos applications mobiles configurées dans Adobe Campaign en utilisant le SDK Experience Cloud Mobile V4 ou le SDK Experience Platform, elles doivent être configurées par un administrateur sous [!UICONTROL Administration] > [!UICONTROL Canaux] > [!UICONTROL Application mobile].

>[!IMPORTANT]
>
>Les implémentations In-App et des notifications push doivent être effectuées par des utilisateurs expérimentés. Si vous avez besoin d&#39;aide, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels.

Une fois une application mobile configurée, vous pouvez récupérer les données de PII qu&#39;elle a collectées pour créer ou mettre à jour des profils à partir de votre base de données. Pour plus d&#39;informations à ce sujet, reportez-vous à cette section : [Création et mise à jour des informations de profil en fonction des données d&#39;application mobile](../../channels/using/updating-profile-with-mobile-app-data.md).

Pour obtenir des instructions générales sur les livraisons mobiles dans Adobe Campaign Standard, reportez-vous à cette [page](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Utilisation du SDK Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!NRemarque]
>
>Pour en savoir plus sur les différents cas pratiques mobiles pris en charge dans Adobe Campaign Standard grâce à l&#39;utilisation des SDK Adobe Experience Platform SDK, consultez cette [page](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Pour envoyer des notifications push et des messages In-App avec l&#39;application SDK Experience Platform, une application mobile doit être créée dans Adobe Experience Platform Launch et configurée dans Adobe Campaign. Pour obtenir les étapes détaillées afin de configurer votre application mobile à l&#39;aide du SDK Experience Platform, consultez cette [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Suivez les étapes ci-dessous pour commencer la configuration :

1. Vérifiez que vous pouvez accéder aux canaux **[!UICONTROL Mobile]** : Notification push et Message In-App dans Adobe Campaign. Si ce n&#39;est pas le cas, contactez l&#39;équipe chargée de votre compte.

   ![](assets/launch_1.png)

1. Créez l&#39;application mobile dans Experience Platform Launch en créant une propriété de type Mobile. Pour plus d&#39;informations, consultez la documentation d&#39;[Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property).
1. Installez l&#39;extension **[!UICONTROL Adobe Campaign Standard]**pour votre application mobile dans Experience Platform Launch :

   Pour plus d&#39;informations sur les extensions, consultez la documentation d&#39;[Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Configurez des règles pour votre application dans Adobe Launch. Voir [Configuration de votre application dans Adobe Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements).
1. Configurez votre application Adobe Launch dans Adobe Campaign Standard. Voir [Configuration de votre application Adobe Launch dans Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Ajoutez une configuration propre au canal à votre configuration de l&#39;application mobile. Voir [Configuration de l&#39;application spécifique au canal dans Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)
