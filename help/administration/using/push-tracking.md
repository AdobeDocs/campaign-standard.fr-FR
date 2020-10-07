---
title: Mise en œuvre du suivi des notifications push
description: Ce document permet de vous assurer que le suivi des notifications push a été correctement mis en œuvre sur iOS et Android.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 75%

---


# Mise en œuvre du suivi des notifications push {#push-tracking}

## À propos du suivi des notifications push {#about-push-tracking}

Pour vérifier que la notification push a été entièrement développée, vous devez vous assurer que la partie « suivi » a été correctement mise en œuvre.
Cela suppose que vous avez déjà mis en oeuvre les premières parties de l’implémentation des notifications Push :

* Enregistrement de l’utilisateur de l’application
* Gestion d’un message de notification Push

Le suivi push est divisé en trois types :

* **Impressions push** : lorsqu’une notification push a été envoyée à l’appareil et qu’elle se trouve dans le centre de notification, mais qu’elle n’a pas du tout été touchée.  On considère qu’il s’agit d’une impression.  Dans la plupart des cas, le nombre des impressions doit être similaire, voire identique à celui des diffusions. Cela garantit que l&#39;appareil a bien reçu le message et a transmis cette information au serveur.

* **Clic push** : lorsqu’une notification push a été envoyée à l’appareil et que l’utilisateur a cliqué sur ce dernier.  L’utilisateur a voulu consulter la notification (qui sera déplacée vers le suivi des ouvertures push) ou l’ignorer.

* **Ouverture push** : lorsqu’une notification push a été envoyée à l’appareil et que l’utilisateur a cliqué sur la notification, entraînant l’ouverture de l’application. Cette mesure est similaire au Clic push, sauf qu’une Ouverture push ne sera pas déclenchée si la notification a été ignorée.

Afin de mettre en œuvre le suivi pour Campaign Standard, l’application mobile doit inclure le SDK Mobile. Ces SDK sont disponibles sur Adobe Mobile Services. Pour plus d’informations à ce propos, consultez cette [page](../../administration/using/configuring-a-mobile-application.md).

Pour envoyer des informations de suivi, trois variables doivent être envoyées. Deux de ces variables font partie des données reçues de Campaign Standard. Une autre variable est une variable d’action qui détermine s’il s’agit d’une **impression**, d’un **clic** ou d’une **ouverture**.

| Variable | Valeur |
|:-:|:-:|
| broadlogId | _mId à partir des données |
| deliveryId | _dId à partir des données |
| action | 1 pour Ouverture, 2 pour Clic et 7 pour Impression |

## Mise en œuvre pour Android {#implementation-android}

### Comment mettre en œuvre le suivi des impressions push {#push-impression-tracking-android}

For impression tracking, you will have to send value &quot;7&quot; for action when calling **[!UICONTROL trackAction()]** function.

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Comment mettre en œuvre le suivi des clics {#push-click-tracking-android}

For click tracking, you will have to send value &quot;2&quot; for action when calling **[!UICONTROL trackAction()]** function.

Pour effectuer le suivi des clics, deux scénarios doivent être gérés :

* L’utilisateur voit la notification, mais l’efface.
* L’utilisateur voit la notification et clique dessus pour la transformer en un suivi d’ouverture.

Pour ce faire, vous devez utiliser deux intentions : une pour le fait de cliquer sur la notification et une autre pour le fait de fermer la notification.

**[!UICONTROL MyFirebaseMessagingService.java]**

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

In order for the **[!UICONTROL BroadcastReceiver]** to work you need to register it to the **[!UICONTROL AndroidManifest.xml]**

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Comment mettre en œuvre le suivi des ouvertures {#push-open-tracking-android}

Vous devez envoyer « 1 » et « 2 », car l’utilisateur doit cliquer sur la notification pour ouvrir l’application. Si l’application n’est pas lancée/ouverte par le biais d’une notification push, aucun événement de suivi ne se produit.

Pour effectuer le suivi des ouvertures, vous devez créer une intention. Les objets d’intention permettent au système d’exploitation Android d’appeler votre méthode lorsque certaines actions sont effectuées (dans le cas présent, cliquer sur la notification pour ouvrir l’application).

Ce code est basé sur la mise en œuvre du suivi des impressions de clics. With **[!UICONTROL Intent]** set, you now need to send tracking info back to Adobe Campaign Standard. In this case, you need to set the **[!UICONTROL Open Intent]** to open to a certain view in your app, this will call the onResume method with the notification data in the **[!UICONTROL Intent Object]**.

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
  
  
private void handleTracking() {
    //Check to see if this view was opened based on a notification
    Intent intent = getIntent();
    Bundle data = intent.getExtras();
  
    if (data != null) {
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Mise en œuvre pour iOS {#implementation-iOS}

### Comment mettre en œuvre le suivi des impressions push {#push-impression-tracking-iOS}

For impression tracking, you will have to send value &quot;7&quot; for action when calling **[!UICONTROL trackAction()]** function.

Pour comprendre le fonctionnement des notifications iOS, les trois états d’une application doivent être présentés :

* **Premier plan** : lorsque l’application est actuellement active et se trouve actuellement à l’écran (en premier plan).
* **Arrière-plan** : lorsque l’application n’est pas à l’écran mais que le processus n’est pas fermé. Lorsque vous double-cliquez sur le bouton d’accueil, il montre généralement toutes les applications qui se trouvent en arrière-plan.
* **Désactivée/fermée** : une application dont le processus a été interrompu.

Si une application est fermée, Apple ne l’appellera pas tant qu’elle n’aura pas été relancée. Vous ne pourrez donc pas savoir quand la notification a été reçue sur iOS.

In order to still have **[!UICONTROL Impression]** tracking working while the app is in the background we need to send **[!UICONTROL Content-Available]** to let the app know a tracking has to be done.

>[!CAUTION]
>
>Le suivi des impressions iOS n’est pas précis et ne doit pas être considéré comme fiable.

Le code suivant cible l’application en arrière-plan :

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
  
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
  
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

Le code suivant cible l’application au premier plan :

```
// This will get called when the app is in the foreground
  
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
  
  
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        if (deliveryId != nil && broadlogId != nil) {
             ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Comment mettre en œuvre le suivi des clics {#push-click-tracking-iOS}

For click tracking, you will have to send value &quot;2&quot; for action when calling **[!UICONTROL trackAction()]** function.

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

Désormais, lorsque vous envoyez des notifications push, vous devez ajouter une catégorie. Dans le cas présent, nous l’avons appelée « PAR DÉFAUT » .

![](assets/tracking_push.png)

Then to handle the **[!UICONTROL Dismiss]** and send a tracking info you need to add the following:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Comment mettre en œuvre le suivi des ouvertures {#push-open-tracking-iOS}

Vous devez envoyer « 1 » et « 2 », car l’utilisateur doit cliquer sur la notification pour ouvrir l’application. Si l’application n’est pas lancée/ouverte par le biais d’une notification push, aucun événement de suivi ne se produit.

```
import Foundation
import UserNotifications
import UserNotificationsUI
  
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
  
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
