---
solution: Campaign Standard
product: campaign
title: Configurer l'intégration Campaign-Données de points ciblés
description: Découvrez comment configurer la fonctionnalité des données de points ciblés dans Adobe Campaign pour envoyer des messages personnalisés en fonction de la localisation de vos abonnés.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: 'Audiences '
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1452'
ht-degree: 99%

---


# Configurer l&#39;intégration Campaign-Données de points ciblés{#configuring-campaign-points-of-interest-data-integration}

## Configuration de l&#39;intégration Campaign-Données de points ciblés avec les SDK Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Votre application mobile doit déjà être configurée dans Adobe Campaign Standard à l&#39;aide du SDK Adobe Experience Platform. Pour obtenir les étapes détaillées, reportez-vous à cette [page](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html).

Les applications mobiles utilisées pour collecter les données de localisation doivent être configurées par un **administrateur** dans l&#39;interface d&#39;Adobe Campaign.

Pour pouvoir utiliser Adobe Experience Platform Location Services avec les applications mobiles configurées à l&#39;aide du SDK Adobe Experience Platform, vous devez :

1. Ajouter les extensions **[!UICONTROL Places]** et **[!UICONTROL Places Monitor]** à votre configuration d&#39;application mobile dans Adobe Experience Platform Launch. Configurer votre application mobile dans Adobe Campaign. Voir [Installation de l&#39;extension Places dans Adobe Experience Platform Launch](https://docs.adobe.com/content/help/fr-FR/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) et [Installation de l&#39;extension Places Monitor dans Experience Platform Launch](https://docs.adobe.com/content/help/fr-FR/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch).

