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
source-git-commit: f4f09556fed8c3cca44a72ac6dfeb280379d58c3
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 20%

---


# Configuration d&#39;une application mobile{#configuring-a-mobile-application}

## Configuring a mobile application using Adobe Experience Platform SDKs {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Les implémentations In-App et des notifications push doivent être effectuées par des utilisateurs expérimentés. Si vous avez besoin d&#39;aide, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels.

Pour envoyer des notifications push et des messages In-App avec l&#39;application SDK Experience Platform, une application mobile doit être créée dans Adobe Experience Platform Launch et configurée dans Adobe Campaign.

Pour plus d’informations sur la fonctionnalité obsolète SDK Mobile version 4, reportez-vous à cette [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html).

Une fois une application mobile configurée, vous pouvez récupérer les données de PII qu&#39;elle a collectées pour créer ou mettre à jour des profils à partir de votre base de données. Pour plus d&#39;informations à ce sujet, reportez-vous à cette section : [Création et mise à jour des informations de profil en fonction des données d&#39;application mobile](../../channels/using/updating-profile-with-mobile-app-data.md).

Pour en savoir plus sur les différents cas pratiques mobiles pris en charge dans Adobe Campaign Standard grâce à l&#39;utilisation des SDK Adobe Experience Platform SDK, consultez cette [page](https://helpx.adobe.com/fr/campaign/kb/configure-launch-rules-acs-use-cases.html).

Pour terminer la configuration, procédez comme suit :

1. En Adobe Campaign, assurez-vous que vous pouvez accéder aux éléments suivants :
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL Message In-App]**
   * **[!UICONTROL Adobe Places]**
   Si ce n&#39;est pas le cas, contactez l&#39;équipe chargée de votre compte.

1. Vérifiez que votre utilisateur dispose des autorisations nécessaires dans Adobe Campaign Standard et Experience Platform Launch.
   * Dans Adobe Campaign Standard, assurez-vous que l’utilisateur IMS fait partie des Profils utilisateur et administrateur standard. Cette étape permet à l’utilisateur de se connecter à Adobe Campaign Standard, d’accéder à la page de l’application mobile SDK Experience Platform et de vue des propriétés de l’application mobile que vous avez créées dans le lancement de la plate-forme d’expérience.

   * Dans le lancement de la plate-forme d’expérience, assurez-vous que votre utilisateur IMS fait partie d’un profil de produits de lancement de la plate-forme d’expérience.
Cette étape permet à l’utilisateur de se connecter au lancement de la plate-forme d’expérience pour créer et vue les propriétés. Pour plus d’informations sur les profils de produits dans le lancement de la plateforme d’expérience, voir Création de votre profil de produits. Dans le profil du produit, aucune autorisation ne doit être définie sur la société ou les propriétés, mais l’utilisateur doit être en mesure de se connecter.
   Pour exécuter d’autres tâches, telles que l’installation d’une extension, la publication d’une application, la configuration d’environnements, etc., vous devez définir des autorisations dans le profil de produits.

1. Dans le lancement de la plate-forme d’expérience, créez une propriété **** Mobile. Pour plus d’informations, voir [Configuration d’une propriété](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)mobile.

