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
source-wordcount: '726'
ht-degree: 9%

---


# Implémentation du suivi local {#local-tracking}

## A propos du suivi local {#about-local-tracking}

Dans cette page, découvrez comment vous assurer que le suivi des notifications locales a été implémenté correctement. Notez que cela implique que la notification locale a déjà été configurée.

Le suivi des notifications locales peut être divisé en trois types :

* **Impressions** locales : lorsqu’une notification locale a été envoyée au périphérique et qu’elle se trouve sur le centre de notification, mais n’a pas été touchée du tout. Dans la plupart des cas, le nombre d’impressions doit être similaire si ce n’est pas le même que le nombre livré. Il s’assure que le périphérique a bien reçu le message et transmet ces informations au serveur.

* **Clic** local : lorsqu&#39;une notification locale a été diffusée sur le périphérique et que l&#39;utilisateur a cliqué sur ce dernier. L’utilisateur souhaitait soit vue la notification (qui à son tour basculerait vers le suivi ouvert local), soit rejeter la notification.

* **Ouverture** locale : lorsqu&#39;une notification locale a été envoyée au périphérique et que l&#39;utilisateur a cliqué sur la notification, l&#39;application s&#39;est ouverte. Il s’agit de la même méthode que le clic local, sauf qu’une ouverture locale ne sera pas déclenchée si la notification a été rejetée.

Pour mettre en oeuvre le suivi pour Adobe Campaign Standard, l’application mobile doit inclure Mobile SDK dans l’application. Ces SDK sont disponibles dans [!DNL Adobe Mobile Services].

Pour envoyer des informations de suivi, trois variables doivent être envoyées : deux font partie des données reçues d’Adobe Campaign et l’autre est une variable d’action qui détermine s’il s’agit d’une impression, d’un clic ou d’une ouverture.

| Variable | Valeur |
| :-: | :-: |
| deliveryId | &quot;deliveryId&quot; à partir des données entrantes (similaire au suivi Push où&quot;_dld&quot; est utilisé) |
| broadlogId | &quot;broadlogId&quot; à partir des données entrantes (semblable au suivi push où &quot;_mld&quot; est utilisé) |
| action | &quot;1&quot; pour Open, &quot;2&quot; pour Click et &quot;7&quot; pour Impression |

## Implémentation du suivi des impressions locales {#implement-local-impression-tracking}

Pour le suivi des impressions, vous devez envoyer la valeur &quot;7&quot; pour l&#39;action lors de l&#39;appel des fonctions VEMessageInfo() ou trackAction().

### Pour Android {#implement-local-impression-tracking-android}

Le SDK Adobe Experience Platform Mobile début le suivi d’impression pour la notification locale lors de son déclenchement.

### Pour iOS {#implement-local-impression-tracking-ios}

Pour expliquer comment mettre en oeuvre le suivi des impressions, nous devons comprendre les trois états d’une application :

* **Premier plan**: lorsque l’application est actuellement principale et affichée à l’écran au premier plan.

* **Contexte**: lorsque l’application n’est pas à l’écran mais que le processus n’est pas fermé non plus. Lorsque vous cliquez sur le bouton d’accueil en doublon, il affiche généralement toutes les applications en arrière-plan.

* **Désactivé/Fermé**: lorsque le processus de demande a été interrompu. Si une application est fermée, Apple ne l’appellera pas tant que l’application n’aura pas été relancée. Cela signifie que vous ne pouvez jamais vraiment savoir quand la notification a été reçue sur iOS.

Pour que le suivi des impressions fonctionne toujours pendant que l’application est en arrière-plan, nous devons envoyer &quot;Contenu disponible&quot; pour informer l’application que le suivi doit être effectué.

Le SDK Adobe Experience Platform Mobile début le suivi d’impression pour la notification locale lors de son déclenchement.

>[!CAUTION]
>
>Le suivi des impressions iOS n’est pas précis et ne doit pas être examiné de manière fiable.

## Implémentation du suivi des clics {#implementing-click-tracking}

Pour le suivi des clics, vous devez envoyer la valeur &quot;2&quot; pour l&#39;action lors de l&#39;appel des fonctions MessageInfo() ou trackAction().

### Pour Android {#implement-click-tracking-android}

Pour effectuer le suivi des clics, deux scénarios doivent être gérés :

* L’utilisateur voit la notification, mais l’efface.

* L&#39;utilisateur voit la notification et clique dessus, ce qui se transforme en suivi ouvert.

Le premier scénario de clic est suivi par Adobe Experience Platform Mobile SDK.

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

Ensuite, pour gérer l’abandon et envoyer des informations de suivi, vous devez ajouter les éléments suivants :

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

## Implémentation du suivi ouvert {#implement-open-tracking}

Vous devez envoyer &quot;1&quot; et &quot;2&quot; car l’utilisateur doit cliquer sur la notification pour ouvrir l’application. Si l’application n’est pas lancée/ouverte par le biais d’une notification locale, aucun événement de suivi ne se produit.

### Pour Android {#implement-open-tracking-android}

Pour suivre l&#39;ouverture, nous devons créer l&#39;intention. Les objets Intent permettent à Android OS d&#39;appeler votre méthode lorsque certaines actions sont effectuées, dans ce cas, en cliquant sur la notification pour ouvrir l&#39;application.

Ce code est basé sur la mise en œuvre du suivi des impressions de clics. Une fois l’intention définie, vous devez à présent renvoyer les informations de suivi à Adobe Campaign. Dans ce cas, la Vue([!DNL Activity]) Android qui a déclenché la notification sera ouverte ou mise en premier plan suite au clic de l’utilisateur. L&#39;objet intent dans [!DNL Activity] contient les données de notification qui peuvent être utilisées pour effectuer le suivi des données ouvertes.

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
