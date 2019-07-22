---
title: Configuration d'une application mobile
seo-title: Configuration d'une application mobile
description: Configuration d'une application mobile
seo-description: Découvrez comment configurer Adobe Campaign pour envoyer des notifications push ou des message In-App à l'aide du SDK V4 ou du SDK Experience Platform.
page-status-flag: jamais activé
uuid: 63 e 1476 a -7875-4 f 48-ba 9 e -97 f 1 a 0007 e 42
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: référence
topic-tags: configuration-canaux
discoiquuid: 2 a 14500 f -5 ede -4131-8 b 1 a-b 7 fd 65 b 7 e 3 aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b9799c40bd7b6422409456db2c4f694f486b42f8

---


# Configuration d'une application mobile{#configuring-a-mobile-application}

Les notifications Push ou les messages in-app sont reçus sur les applications mobiles qui doivent d'abord être configurées dans Adobe Mobile Services, selon le canal que vous souhaitez utiliser.

* Pour envoyer des messages in-app et des notifications Push, vos applications mobiles doivent être configurées dans Adobe Campaign en exploitant les SDK Adobe Experience Platform. See [Using Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

* Pour envoyer uniquement des notifications Push, vous pouvez configurer l'intégration entre Adobe Campaign et Adobe Mobile Service à l'aide du SDK V 4. See [Using SDK V4](#using-sdk-v4).

After your mobile applications are set up in Adobe Campaign by leveraging the Experience Cloud Mobile SDK V4 or Experience Platform SDK, they need to be configured by an administrator under the [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>Les notifications Push et les implémentations In-App doivent être effectuées par des utilisateurs expérimentés. Si vous avez besoin d'aide, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels.

## Utilisation du SDK Adobe Experience Platform {#using-adobe-experience-platform-sdk}

Pour envoyer des notifications Push et des messages In-App à l'aide de l'application SDK Experience Platform, une application mobile doit être configurée dans Adobe Experience Platform Experience Platform Experience Platform Launch et configurée dans Adobe Campaign. Pour obtenir les étapes détaillées afin de configurer votre application mobile à l'aide du SDK Experience Platform, consultez cette [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Suivez les étapes ci-dessous pour commencer la configuration :

1. Vérifiez que vous pouvez accéder aux canaux **[!UICONTROL Mobile] : Notification push et Message In-App dans Adobe Campaign.** Si ce n'est pas le cas, contactez votre équipe de compte.

   ![](assets/launch_1.png)

1. Créez l'application mobile dans le lancement de Platform Platform en créant une propriété de type Mobile. For more info, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) documentation.
1. Install the **[!UICONTROL Adobe Campaign (Beta)]** extension for your mobile application in Experience Platform Launch:

   For more information on extensions, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard-beta) documentation.

1. Configurez des règles pour votre application dans Adobe Launch. Voir [Configuration de votre application dans Adobe Launch](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ConfiguringyourapplicationinLaunch).
1. Configurez votre application Adobe Launch dans Adobe Campaign Standard. Voir [Configuration de votre application Adobe Launch dans Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Ajoutez une configuration propre au canal à votre configuration de l'application mobile. Voir [Configuration de l'application spécifique au canal dans Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Utilisation du SDK V4 {#using-sdk-v4}

Contrairement aux messages in-app, les notifications push sont prises en charge par les SDK V4 et Adobe Experience Platform. Pour obtenir les étapes détaillées afin d'utiliser les notifications push avec votre application mobile, consultez cette [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Les applications mobiles recevant les notifications push doivent être configurées par un administrateur dans l'interface d'Adobe Campaign. En configurant Adobe Campaign et Adobe Mobile Services, vous serez en mesure d'utiliser les données de votre application mobile pour vos campagnes.

Pour pouvoir envoyer des notifications push, vous devez effectuer les opérations suivantes :

1. Vérifiez que vous avez accès au canal **[!UICONTROL Application mobile]dans Adobe Campaign.**
1. Configurez votre application mobile dans :

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Effectuer la configuration spécifique de l'application mobile :

   * Intégrez le fichier de configuration téléchargé à partir de l'interface Adobe Mobile Services avec l'application mobile.
   * Intégrez le SDK d'Experience Cloud Mobile dans votre application mobile.

1. Définissez les données à collecter auprès des abonnés de vos applications. Les abonnés de l'application mobile dont le profil se trouve dans la base de données Adobe Campaign sont réconciliés en fonction des critères que vous avez définis.

   Pour plus d'informations à ce propos, consultez [cette page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. Vérifiez que la configuration a été effectuée correctement en lançant votre application mobile sur votre appareil et en vous connectant. Assurez-vous que vous avez accepté de recevoir des notifications.
1. Then, in Adobe Campaign's advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Dans la liste, sélectionnez votre application mobile pour afficher ses propriétés. Vos informations d'abonnement s'affichent dans la liste des abonnés.

   ![](assets/push_notif_mobile_app.png)

1. Pour vérifier les applications mobiles auxquelles un profil s'est abonné, dans le menu **[!UICONTROL Profils &amp; audiences &gt; Profils]**, sélectionnez un profil et cliquez sur le bouton **Editer les propriétés du profil]à droite.[!UICONTROL ** Les applications mobiles sont répertoriées dans l'onglet **[!UICONTROL Abonnements à l'application mobile].**

   ![](assets/push_notif_subscriptions.png)