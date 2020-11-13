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
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '726'
ht-degree: 100%

---


# Mise en œuvre du suivi local {#local-tracking}

## À propos du suivi local {#about-local-tracking}

Dans cette page, découvrez comment vous assurer que le suivi des notifications locales a été mis en œuvre correctement. Notez que cela implique que la notification locale a déjà été configurée.

Le suivi des notifications locales peut être divisé en trois types :

* **Impressions locales** : lorsqu’une notification locale a été envoyée à l’appareil et qu’elle se trouve dans le centre de notification, mais qu’elle n’a pas du tout été touchée. Dans la plupart des cas, le nombre des impressions doit être similaire, voire identique à celui des diffusions. Cela garantit que l&#39;appareil a bien reçu le message et a transmis cette information au serveur.

* **Clic local** : lorsqu’une notification locale a été envoyée à l’appareil et que l’utilisateur a cliqué sur ce dernier. L’utilisateur a voulu consulter la notification (qui sera déplacée vers le suivi des ouvertures locales) ou l’ignorer.

* **Ouverture locale** : lorsqu’une notification locale a été envoyée à l’appareil et que l’utilisateur a cliqué sur la notification, entraînant l’ouverture de cette dernière. Cette mesure est similaire au clic local, sauf qu’une ouverture locale ne sera pas déclenchée si la notification a été ignorée.

Pour mettre en œuvre le suivi pour Adobe Campaign Standard, l’application mobile doit inclure les SDK Mobile dans l’application. Ces SDK sont disponibles dans [!DNL Adobe Mobile Services].

Pour envoyer des informations de suivi, trois variables doivent être envoyées : deux font partie des données reçues d’Adobe Campaign et l’autre est une variable d’action qui détermine s’il s’agit d’une impression, d’un clic ou d’une ouverture.

| Variable | Valeur |
| :-: | :-: |
| deliveryId | &quot;deliveryId&quot; à partir des données entrantes (similaire au suivi push où&quot;_dld&quot; est utilisé) |
| broadlogId | &quot;broadlogId&quot; à partir des données entrantes (similaire au suivi push où &quot;_mld&quot; est utilisé) |
| action | « 1 » pour Ouverture, « 2 » pour Clic et « 7 » pour Impression |

## Implémentation du suivi des impressions locales {#implement-local-impression-tracking}

Pour le suivi des impressions, vous devez envoyer la valeur « 7 » pour l&#39;action lors de l&#39;appel des fonctions collectMessageInfo() ou trackAction().

### Pour Android {#implement-local-impression-tracking-android}

Le SDK Adobe Experience Platform Mobile débute le suivi d’impression pour la notification locale lors de son déclenchement.

### Pour iOS {#implement-local-impression-tracking-ios}

Pour expliquer comment mettre en œuvre le suivi des impressions, nous devons comprendre les trois états d’une application :

* **Premier plan** : lorsque l’application est actuellement active et se trouve actuellement à l’écran en premier plan.

* **Arrière-plan** : lorsque l’application n’est pas à l’écran mais que le processus n’est pas fermé non plus. Lorsque vous double-cliquez sur le bouton d’accueil, il affiche généralement toutes les applications en arrière-plan.

* **Désactivée / Fermée** : lorsque le processus de l’application a été interrompu. Si une application est fermée, Apple ne l’appellera pas tant qu’elle n’aura pas été relancée. Cela signifie que vous ne pouvez jamais vraiment savoir quand la notification a été reçue sur iOS.

Pour que le suivi des impressions fonctionne toujours pendant que l’application est en arrière-plan, nous devons envoyer « Contenu disponible » pour informer l’application que le suivi doit être effectué.

Le SDK Adobe Experience Platform Mobile débute le suivi d’impression pour la notification locale lors de son déclenchement.

>[!CAUTION]
>
>Le suivi des impressions iOS n’est pas précis et ne doit pas être considéré comme fiable.

## Mise en œuvre du suivi des clics {#implementing-click-tracking}

Pour le suivi des clics, vous devez envoyer la valeur « 2 » pour l&#39;action lors de l&#39;appel des fonctions collectMessageInfo() ou trackAction().

### Pour Android {#implement-click-tracking-android}

Pour effectuer le suivi des clics, deux scénarios doivent être gérés :

* L’utilisateur voit la notification, mais l’efface.

* L&#39;utilisateur voit la notification et clique dessus, ce qui se transforme en suivi d’ouvertures.

Le premier scénario de clic est suivi par le SDK Mobile d’Adobe Experience Platform.

### Pour iOS {#implement-click-tracking-ios}

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

Ensuite, pour gérer l’abandon et envoyer des informations de suivi, vous devez ajouter les éléments suivants :

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                // Else comment out the above line and uncomment the line below
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

## Mise en œuvre du suivi des ouvertures {#implement-open-tracking}

Vous devez envoyer « 1 » et « 2 » car l’utilisateur doit cliquer sur la notification pour ouvrir l’application. Si l’application n’est pas lancée / ouverte par le biais d’une notification locale, aucun événement de suivi ne se produit.

### Pour Android {#implement-open-tracking-android}

Pour suivre l’ouverture, nous devons créer l’intention. Les objets d’intention permettent au système d’exploitation Android d’appeler votre méthode lorsque certaines actions sont effectuées, dans ce cas, en cliquant sur la notification pour ouvrir l’application.

Ce code est basé sur la mise en œuvre du suivi des impressions de clics. Lorsque l’intention est définie, vous devez renvoyer les informations de suivi à Adobe Campaign. Dans ce cas, la Vue Android ([!DNL Activity]) qui a déclenché la notification sera ouverte ou mise en premier plan suite au clic de l’utilisateur. L&#39;objet d’intention dans [!DNL Activity] contient les données de notification qui peuvent être utilisées pour effectuer le suivi des ouvertures.

MainActivity.java (étend [!DNL Activity])

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
        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");
  
  
  
        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Pour iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
  
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
  
    // Called when user clicks the local notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
            // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            // Else comment out the above line and uncomment the line below
            // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               // If you're using  ACPCore v2.3.0 or later, use the line below.
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
               // Else comment out the above line and uncomment the line below
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