1. Dans le lancement de la plate-forme d’expérience, cliquez sur l’onglet **[!UICONTROL Extensions]** , accédez au **[!UICONTROL catalogue]** et recherchez l’extension **[!UICONTROL Adobe Campaign Standard]** . Pour plus d’informations, voir [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Pour prendre en charge les cas d’utilisation des emplacements dans Campaign Standard, installez l’extension **[!UICONTROL Places]** et l’extension **[!UICONTROL Places Monitor]** .
   * Installez l’extension **[!UICONTROL Places]** dans le lancement de la plate-forme d’expérience. Consultez à ce sujet cette [page](https://docs.adobe.com/content/help/fr-FR/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installez l’extension **[!UICONTROL Places Monitor]** dans le lancement de la plate-forme d’expérience. Consultez à ce sujet cette [page](https://docs.adobe.com/content/help/fr-FR/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. Dans Adobe Campaign Standard, configurez la propriété mobile que vous avez créée dans le lancement de la plate-forme d’expérience. Reportez-vous à [Configuration de votre application de lancement Adobe Experience Platform en Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Ajouter la configuration spécifique au canal à votre configuration d’application mobile.
Pour plus d’informations, voir Configuration d’applications spécifiques à un [Canal dans Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Si nécessaire, vous pouvez supprimer votre propriété de lancement de plate-forme d’expérience.
Pour plus d’informations, voir [Suppression de votre application](../../administration/using/configuring-a-mobile-application.md#delete-app)de lancement de plateforme d’expérience.

## Synchronisation de l’application mobile AEPSDK à partir du processus technique de lancement {#aepsdk-workflow}

>[!IMPORTANT]
>
>Cette fonctionnalité est une fonctionnalité bêta en Adobe Campaign à compter de la version 20.3. Vous devrez envoyer un ticket au service à la clientèle d’Adobe (directement ou par l’intermédiaire de votre contact Adobe) pour que l’application mobile **[!UICONTROL synchronisée AEPSDK à partir du processus technique de lancement]** soit activée dans votre instance Adobe Campaign.

Après avoir créé et configuré votre propriété mobile dans le lancement de la plate-forme d’expérience, l’application mobile **[!UICONTROL Sync AEPSDK du processus technique de lancement]** synchronise désormais les propriétés mobiles Adobe Launch importées dans Adobe Campaign Standard.

Par défaut, le flux de travail technique est début toutes les 15 minutes. Si nécessaire, il peut être redémarré manuellement :

1. Dans Adobe Campaign Standard, dans le menu avancé, sélectionnez **[!UICONTROL Administration]** > Paramètres **[!UICONTROL de l’]** application > **[!UICONTROL Workflows]**.
1. Ouvrez l’application **[!UICONTROL Sync Mobile AEPSDK à partir du processus Launch (syncWithLaunch)]** .

   ![](assets/launch_10.png)

1. Cliquez sur l&#39;activité **[!UICONTROL Planificateur]** .

1. Sélectionnez Exécution **** immédiate.

   ![](assets/launch_11.png)

Votre flux de travail va maintenant redémarrer et synchroniser les propriétés d’Adobe Launch mobile importées dans Adobe Campaign Standard.

## Setting up your Adobe Experience Platform Launch application in Adobe Campaign {#set-up-campaign}

Pour utiliser une propriété mobile Experience Platform Launch dans Campaign, vous devez également configurer cette propriété dans Adobe Campaign. En Adobe Campaign, assurez-vous que l’utilisateur IMS fait partie des Profils utilisateur et administrateur standard.

Pour les utilisateurs pour lesquels l’indicateur de fonctionnalité Synchroniser l’application mobile AEPSDK à partir du lancement du processus technique est activé, vous devez attendre que le processus technique s’exécute et synchronise la propriété Launch mobile sur Adobe Campaign. Vous pouvez ensuite le configurer dans Adobe Campaign.

Pour plus d&#39;informations sur l&#39;indicateur de fonctionnalité de processus technique de lancement de l&#39;application mobile Sync AEPSDK, reportez-vous à cette [section](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Par défaut, les administrateurs dont l’unité d’organisation est définie sur ALL peuvent modifier l’application mobile.

1. From the advanced menu, select **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Sélectionnez l’application mobile que vous avez créée dans le lancement de la plate-forme d’expérience.
Son **[!UICONTROL Property Status]** doit être **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Par défaut, pour récupérer la liste des applications mobiles créées dans Adobe Launch, Campaign Standard utilise la valeur définie dans l’option NmsServer_URL pour rechercher les propriétés correspondantes.
Dans certains cas, le point de terminaison Campaign pour une application mobile peut être différent de celui défini dans NmsServer_URL. Dans ce cas, définissez le point de terminaison dans l’option Launch_URL_Campaign. Campaign utilisera la valeur de cette option pour rechercher les propriétés correspondantes dans Adobe Launch.

   ![](assets/launch_4.png)

1. Vous pouvez modifier l&#39;unité d&#39;organisation de votre application mobile sous la section Autorisation **[!UICONTROL d&#39;]** accès afin de limiter l&#39;accès à cette application mobile à des unités d&#39;organisation spécifiques. Pour plus d&#39;informations, consultez cette page.

   Ici, l&#39;administrateur peut affecter des unités d&#39;organisation en les sélectionnant dans la liste déroulante.

   ![](assets/launch_12.png)

1. To make the connection between Campaign and Experience Platform Launch, click **[!UICONTROL Save]**.

1. Vérifiez que l’état de l’application mobile est passé de **[!UICONTROL Prêt à Configurer]** à **[!UICONTROL Configuré]**.

   Lorsque l’extension Campaign de lancement de plateforme d’expérience indique que la clé a bien été configurée, vous pouvez également vérifier que la propriété a bien été configurée dans Campaign.

   ![](assets/launch_5.png)

1. Pour que cette configuration prenne effet, les modifications doivent être publiées dans le lancement de la plate-forme d’expérience.

   Pour plus d’informations, voir Configuration [de](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)publication.

## Configuration d&#39;applications spécifiques au Canal dans Adobe Campaign {#channel-specific-config}

Votre application mobile est maintenant prête à être utilisée dans Campaign pour les notifications push ou les diffusions in-app. Vous pouvez à présent la configurer davantage pour créer des événements qui déclencheront vos messages in-app et/ou téléchargeront les certificats push.

1. From the advanced menu, select **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Sélectionnez l’application mobile que vous avez créée et configurée dans le lancement d’Experience Platform.

1. On the **[!UICONTROL Mobile application properties]** tab, you can start adding events that are available in your mobile application for your in-app messages.

1. Pour configurer vos événements, cliquez sur **[!UICONTROL Créer un élément]**.

   ![](assets/launch_6.png)

1. Entrez un nom et une description.

   ![](assets/launch_7.png)

1. Cliquez sur **[!UICONTROL Ajouter]**.

   Votre événement est désormais disponible dans l’onglet Déclencheurs lorsque vous créez un message in-app. Pour plus d’informations, voir [Préparation et envoi d’un message](../../channels/using/preparing-and-sending-an-in-app-message.md)intégré à l’application.

1. Dans la section **[!UICONTROL Paramètres spécifiques à l&#39;appareil]** du tableau de bord d&#39;une application mobile, pour chaque type d&#39;appareil, fournissez les détails de l&#39;application, y compris le certificat pour iOS et la clé du serveur pour Android.

   Une fois le certificat téléchargé, un message vous informe que le téléchargement a réussi et indique la date d’expiration de votre certificat.

   >[!NOTE]
   >
   >Après avoir ajouté le certificat dans Adobe Campaign Standard, vous ne pourrez plus modifier vos paramètres à nouveau, car une seule plate-forme APNS (production ou sandbox) peut être ajoutée à l’application MCPNS.

   ![](assets/launch_8.png)

1. Cliquez sur l’onglet Abonnés **[!UICONTROL des applications]** mobiles pour afficher une liste d’abonnés et d’autres informations sur ces abonnés, par exemple s’ils ont choisi de ne pas recevoir vos notifications.

## Suppression de votre application de lancement d’Adobe Experience Platform {#delete-app}

La suppression de votre application de lancement de plateforme d’expérience ne peut pas être annulée.

>[!CAUTION]
>
>La suppression de votre application de lancement de plateforme d’expérience ne peut pas être annulée.

Pour supprimer votre application de lancement de plateforme d’expérience, suivez la procédure décrite dans [Suppression des propriétés](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)mobiles.

Une fois l’application supprimée, vérifiez en Adobe Campaign si l’état des propriétés de l’application a été correctement mis à jour sur Supprimé au lancement.

En cliquant sur votre application en Adobe Campaign, vous pouvez choisir de supprimer complètement cette application de Adobe Campaign en cliquant sur Supprimer de Campaign.

    ![](assets/launch_9.png)
