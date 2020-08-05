---
title: Configuration des règles Adobe Experience Platform Launch pour la prise en charge des cas d’utilisation Adobe Campaign Standard
description: Configuration des règles Adobe Experience Platform Launch pour la prise en charge des cas d’utilisation Adobe Campaign Standard
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
source-git-commit: 2b8a25a90ea253666fb71c3f7aaf830d736e6c5b
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 9%

---


# Configuration des règles de lancement pour la prise en charge des cas d’utilisation Adobe Campaign Standard {#configuring-rules-launch}

In [!DNL Adobe Experience Platform Launch], you need to create data elements and rules to send PII and other data from mobile applications to [!DNL Adobe Campaign Standard].

Pour que toutes les modifications apportées à la configuration [!DNL Adobe Experience Platform Launch] prennent effet, vous devez les publier. Pour plus d’informations, voir [Publication](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Pour créer des règles dans [!DNL Experience Platform Launch], procédez comme suit :

1. [Création d’éléments de données](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Création de règles](../../administration/using/configuring-rules-launch.md#create-data-elements) pour les cas d’utilisation que vous souhaitez prendre en charge :
   * [Postback sur les informations d’identification personnelle](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback de suivi in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Notifications Push suivi postback](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Publication de l’emplacement](../../administration/using/configuring-rules-launch.md#location-postback)

## Création d’éléments de données {#create-data-elements}

Voici les éléments de données que nous vous recommandons de créer dans [!DNL Experience Platform Launch].
Vous pouvez créer des éléments de données supplémentaires en fonction de vos besoins.

* **[!UICONTROL Identifiant Experience Cloud]**
* **[!UICONTROL Clé]**
* **[!UICONTROL Serveur Campaign]**

Pour créer ces éléments de données, procédez comme suit :

1. Dans [!DNL Experience Platform Launch]le tableau de bord de votre application mobile, cliquez sur l’onglet Eléments **[!UICONTROL de]** données.

1. Pour créer l’élément de données ID **[!UICONTROL d’]** Experience Cloud, cliquez sur **[!UICONTROL Créer un élément]** de données.

1. In the **[!UICONTROL Name]** field, for example, type in **mcid**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Puis, ID **** d’Experience Cloud dans la liste déroulante de type d’élément **** Data.

   ![](assets/rules_1.png)

1. Pour créer l’élément de données Clé, cliquez sur **[!UICONTROL Ajouter l’élément]** de données.

1. Dans le champ **[!UICONTROL Name]**, saisissez par exemple **pkey**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Ensuite, **[!UICONTROL appuyez sur]** la touche dans la liste déroulante de type d’élément **** de données.

1. Pour créer l’élément de données du serveur Campaign, cliquez sur **[!UICONTROL Ajouter l’élément]** de données.

1. Dans le champ **[!UICONTROL Nom]** , saisissez un nom, par exemple, **camp-server**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Ensuite, **[!UICONTROL Campaign Server]** dans la liste déroulante de type d’élément **** Data.

## Création de règles {#creating-rules}

Vous devez créer des règles pour les éléments suivants :

* [Postback sur les informations d’identification personnelle](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback de suivi in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Notifications Push suivi postback](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Publication de l’emplacement](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback sur les informations d’identification personnelle {#pii-postback}

>[!NOTE]
>
>Pour envoyer des informations d’identification personnelle d’une application mobile à Adobe Campaign, vous devez mettre en oeuvre une API SDK. Pour plus d’informations, consultez [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Pour envoyer des données d’identification personnelle à [!DNL Adobe Campaign Standard], créez une règle dans [!DNL Experience Platform Launch]:

1. Dans [!DNL Experience Platform Launch]le tableau de bord de votre application mobile, cliquez sur l’onglet **[!UICONTROL Règles]** , puis **[!UICONTROL Créer une règle]**.

1. Saisissez un nom, par exemple, **Mobile Core - Collect PII**.

1. Dans la section **[!UICONTROL Événements]** , cliquez sur **[!UICONTROL Ajouter]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, **[!UICONTROL Collectez les informations d’identification personnelle]** dans la liste déroulante **[!UICONTROL Type d&#39;événement]** .

1. Cliquez sur **[!UICONTROL Conserver les modifications]**.

1. Dans la section **[!UICONTROL Actions]** , cliquez sur **[!UICONTROL Ajouter]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, **[!UICONTROL envoyez les informations d’identification personnelle]** dans la liste déroulante Type **[!UICONTROL d’]** action.

1. Dans **[!UICONTROL l’URL]**, saisissez l’URL suivante :

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Cochez la case **[!UICONTROL Ajouter le corps]** de la publication.

1. Dans Corps **[!UICONTROL de la]** publication, saisissez ce qui suit :

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   Le paramètre marketingCloudId vous permet de concilier vos abonnés d’application avec les destinataires de la base de données et, par conséquent, il est nécessaire. Vous pouvez spécifier d’autres paires clé-valeur en fonction des besoins de votre entreprise. Dans l’exemple ci-dessus, Courriel, Prénom et Nom sont transmis à partir de l’application.

   Les clés (par exemple cusEmail, cusFirstName et cusLastName) doivent correspondre aux ID de champ définis dans votre ressource personnalisée dans l’instance Adobe Campaign Standard. Les variables de valeur (par exemple, email, firstName et LastName) doivent correspondre aux clés des données JSON envoyées à partir de l’application mobile lors de l’appel de l’API de collecte d’informations sur les adresses IP AMS à partir du code de l’application.

   Vous pouvez également transmettre des données de cycle de vie dans le postback Collecter les informations d’identification personnelle ou dans un postback différent selon vos déclencheurs de Événement. voici un exemple des données de cycle de vie JSON :

       &quot;
 {     
 &quot;marketingCloudId&quot;:&quot;{%%mcid%%}&quot;,     
     &quot;cusDayslastlaunch&quot;: &quot;{%%DaysSinceLastUse%}&quot;,
     &quot;cusDaysfirstlaunch&quot; : &quot;{%%DaysSinceFirstUse%}&quot;,
     &quot;cusLaunches&quot; : &quot;{%%Launches%}&quot;
     }
     &quot;
   
   Les éléments de données définis dans [!DNL Experience Platform Launch] doivent être inclus dans des pourcentages de doublon, par exemple %%mcid%%, et les variables contextuelles de l&#39;application doivent être incluses dans des pourcentages uniques, par exemple %contextdata.email%.

1. Dans **[!UICONTROL Type de contenu]**, saisissez **application/json**.

1. Dans **[!UICONTROL Délai d’expiration]**, sélectionnez 0.

   ![](assets/rules_2.png)

Vos données utilisateur sont maintenant configurées pour être envoyées à Campaign.

### Postback de suivi in-app {#inapp-tracking-postback}

Pour envoyer des données de suivi au rapports [!DNL Adobe Campaign Standard] de la manière dont vos utilisateurs interagissent avec les messages In-App dans votre application mobile, créez la règle suivante dans [!DNL Experience Platform Launch]:

1. Dans [!DNL Experience Platform Launch]le tableau de bord de votre application mobile, sélectionnez l’onglet **[!UICONTROL Règles]** et cliquez sur **[!UICONTROL Ajouter une règle]**.

1. Saisissez un nom, par exemple, **Adobe Campaign - Suivi** des clics in-app.

1. Dans la section **[!UICONTROL Événements]** , cliquez sur **[!UICONTROL Ajouter]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Ensuite, le suivi **[!UICONTROL des clics]** in-app est activé dans la liste déroulante des **** Types d&#39;événement.

1. Cliquez sur **[!UICONTROL Conserver les modifications]**.

1. Dans la section **[!UICONTROL Actions]** , cliquez sur **[!UICONTROL Ajouter]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, **[!UICONTROL envoyez un postback]** dans la liste déroulante **[!UICONTROL Type d&#39;événement]** .

1. Dans **[!UICONTROL l’URL]**, saisissez l’URL suivante :

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Cochez la case **[!UICONTROL Ajouter le corps]** de la publication.

1. Dans Corps **** de la publication, tapez **{}**.

1. Dans **[!UICONTROL Type de contenu]**, saisissez **application/json**.

1. Dans **[!UICONTROL Délai d’expiration]**, sélectionnez 0.

   ![](assets/rules_3.png)

### Notifications Push suivi postback {#push-tracking-postback}

To send tracking data to [!DNL Adobe Campaign Standard], which helps track your Push notification deliveries and your users’ interaction with your mobile application, you need to create a rule in [!DNL Experience Platform Launch].

Pour plus d’informations sur le suivi Push, voir Suivi [](../../administration/using/push-tracking.md)Push.

Pour effectuer le suivi des actions de l’application, utilisez l’API trackAction. Pour plus d’informations, voir [Suivi des actions](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)de l’application.

1. Dans [!DNL Experience Platform Launch]le tableau de bord de votre application mobile, cliquez sur l’onglet **[!UICONTROL Règles]** , puis sur **[!UICONTROL Ajouter une règle]**.

1. Saisissez un nom, par exemple, **Adobe Campaign - Suivi des** clics push.

1. Dans la section **[!UICONTROL Événements]** , cliquez sur **[!UICONTROL Ajouter]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, **[!UICONTROL effectuez le suivi des actions]** dans la liste déroulante **[!UICONTROL Type d&#39;événement]** .

1. Dans la liste déroulante **[!UICONTROL Action]** , sélectionnez **[!UICONTROL Action]**, sélectionnez **[!UICONTROL est égal]** et tapez **suivi.**

1. Cliquez sur **[!UICONTROL Conserver les modifications]**. Ensuite, dans la section **[!UICONTROL Actions]** , cliquez sur **[!UICONTROL Ajouter]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, **[!UICONTROL Envoyez un postback]** dans la liste déroulante Type **[!UICONTROL d’]** action.

1. Dans **[!UICONTROL l’URL]**, saisissez l’URL suivante :

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Cochez la case **[!UICONTROL Ajouter le corps]** de la publication.

1. Ajoutez votre corps de publication, par exemple, { }.

1. Dans **[!UICONTROL Type de contenu]**, saisissez **application/json**.

1. Dans **[!UICONTROL Délai d’expiration]**, sélectionnez 0.

### Publication de l’emplacement {#location-postback}

1. Dans [!DNL Experience Platform Launch]le tableau de bord de votre application mobile, cliquez sur l’onglet **[!UICONTROL Règles]** , puis sur **[!UICONTROL Ajouter une règle]**.

1. Entrez un nom, par exemple, **Emplacement postback**.

1. Dans la section **[!UICONTROL Événements]** , cliquez sur **[!UICONTROL Ajouter]**.

1. Créez un événement, par exemple, Saisissez un point d’accès (POI) ou Quitter un point d’accès (POI). Dans la liste déroulante **[!UICONTROL Extension]** , sélectionnez **Places - Bêta**. Ensuite, **saisissez le point d’accès** ou de **sortie du point d’accès** dans la liste déroulante **[!UICONTROL Type d&#39;événement]** .

1. Entrez un nom, par exemple, **Places - Bêta - Entrez un point d’intérêt** ou un point de **sortie**.

1. Dans la section **[!UICONTROL Actions]** , cliquez sur **[!UICONTROL Ajouter]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, **[!UICONTROL Envoyez un postback]** à partir de la liste déroulante Type **[!UICONTROL d’]** action.

1. Saisissez un nom, par exemple, **Mobile Core - Envoyer le postback** de l’emplacement.

1. Dans **[!UICONTROL l’URL]**, saisissez l’URL suivante :

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Cochez la case **[!UICONTROL Ajouter le corps]** de la publication et ajoutez votre corps de publication, par exemple :

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >Dans l’exemple ci-dessus, les éléments de données du côté droit doivent être configurés dans [!DNL Experience Platform Launch] en suivant les étapes de la section [Création d’éléments](../../administration/using/configuring-rules-launch.md#create-data-elements)de données. Les éléments de données sur le côté gauche sont pris en charge dans [!DNL Adobe Campaign Standard] et n’ont pas besoin de configuration. Si vous avez besoin de données supplémentaires, vous devez exécuter des extensions de ressources personnalisées dans [!DNL Adobe Campaign Standard].

1. Dans **[!UICONTROL Type de contenu]**, saisissez **application/json**.

1. Dans **[!UICONTROL Délai d’expiration]**, sélectionnez 5.

   ![](assets/rules_4.png)
