---
solution: Campaign Standard
product: campaign
title: Configuration d'une application mobile
description: Découvrez comment configurer Adobe Campaign pour envoyer des notifications push ou des messages In-App à l’aide du SDK V4 ou du SDK Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Paramètres d’instance
role: Administrateur
level: Expérience
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 99%

---


# Configuration d&#39;une application mobile{#configuring-a-mobile-application}

## Configuration d’une application mobile à l’aide des SDK Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Les implémentations In-App et des notifications push doivent être effectuées par des utilisateurs expérimentés. Si vous avez besoin d&#39;aide, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels.

Pour envoyer des notifications push et des messages In-App avec l&#39;application SDK Experience Platform, une application mobile doit être créée dans Adobe Experience Platform Launch et configurée dans Adobe Campaign.

Pour plus d’informations sur la fonctionnalité obsolète SDK Mobile version 4, voir cette [page](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4-deprecated.html).

Une fois une application mobile configurée, vous pouvez récupérer les données de PII qu&#39;elle a collectées pour créer ou mettre à jour des profils à partir de votre base de données. Pour plus d&#39;informations à ce sujet, reportez-vous à cette section : [Création et mise à jour des informations de profil en fonction des données d&#39;application mobile](../../channels/using/updating-profile-with-mobile-app-data.md).

Pour en savoir plus sur les différents cas pratiques mobiles pris en charge dans Adobe Campaign Standard grâce à l&#39;utilisation des SDK Adobe Experience Platform SDK, consultez cette [page](https://helpx.adobe.com/fr/campaign/kb/configure-launch-rules-acs-use-cases.html).

Pour terminer la configuration, procédez comme suit :

1. Dans Adobe Campaign, assurez-vous que vous pouvez accéder aux éléments suivants :
   * **[!UICONTROL Notification push]**
   * **[!UICONTROL Message In-App]**
   * **[!UICONTROL Adobe Places]**

   Si ce n&#39;est pas le cas, contactez l&#39;équipe chargée de votre compte.

1. Vérifiez que votre utilisateur dispose des autorisations nécessaires dans Adobe Campaign Standard et Experience Platform Launch.
   * Dans Adobe Campaign Standard, assurez-vous que l’utilisateur IMS figure dans les profils de produit utilisateur et administrateur standard. Cette étape permet à l’utilisateur de se connecter à Adobe Campaign Standard, d’accéder à la page de l’application mobile SDK Experience Platform et d’afficher les propriétés de l’application mobile créée dans Experience Platform Launch.

   * Dans Experience Platform Launch, assurez-vous que votre utilisateur IMS fait partie d’un profil de produit Experience Platform Launch.
Cette étape permet à l’utilisateur de se connecter à Experience Platform Launch pour créer et afficher les propriétés. Pour plus d’informations sur les profils de produit d’Experience Platform Launch, voir la section Créer votre profil de produit. Dans le profil de produit, aucune autorisation ne doit être définie pour l’entreprise ou les propriétés, mais l’utilisateur doit être en mesure de se connecter.

   Pour exécuter d’autres tâches, comme installer une extension, publier une application, configurer des environnements, etc., vous devez définir des autorisations dans le profil de produit.

