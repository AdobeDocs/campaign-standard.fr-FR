---
title: Configuration des règles de balises pour la prise en charge des cas pratiques Adobe Campaign Standard
description: Découvrez comment configurer des règles de balises pour prendre en charge les cas pratiques Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 73%

---

# Configuration des règles de balises pour la prise en charge des cas pratiques Adobe Campaign Standard {#configuring-rules-launch}

Dans l’interface utilisateur de collecte de données, créez des éléments de données et des règles pour envoyer les informations d’identification personnelles et d’autres données depuis les applications mobiles vers [!DNL Adobe Campaign Standard].

Pour que toutes les modifications de configuration de l’interface utilisateur de la collecte de données soient prises en compte, vous devez les publier. Pour plus d&#39;informations, voir la section [Publication](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Pour créer des règles dans l’interface utilisateur de la collecte de données, procédez comme suit :

1. [Création d&#39;éléments de données](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Création de règles](../../administration/using/configuring-rules-launch.md#create-data-elements) pour les cas pratiques que vous souhaitez prendre en charge :
   * [Postback des informations d&#39;identification personnelles](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback de tracking In-App](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback de tracking des notifications push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback de l&#39;emplacement](../../administration/using/configuring-rules-launch.md#location-postback)

## Création d&#39;éléments de données {#create-data-elements}

Voici les éléments de données que nous vous recommandons de créer dans l’interface utilisateur de collecte de données.
Vous pouvez créer des éléments de données supplémentaires en fonction de vos besoins.

* **[!UICONTROL Identifiant Experience Cloud]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Serveur Campaign]**

Pour créer ces éléments de données, procédez comme suit :

1. Dans l’interface utilisateur de la collecte de données, dans le tableau de bord de votre application mobile, cliquez sur le bouton **[!UICONTROL Éléments de données]** .

1. Pour créer l’élément de données **[!UICONTROL Identifiant Experience Cloud]**, cliquez sur **[!UICONTROL Create New Data Element]**.

1. Dans le champ **[!UICONTROL Name]**, saisissez par exemple **mcid**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Sélectionnez ensuite **[!UICONTROL Experience Cloud ID]** dans la liste déroulante de type **[!UICONTROL Data element]**.

   ![](assets/do-not-localize/rules_1.png)

1. Pour créer l&#39;élément de données Pkey, cliquez sur **[!UICONTROL Add data element]**.

1. Dans le champ **[!UICONTROL Name]**, saisissez par exemple **pkey**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Adobe Campaign Standard]**. Sélectionnez ensuite **[!UICONTROL pkey]** dans la liste déroulante de type **[!UICONTROL Data element]**.

1. Pour créer l&#39;élément de données Serveur Campaign, cliquez sur **[!UICONTROL Add data element]**.

1. Dans le champ **[!UICONTROL Name]**, saisissez un nom, par exemple, **camp-server**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Adobe Campaign Standard]**. Sélectionnez ensuite **[!UICONTROL Campaign Server]** dans la liste déroulante de type **[!UICONTROL Data element]**.

## Création de règles {#creating-rules}

Vous devez créer des règles pour les situations suivantes :

