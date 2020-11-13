---
title: Cas pratiques mobiles pris en charge dans Adobe Campaign Standard grâce aux SDK Adobe Experience Platform
description: Ce document apporte des informations sur la prise en charge des cas pratiques mobiles.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '971'
ht-degree: 100%

---


# Cas pratiques mobiles pris en charge dans Adobe Campaign Standard {#mobile-use-cases}

Dans cette page, vous trouverez la liste de tous les cas pratiques mobiles pris en charge dans [!DNL Adobe Campaign Standard] en utilisant les [!DNL Adobe Experience Platform SDKs]. Notez que la prise en charge de ces cas pratiques suppose l’installation et la configuration des [!DNL Adobe Experience Platform SDKs], d’[!DNL Adobe Experience Platform Launch] et d’[!DNL Adobe Campaign Standard]. Pour plus d’informations à ce propos, consultez [cette page](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard prend en charge les cas pratiques suivants :

* [Enregistrer un profil mobile dans Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Envoyer un jeton push à Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Enrichir un profil mobile à l’aide de données personnalisées provenant de votre application ](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Enrichir un profil mobile avec les données de cycle de vie de votre application](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Tracker les interactions de l’utilisateur à l’aide de notifications push](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Mettre en œuvre un événement personnalisé dans votre application mobile pour déclencher des messages In-App.](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Définir des champs de liaison servant à effectuer une authentification supplémentaire pour le modèle de profil basé sur les messages In-App](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Pour configurer ces cas pratiques, vous devez utiliser les extensions d’[!DNL Experience Platform Launch] suivantes :

* **[!DNL Adobe Campaign Standard]** <br>Pour installer et configurer l’extension de Campaign Standard, voir la section [Configurer l’extension de Campaign Standard dans Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch).
* **[!DNL Mobile Core]**, qui est automatiquement installée. <br>Pour plus d’informations sur l’extension Mobile Core, voir la section [Mobile Core](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core).
* **[!DNL Profile]**, qui est automatiquement installée. <br>Pour plus d’informations sur l’extension Profile, voir la section [Profil](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile).

## Enregistrer un profil mobile dans Campaign Standard {#register-mobile-profile}

### Avec iOS {#register-mobile-profile-ios}

Sous iOS, les [!DNL Experience Platform APIs] suivantes sont nécessaires :

* **[!UICONTROL Début de cycle de vie]**, au démarrage de l’application et lorsqu’elle est active au premier plan.
* **[!UICONTROL Mise en pause du cycle de vie]**, lorsque l’application est en arrière-plan.

Pour plus d’informations, voir la section [Extension de cycle de vie sous iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios).

Voici un exemple d’implémentation de ce cas pratique avec iOS :

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Avec Android {#register-mobile-profile-android}

Sous Android, les [!DNL Experience Platform APIs] suivantes sont nécessaires :

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Pour plus d’informations, voir la section [Extension du cycle de vie sous Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android).

Voici un exemple de mise en œuvre pour ce cas pratique avec Android :

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Envoyer un jeton push à Adobe Campaign Standard {#send-push-token}

### Avec iOS {#send-push-token-ios}

Sous iOS, le [!DNL Experience Platform SDK] suivant est nécessaire :

* **[!UICONTROL setPushIdentifier]** <br>Pour plus d’informations, voir la section [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier).

Voici l’exemple de mise en œuvre de ce cas pratique avec iOS :

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Avec Android {#send-push-token-android}

Sous Android, le [!DNL Experience Platform SDK] suivant est nécessaire :

* **[!UICONTROL setPushIdentifier]** <br>Pour plus d’informations, voir la section [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier).

Voici l’exemple de mise en œuvre de ce cas pratique avec Android :

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Enrichir un profil mobile à l’aide de données personnalisées provenant de votre application {#enrich-mobile-profile-custom}

Pour que ce cas pratique fonctionne, vous devez créer des règles pour les postbacks d’informations d’identification personnelles. Pour plus d’informations, voir la section [Postbacks d’informations d’identification personnelles](../../administration/using/configuring-rules-launch.md#pii-postback).

### Avec iOS {#enrich-mobile-profile-custom-ios}

Sous iOS, l’[!DNL Experience Platform API] suivante est nécessaire :

* collectPII <br> Pour plus d’informations, voir collectPII.

Voici un exemple d’implémentation de ce cas pratique avec iOS :

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### Avec Android {#enrich-mobile-profile-custom-android}

Sous Android, l’[!DNL Experience Platform API] suivante est nécessaire :

* collecTPII <br> Pour plus d’informations, voir collectPII.

Voici un exemple de mise en œuvre pour ce cas pratique avec Android :

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## Enrichir un profil mobile avec les données de cycle de vie de votre application {#enrich-mobile-profile-lifecycle}

Pour que ce cas pratique fonctionne, vous devez créer des règles pour les postbacks d’informations d’identification personnelles. Pour plus d’informations, voir la section [Postbacks d’informations d’identification personnelles](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaign ne fait pas la distinction entre les données personnalisées et les données de cycle de vie provenant de l’application mobile. Ces deux types de données peuvent être envoyés au serveur à l’aide d’une règle de postback CollectPII en réponse à un événement dans l’application mobile.

### Avec iOS {#enrich-mobile-profile-lifecycle-ios}

Sous iOS, les [!DNL Experience Platform APIs] suivantes sont nécessaires :

* **[!UICONTROL Début de cycle de vie]**, au démarrage de l’application et lorsqu’elle est active au premier plan.
* **[!UICONTROL Mise en pause du cycle de vie]**, lorsque l’application est en arrière-plan.

Pour plus d’informations, voir la section [Extension de cycle de vie sous iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios).

Voici un exemple d’implémentation de ce cas pratique avec iOS :

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Avec Android {#enrich-mobile-profile-lifecycle-android}

Sous Android, les [!DNL Experience Platform APIs] suivantes sont nécessaires :

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Pour plus d’informations, voir la section [Extension du cycle de vie sous Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android).

Voici un exemple de mise en œuvre pour ce cas pratique avec Android :

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Tracker les interactions de l’utilisateur à l’aide de notifications push {#track-user-push}

Vous devez créer des règles pour le postback de tracking des notifications push. Pour plus d’informations, voir la section [Postback de tracking des notifications push](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Avec iOS {#track-user-push-ios}

Sous iOS, le [!DNL Experience Platform SDK] suivant est nécessaire :

* **[!UICONTROL trackAction]**. Pour plus d’informations, voir la section [Tracker les actions de l’application](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Voici un exemple d’implémentation de ce cas pratique avec iOS :

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Avec Android {#track-user-push-android}

Sous Android, le [!DNL Experience Platform SDK] suivant est nécessaire :

* **[!UICONTROL trackAction]** Pour plus d’informations, voir la section [Tracker les actions de l’application](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Voici un exemple de mise en œuvre pour ce cas pratique avec Android :

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Implémenter un événement personnalisé dans votre application pour déclencher des messages In-App {#custom-event-inapp}

### Avec iOS {#custom-event-inapp-ios}

Sous iOS, le [!DNL Experience Platform SDK] suivant est nécessaire :

* **[!UICONTROL trackAction]**. Pour plus d’informations, voir la section [Tracker les actions de l’application](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Voici un exemple d’implémentation de ce cas pratique avec iOS :

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Avec Android {#custom-event-inapp-android}

Sous Android, le [!DNL Experience Platform SDK] suivant est nécessaire :

* **[!UICONTROL trackAction]** Pour plus d’informations, voir la section [Tracker les actions de l’application](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Voici un exemple de mise en œuvre pour ce cas pratique avec Android :

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Définir des champs de liaison servant à effectuer une authentification supplémentaire {#linkage-fields-inapp}

### Avec iOS {#linkage-fields-inapp-ios}

Pour définir des champs de liaison servant à effectuer une authentification supplémentaire pour le modèle de profil basé sur les messages In-App dans iOS, le [!DNL Experience Platform SDK] suivant est nécessaire :

* Définir des champs de liaison <br>Pour plus d’informations, voir la section [Définir des champs de liaison](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields).
* Réinitialiser les champs de liaison <br>Pour plus d’informations, voir la section [Réinitialiser les champs de liaison](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields).

Voici des exemples de mise en œuvre de ce cas pratique avec iOS.

Pour définir les champs de liaison :

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

Pour réinitialiser les champs de liaison :

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Avec Android {#linkage-fields-inapp-android}

Pour définir des champs de liaison servant à effectuer une authentification supplémentaire pour le modèle de profil basé sur les messages In-App dans Android, le SDK Experience Platform suivant est nécessaire :

* Définir des champs de liaison <br>Pour plus d’informations, voir la section [Définir des champs de liaison](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields).
* Réinitialiser les champs de liaison <br>Pour plus d’informations, voir la section [Réinitialiser les champs de liaison](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields).

Voici des exemples de mise en œuvre de ce cas pratique avec Android.

Pour définir les champs de liaison :

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Pour réinitialiser les champs de liaison :

```
Campaign.resetLinkageFields()
```