1. Une fois les extensions configurées, créez des éléments de données dans **[!UICONTROL Adobe Experience Platform Launch]** pour récupérer des données de ces extensions. Reportez-vous à cette [page](https://helpx.adobe.com/fr/campaign/kb/config-app-in-launch.html#Step1Createdataelements) pour créer vos éléments de données.

1. Ensuite, dans **[!UICONTROL Adobe Experience Platform Launch]**, vous devez créer des règles pour prendre en charge les cas pratiques mobiles entre Point ciblé et Adobe Campaign.\
   Cette règle sera déclenchée lorsqu&#39;un utilisateur entre dans un **[!UICONTROL Point ciblé]** repéré géographiquement. Reportez-vous à cette [page](https://helpx.adobe.com/fr/campaign/kb/config-app-in-launch.html#Locationpostback) pour créer votre règle.

1. Définissez vos **[!UICONTROL Points ciblés]** dans Places. Voir [Création d&#39;un point ciblé](https://docs.adobe.com/content/help/fr-FR/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. Vérifier que vous avez accès à l&#39;application mobile et aux données de localisation collectées dans Adobe Campaign. Voir [Accéder aux applications mobiles utilisées pour collecter les données de localisation](#accessing-mobile-apps-used-to-collect-location-data) et [Accéder aux données de localisation collectées](#accessing-collected-location-data).

## Configuration de l&#39;intégration Campaign-Données de points ciblés avec le SDK V4 {#configuring-campaign-poi-sdkv4}

Les applications mobiles utilisées pour collecter les données de localisation doivent être configurées par un **administrateur** dans l&#39;interface d&#39;Adobe Campaign.

Pour utiliser la fonctionnalité de données Point ciblé avec des applications mobiles configurées à l&#39;aide du SDK V4, vous devez :

1. Pouvoir accéder à Adobe Analytics pour Mobile. Vérifier votre contrat de licence ou contacter votre chargé de compte Adobe pour plus d&#39;informations.
1. Configurer votre application mobile dans Adobe Campaign. Voir [Configurer une application mobile dans Campaign](#setting-up-a-mobile-app-in-campaign).
1. Configurer votre application mobile dans l&#39;interface Adobe Mobile Services. Vous pouvez ainsi vous assurer que les données collectées par Adobe Mobile Services sont envoyées à Adobe Campaign. Voir [Configurer une application mobile dans Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Effectuer la configuration spécifique de l’application mobile :

   * Intégrez le fichier de configuration téléchargé à partir de l’interface Adobe Mobile Services avec l’application mobile.
   * Intégrez le SDK d’Experience Cloud Mobile dans votre application mobile. Voir [Intégrer le SDK dans une application mobile](#integrating-the-sdk-into-a-mobile-application).

1. Définir les points ciblés dans l&#39;interface Adobe Mobile Services. Voir [Définir les points ciblés dans Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Définir les données à collecter auprès des abonnés de votre application mobile. Voir [Collecter les données de points ciblés auprès des abonnés](#collecting-subscribers--points-of-interest-data).
1. Vérifier que vous avez accès à l&#39;application mobile et aux données de localisation collectées dans Adobe Campaign. Voir [Accéder aux applications mobiles utilisées pour collecter les données de localisation](#accessing-mobile-apps-used-to-collect-location-data) et [Accéder aux données de localisation collectées](#accessing-collected-location-data).

### Configuration d&#39;une application mobile dans Adobe Campaign à l&#39;aide du SDK V 4 {#setting-up-a-mobile-app-in-campaign}

Pour pouvoir collecter des données de points ciblés avec Adobe Campaign, vous devez configurer l&#39;application mobile à partir de laquelle Adobe Campaign recevra les données.

1. Cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Application mobile]**.
1. Cliquez sur **[!UICONTROL Créer]** pour configurer une application.
1. Saisissez un nom dans le champ **[!UICONTROL Nom de l&#39;application]** et cliquez sur **[!UICONTROL Créer]**.

   Ne remplissez pas la section **[!UICONTROL Paramètres spécifiques à l&#39;appareil]**, qui concerne uniquement le paramétrage des applications destinées à recevoir des notifications push.

Dans la section **[!UICONTROL Propriétés de l&#39;application mobile]**, deux URL sont répertoriées : **[!UICONTROL Point d&#39;entrée pour la collecte des PII]** et **[!UICONTROL Point d&#39;entrée des services de localisation]**. Elles seront utilisées dans l&#39;interface Adobe Mobile Services. Voir [Configurer une application mobile dans Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* L&#39;URL **[!UICONTROL Point d&#39;entrée pour la collecte des PII]** sert à collecter les jetons d&#39;enregistrement et les identifiants Experience Cloud des utilisateurs à partir de l&#39;application mobile lors de son lancement. Lorsqu&#39;un utilisateur se connecte à l&#39;application à l&#39;aide d&#39;identifiants comme l&#39;adresse électronique, le prénom et le nom, ces données sont également utilisées pour réconcilier le jeton d&#39;enregistrement de l&#39;utilisateur avec un profil Adobe Campaign.
* L&#39;URL **[!UICONTROL Point d&#39;entrée des services de localisation]** sert à collecter les données de localisation telles que la latitude, la longitude et le rayon d&#39;un point ciblé d&#39;un utilisateur.

Vous pouvez maintenant utiliser ces valeurs dans Adobe Mobile Services pour terminer la configuration, comme expliqué dans la section [Configurer une application mobile dans Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

![](assets/poi_mobile_app_properties.png)

### Configurer une application mobile dans Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Pour envoyer les données collectées par Adobe Mobile Services vers Adobe Campaign, vous devez configurer des postbacks dans l&#39;interface Mobile Services.

Vous aurez besoin d&#39;informations spécifiques accessibles dans les paramètres de l&#39;application mobile définis dans Adobe Campaign (voir [Configurer une application mobile dans Campaign](#setting-up-a-mobile-app-in-campaign)) :

* **[!UICONTROL Identifiant IMS de l&#39;organisation]**
* **[!UICONTROL Point d&#39;entrée pour la collecte des PII]**
* **[!UICONTROL Point d&#39;entrée des services de localisation]**

Vous devez avoir accès à Adobe Analytics pour effectuer la configuration ci-après. Si vous n&#39;êtes pas un utilisateur d&#39;Adobe Analytics, contactez votre administrateur Adobe Campaign.

1. Connectez-vous à [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Créez l&#39;application ou sélectionnez une application existante.
1. Accédez à la page **[!UICONTROL Gérer les paramètres d&#39;application]**.
1. Dans la section **Service d&#39;ID de visiteur**, cochez l&#39;option **Activer** et sélectionnez votre organisation dans la liste déroulante. Cliquez sur **Enregistrer**.

   >[!CAUTION]
   >
   >Cette organisation doit être la même que celle utilisée sur l&#39;instance Adobe Campaign.

1. Cliquez sur **[!UICONTROL Gérer les postbacks]**.
1. Créez un postback.

   * Sélectionnez **[!UICONTROL PII]** comme **[!UICONTROL Type de postback]**.
   * Dans le champ **[!UICONTROL URL]**, copiez l&#39;URL **[!UICONTROL Point d&#39;entrée pour la collecte des PII]** à partir de l&#39;application mobile que vous avez configurée dans l&#39;interface Adobe Campaign, précédée du nom du serveur. Voir [Configurer une application mobile dans Campaign](#setting-up-a-mobile-app-in-campaign).
   * Renseignez le champ **[!UICONTROL Corps de publication]** comme suit :

      Pour iOS:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      Pour Android :

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * Définissez **Type de contenu** sur **[!UICONTROL application/json]**.
   * Dans la section **Quelles balises de données déclenchent le postback ?**, sélectionnez n&#39;importe quel événement, généralement **[!UICONTROL Lancé]** et **[!UICONTROL existe]**.
   * Cliquez sur **[!UICONTROL Enregistrer et activer]**.

1. Créez un deuxième postback.

   * Sélectionnez **[!UICONTROL Postback]** comme **[!UICONTROL Type de postback]**.
   * Dans le champ **[!UICONTROL URL]**, copiez l&#39;URL **[!UICONTROL Point d&#39;entrée des services de localisation]** à partir de l&#39;application mobile que vous avez configurée dans l&#39;interface Adobe Campaign, précédée du nom du serveur. Voir [Configurer une application mobile dans Campaign](#setting-up-a-mobile-app-in-campaign).
   * Renseignez le champ **[!UICONTROL Corps de publication]** comme suit :

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * Définissez **Type de contenu** sur **[!UICONTROL application/json]**.
   * Dans la section **Quelles balises de données déclenchent le postback ?**, sélectionnez **[!UICONTROL campaign.test]** et **[!UICONTROL existe]**.
   * Cliquez sur **[!UICONTROL Enregistrer et activer]**.

>[!NOTE]
>
>Pour obtenir des informations détaillées sur la configuration des postbacks, voir la [Documentation Adobe Mobile Services](https://docs.adobe.com/content/help/fr-FR/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html).

### Intégrer le SDK dans une application mobile {#integrating-the-sdk-into-a-mobile-application}

Le kit de développement logiciel (SDK) de Mobile Services facilite l&#39;intégration d&#39;une application mobile dans Adobe Campaign.

Cette étape est décrite dans cette [page](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html).

### Définir les points ciblés dans Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Pour définir les points ciblés servant à collecter les données de localisation :

1. Connectez-vous à l&#39;interface Adobe Mobile Services.
1. Ajoutez votre application.

   Pour plus d&#39;informations sur la gestion des applications dans Mobile Services, voir la [Documentation Adobe Mobile Services](https://docs.adobe.com/content/help/fr-FR/mobile-services/using/manage-apps-ug/t-new-app.html).

1. Définissez les points ciblés.

   Pour plus d&#39;informations sur la gestion des points ciblés, voir la [Documentation Adobe Mobile Services](https://docs.adobe.com/content/help/fr-FR/mobile-services/using/location-ug/t-manage-points.html).

### Collecter les données de points ciblés auprès des abonnés {#collecting-subscribers--points-of-interest-data}

Une ressource personnalisée spécifique vous permet de définir les données à collecter auprès des abonnés de vos applications.

Cette étape est présentée dans la page [Configuration d&#39;une application mobile à l&#39;aide du SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).


## Accéder aux applications mobiles utilisées pour collecter les données de localisation {#accessing-mobile-apps-used-to-collect-location-data}

Pour accéder aux applications créées dans Adobe Campaign :

1. Cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche.
1. Sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Application mobile (SDK v4)]** ou **[!UICONTROL Application mobile (SDK AEP)]** selon le SDK.
1. Dans la liste, sélectionnez une application mobile pour afficher ses propriétés.

   ![](assets/poi_mobile_app_subscribers.png)

Une liste des abonnés de l&#39;application est également affichée dans l&#39;onglet **[!UICONTROL Abonnés à l&#39;application mobile]**. Les abonnés correspondent à tous les utilisateurs qui ont installé l&#39;application sur leur appareil mobile. Les profils de la base de données Adobe Campaign sont identifiés par un jeton d&#39;enregistrement.

## Accéder aux données de localisation collectées     {#accessing-collected-location-data}

Une fois la configuration terminée, les données de points ciblés collectées sont répertoriées dans l&#39;onglet **[!UICONTROL Lieux]** de chaque profil. Pour accéder à la liste :

1. Sélectionnez un profil.
1. Cliquez sur le bouton **[!UICONTROL Editer les propriétés du profil]** à droite.
1. Sélectionnez l&#39;onglet **[!UICONTROL Lieux]**.

   ![](assets/poi_profile_places.png)

La liste des données de points ciblés collectées pour le profil en cours s&#39;affiche. Les informations de localisation sont conservées dans la base de données Adobe Campaign pendant six mois.

Pour plus d&#39;informations sur l&#39;accès aux profils et leur édition, voir la section [Profils](../../audiences/using/about-profiles.md).