* [Postback des informations d&#39;identification personnelles](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback de tracking In-App](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback de tracking des notifications push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback de l&#39;emplacement](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback des informations d&#39;identification personnelles {#pii-postback}

>[!NOTE]
>
>Pour envoyer des informations d’identification personnelle d’une application mobile à Adobe Campaign, vous devez mettre en œuvre une API SDK. Voir à ce sujet la section [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Pour envoyer des données de PII à [!DNL Adobe Campaign Standard], créez une règle dans l’interface utilisateur de la collecte de données :

1. Dans l’interface utilisateur de la collecte de données, dans le tableau de bord de votre application mobile, cliquez sur le bouton **[!UICONTROL Règles]** tab puis **[!UICONTROL Créer une règle]**.

1. Saisissez un nom, par exemple, **Mobile Core - Collect PII**.

1. Dans la section **[!UICONTROL Events]**, cliquez sur **[!UICONTROL Add]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Sélectionnez ensuite **[!UICONTROL Collect PII]** dans la liste déroulante **[!UICONTROL Event type]**.

1. Cliquez sur **[!UICONTROL Keep changes]**.

1. Dans la section **[!UICONTROL Actions]**, cliquez sur **[!UICONTROL Add]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, sélectionnez **[!UICONTROL Send PII]** dans la liste déroulante **[!UICONTROL Action type]**.

1. Dans **[!UICONTROL URL]**, saisissez l&#39;URL suivante :

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Cochez la case **[!UICONTROL Add Post Body]**.

1. Dans **[!UICONTROL Post Body]**, saisissez ce qui suit :

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   Le paramètre marketingCloudId permet de mettre en correspondance vos abonnés d&#39;application et les destinataires contenus dans la base de données. Il est donc indispensable. Vous pouvez spécifier d&#39;autres paires clé-valeur en fonction des besoins de votre entreprise. Dans l&#39;exemple ci-dessus, les informations E-mail, Prénom et Nom sont transmises depuis l&#39;application.

   Les clés (par exemple cusEmail, cusFirstName et cusLastName) doivent correspondre aux ID de champ définis dans votre ressource personnalisée dans l’instance Adobe Campaign Standard. Les variables de valeur (par exemple, e-mail, firstName et LastName) doivent correspondre aux clés contenues dans les données JSON envoyées à partir de l&#39;application mobile lors de l&#39;appel de l&#39;API AMS collectPII depuis le code de l&#39;application.

   Vous pouvez également transmettre des données de cycle de vie dans le postback Collect PII ou dans un autre postback, en fonction de vos déclencheurs d&#39;événement. Voici un exemple des données de cycle de vie JSON :

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Les éléments de données définis dans l’interface utilisateur de la collecte de données doivent être inclus entre deux pourcentages, par exemple `%%mcid%%`, et les variables contextuelles de l’application doivent être incluses dans des pourcentages uniques, par exemple %contextdata.email%.

1. Dans **[!UICONTROL Content Type]**, saisissez **application/json**.

1. Dans **[!UICONTROL Timeout]**, sélectionnez 0.

   ![](assets/do-not-localize/rules_2.png)

Vos données utilisateur sont maintenant configurées pour être envoyées à Campaign.

### Postback de tracking In-App {#inapp-tracking-postback}

>[!NOTE]
>
>Si vous utilisez Android ACPCore v1.4.0 ou une version ultérieure/iOS ACPCore v2.3.0 ou une version ultérieure, la configuration des postbacks de suivi n’est pas requise.

Pour envoyer des données de suivi à [!DNL Adobe Campaign Standard] pour créer des rapports sur la manière dont vos utilisateurs interagissent avec les messages In-App dans votre application mobile, créez la règle suivante dans l’interface utilisateur de la collecte de données :

1. Dans l’interface utilisateur de la collecte de données, dans le tableau de bord de votre application mobile, sélectionnez la variable **[!UICONTROL Règles]** et cliquez sur **[!UICONTROL Ajouter une règle]**.

1. Saisissez un nom, par exemple, **Adobe Campaign - Tracking des clics In-App**.

1. Dans la section **[!UICONTROL Events]**, cliquez sur **[!UICONTROL Add]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Adobe Campaign Standard]**. Sélectionnez ensuite **[!UICONTROL Tracking des clics In-App]** dans la liste déroulante **[!UICONTROL Event type]**.

1. Cliquez sur **[!UICONTROL Keep changes]**.

1. Dans la section **[!UICONTROL Actions]**, cliquez sur **[!UICONTROL Add]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, sélectionnez **[!UICONTROL Send postback]** dans la liste déroulante **[!UICONTROL Event type]**.

1. Dans **[!UICONTROL URL]**, renseignez l&#39;URL suivante :

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Cochez la case **[!UICONTROL Add post body]**.

1. Dans **[!UICONTROL Post Body]**, saisissez **{}**.

1. Dans **[!UICONTROL Content Type]**, saisissez **application/json**.

1. Dans **[!UICONTROL Timeout]**, sélectionnez 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback de tracking des notifications push {#push-tracking-postback}

>[!NOTE]
>
>Si vous utilisez Android ACPCore v1.4.0 ou une version ultérieure/iOS ACPCore v2.3.0 ou une version ultérieure, la configuration des postbacks de suivi n’est pas requise.

Pour envoyer des données de suivi à [!DNL Adobe Campaign Standard], qui vous aide à effectuer le suivi des diffusions des notifications push et de l’interaction de vos utilisateurs avec votre application mobile, vous devez créer une règle dans l’interface utilisateur de la collecte de données.

Pour plus d&#39;informations sur le tracking des messages push, voir la section [Tracking des messages push](../../administration/using/push-tracking.md).

Pour tracker les actions de l&#39;application, utilisez l&#39;API trackAction. Pour plus d&#39;informations, voir la section [Tracker les actions de l&#39;application](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. Dans l’interface utilisateur de la collecte de données, dans le tableau de bord de votre application mobile, cliquez sur le bouton **[!UICONTROL Règles]** et cliquez sur **[!UICONTROL Ajouter une règle]**.

1. Saisissez un nom, par exemple, **Adobe Campaign - Tracking des clics push**.

1. Dans la section **[!UICONTROL Events]**, cliquez sur **[!UICONTROL Add]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, sélectionnez **[!UICONTROL Track Action]** dans la liste déroulante **[!UICONTROL Event type]**.

1. Dans la liste déroulante **[!UICONTROL Action]**, sélectionnez **[!UICONTROL Action]**, puis **[!UICONTROL equals]** et saisissez **tracking**.

1. Cliquez sur **[!UICONTROL Keep changes]**. Puis, dans la section **[!UICONTROL Actions]**, cliquez sur **[!UICONTROL Add]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, sélectionnez **[!UICONTROL Send postback]** dans la liste déroulante **[!UICONTROL Action type]**.

1. Dans **[!UICONTROL URL]**, saisissez l&#39;URL suivante :

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Cochez la case **[!UICONTROL Add post body]**.

1. Ajoutez votre corps de publication, par exemple, { }.

1. Dans **[!UICONTROL Content Type]**, saisissez **application/json**.

1. Dans **[!UICONTROL Timeout]**, sélectionnez 0.

### Postback de l&#39;emplacement {#location-postback}

1. Dans l’interface utilisateur de la collecte de données, dans le tableau de bord de votre application mobile, cliquez sur le bouton **[!UICONTROL Règles]** et cliquez sur **[!UICONTROL Ajouter une règle]**.

1. Entrez un nom, par exemple, **Postback de l&#39;emplacement**.

1. Dans la section **[!UICONTROL Events]**, cliquez sur **[!UICONTROL Add]**.

1. Créez un événement, par exemple, Entrée dans un point ciblé ou Sortie d&#39;un point ciblé. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **Places - Version bêta**. Ensuite, **Enter POI** ou **Exit POI** dans la liste déroulante **[!UICONTROL Event type]**.

1. Entrez un nom, par exemple, **Places - Version bêta - Entrée dans un point ciblé** ou **Sortie d&#39;un point ciblé**.

1. Dans la section **[!UICONTROL Actions]**, cliquez sur **[!UICONTROL Add]**.

1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Mobile Core]**. Ensuite, sélectionnez **[!UICONTROL Send postback]** dans la liste déroulante **[!UICONTROL Action type]**.

1. Saisissez un nom, par exemple, **Mobile Core - Envoyer le postback de l&#39;emplacement**.

1. Dans **[!UICONTROL URL]**, saisissez l&#39;URL suivante :

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Cochez la case **[!UICONTROL Add post body]** et ajoutez votre corps de publication, par exemple :

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
   >Dans l’exemple ci-dessus, les éléments de données situés à droite doivent être configurés dans l’interface utilisateur de collecte de données en suivant la procédure décrite à la section [Création d’éléments de données](../../administration/using/configuring-rules-launch.md#create-data-elements). Les éléments de données situés à gauche sont pris en charge dans [!DNL Adobe Campaign Standard] et n’ont pas besoin de configuration. Si vous avez besoin de données supplémentaires, vous devez incorporer des extensions de ressources personnalisées dans [!DNL Adobe Campaign Standard].

1. Dans **[!UICONTROL Content Type]**, saisissez **application/json**.

1. Dans **[!UICONTROL Timeout]**, sélectionnez 5.

   ![](assets/do-not-localize/rules_4.png)