1. Dans Experience Platform Launch, créez une **[!UICONTROL propriété mobile]**. Pour plus d’informations, voir [Configuration d’une propriété mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. Dans Experience Platform Launch, cliquez sur l’onglet **[!UICONTROL Extensions]**, accédez au **[!UICONTROL catalogue]** et recherchez l’extension **[!UICONTROL Adobe Campaign Standard]**. Pour plus d’informations, voir la section [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Pour prendre en charge les cas pratiques des localisations dans Campaign Standard, installez les extensions **[!UICONTROL Places]** et **[!UICONTROL Places Monitor]**.
   * Installez l’extension **[!UICONTROL Places]** dans Experience Platform Launch. Consultez à ce sujet cette [page](https://docs.adobe.com/content/help/fr-FR/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installez l’extension **[!UICONTROL Places Monitor]** dans Experience Platform Launch. Consultez à ce sujet cette [page](https://docs.adobe.com/content/help/fr-FR/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. Dans Adobe Campaign Standard, configurez la propriété mobile que vous avez créée dans Experience Platform Launch. Voir la section [Configuration de l’application Adobe Experience Platform Launch dans Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Ajoutez la configuration spécifique au canal à votre configuration d’application mobile.
Pour plus d&#39;informations, reportez-vous à la section [Configuration de l&#39;application spécifique au canal dans Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Si nécessaire, vous pouvez supprimer la propriété Experience Platform Launch.
Pour plus d’informations, voir la section [Suppression de l’application Adobe Experience Platform Launch](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Workflow technique Synchronisation de l’application mobile AEPSDK depuis Launch {#aepsdk-workflow}

Après avoir créé et configuré votre propriété mobile dans Experience Platform Launch, le workflow technique **[!UICONTROL Synchronisation de l’application mobile AEPSDK depuis Launch]** synchronise les propriétés mobiles d’Adobe Launch importées dans Adobe Campaign Standard.

Par défaut, le workflow technique démarre toutes les 15 minutes. Si nécessaire, il est possible de le redémarrer manuellement :

1. Dans le menu avancé d’Adobe Campaign Standard, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l’application]** > **[!UICONTROL Workflows]**.
1. Ouvrez le workflow **[!UICONTROL Synchronisation de l’application mobile AEPSDK depuis Launch (syncWithLaunch)]**.

   ![](assets/launch_10.png)

1. Cliquez sur l’activité **[!UICONTROL Planificateur]**.

1. Sélectionnez **[!UICONTROL Traitement anticipé]**.

   ![](assets/launch_11.png)

Votre workflow va maintenant redémarrer et synchroniser les propriétés mobiles d’Adobe Launch importées dans Adobe Campaign Standard.

## Configuration de l’application Adobe Experience Platform Launch dans Adobe Campaign. {#set-up-campaign}

Pour utiliser une propriété mobile Experience Platform Launch dans Campaign, vous devez également configurer cette propriété dans Adobe Campaign. Dans Adobe Campaign, assurez-vous que l’utilisateur IMS figure dans les profils de produit utilisateur et administrateur standard.

Vous devrez attendre que le workflow technique s’exécute et synchronise la propriété mobile Launch sur Adobe Campaign. Vous pouvez ensuite la configurer dans Adobe Campaign.

Pour plus d’informations sur le wokflow technique de synchronisation de l’application mobile AEPSDK depuis Launch, voir cette [section](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Par défaut, les administrateurs dont l’entité organisationnelle est définie sur ALL peuvent modifier l’application mobile.

1. Dans le menu avancé, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Sélectionnez l’application mobile créée dans Experience Platform Launch.
Son **[!UICONTROL Property Status]** doit être **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Par défaut, pour récupérer la liste des applications mobiles créées dans Adobe Launch, Campaign Standard utilise la valeur définie dans l’option NmsServer_URL pour rechercher les propriétés correspondantes.
   >
   >Dans certains cas, le point d’entrée Campaign d’une application mobile peut être différent de celui défini dans NmsServer_URL. Dans ce cas, définissez le point d’entrée dans l’option Launch_URL_Campaign. Campaign utilisera la valeur de cette option pour rechercher les propriétés correspondantes dans Adobe Launch.

   ![](assets/launch_4.png)

1. Vous pouvez modifier l’entité organisationnelle de votre application mobile dans la section **[!UICONTROL Autorisation d’accès]** pour limiter l’accès à cette application mobile à des entités organisationnelles spécifiques. Pour plus d&#39;informations, consultez cette page.

   L’administrateur peut ainsi affecter des sous-entités organisationnelles en les sélectionnant dans la liste déroulante.

   ![](assets/launch_12.png)

1. Pour établir la connexion entre Campaign et Experience Platform Launch, cliquez sur **[!UICONTROL Enregistrer]**.

1. Vérifiez que l’état de l’application mobile est passé de **[!UICONTROL Ready to configure]** à **[!UICONTROL Configured]**.

   Lorsque l’extension Experience Platform Launch Campaign indique que la clé a été configurée avec succès, vous pouvez également vérifier que la propriété a été configurée avec succès dans Campaign.

   ![](assets/launch_5.png)

1. Pour que cette configuration soit prise en compte, les modifications doivent être publiées dans Experience Platform Launch.

   Pour plus d’informations, voir la section [Publier la configuration](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Configuration d’une application spécifique à un canal dans Adobe Campaign {#channel-specific-config}

Votre application mobile est maintenant prête à être utilisée dans Campaign pour les notifications push ou les diffusions In-App. Vous pouvez à présent la configurer davantage pour créer des événements qui déclencheront vos messages In-App et/ou téléchargeront les certificats push.

1. Dans le menu avancé, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Sélectionnez l’application mobile créée et configurée dans Experience Platform Launch.

1. Dans l’onglet **[!UICONTROL Propriétés de l’application mobile]**, vous pouvez commencer à ajouter les événements disponibles dans l’application mobile pour les messages In-App.

1. Pour configurer vos événements, cliquez sur **[!UICONTROL Créer un élément]**.

   ![](assets/launch_6.png)

1. Saisissez un nom et une description.

   ![](assets/launch_7.png)

1. Cliquez sur **[!UICONTROL Ajouter]**.

   Votre événement est maintenant disponible dans l’onglet Triggers lors de la création d’un message In-App. Pour plus d’informations, voir la section [Préparation et envoi d’un message In-App](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. Dans la section **[!UICONTROL Paramètres spécifiques à l&#39;appareil]** du tableau de bord d&#39;une application mobile, pour chaque type d&#39;appareil, fournissez les détails de l&#39;application, y compris le certificat pour iOS et la clé du serveur pour Android.

   Une fois le certificat transféré, un message vous informe que le transfert a réussi et indique la date d’expiration de votre certificat.

   >[!NOTE]
   >
   >Une fois le certificat ajouté dans Adobe Campaign Standard, vous ne pouvez plus restaurer vos paramètres dans la mesure où une seule plateforme APNS (production ou sandbox) peut être ajoutée à l’application MCPNS.

   ![](assets/launch_8.png)

1. Cliquez sur l’onglet **[!UICONTROL Abonnés à l’application mobile]** pour afficher une liste d’abonnés et d’autres informations les concernant, par exemple s’ils ont choisi de ne pas recevoir vos notifications.

## Suppression de l’application Adobe Experience Platform Launch {#delete-app}

La suppression de l’application Adobe Experience Platform Launch ne peut pas être annulée.

>[!CAUTION]
>
>La suppression de l’application Adobe Experience Platform Launch ne peut pas être annulée.

Pour supprimer l’application Experience Platform Launch, suivez la procédure décrite dans la section [Suppression des propriétés mobiles](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

Une fois l’application supprimée, vérifiez dans Adobe Campaign si l’état de la propriété de l’application a été correctement mis à jour à Deleted dans Launch.

En cliquant sur votre application dans Adobe Campaign, vous pouvez choisir de la supprimer complètement d’Adobe Campaign en cliquant sur Supprimer dans Campaign.

![](assets/launch_9.png)
