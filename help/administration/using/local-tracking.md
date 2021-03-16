---
solution: Campaign Standard
product: campaign
title: Mise en œuvre du suivi des notifications push
description: Ce document permet de vous assurer que le suivi des notifications push a été correctement mis en œuvre sur iOS et Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Paramètres d’instance
role: Administrateur
level: Expérience
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 74%

---


# Mise en œuvre du suivi local {#local-tracking}

## À propos du suivi local {#about-local-tracking}

Dans cette page, découvrez comment vous assurer que le suivi des notifications locales a été mis en œuvre correctement. Notez que cela implique que la notification locale a déjà été configurée.

Le suivi des notifications locales peut être divisé en trois types :

* **Impressions locales** : lorsqu’une notification locale a été envoyée à l’appareil et qu’elle se trouve dans le centre de notification, mais qu’elle n’a pas du tout été touchée. Dans la plupart des cas, le nombre des impressions doit être similaire, voire identique à celui des diffusions. Cela garantit que l&#39;appareil a bien reçu le message et a transmis cette information au serveur.

* **clic**  local : lorsqu&#39;une notification locale a été remise au périphérique et que l&#39;utilisateur a cliqué sur la notification. L’utilisateur a voulu consulter la notification (qui sera déplacée vers le suivi des ouvertures locales) ou l’ignorer.

* **Ouverture locale** : lorsqu’une notification locale a été envoyée à l’appareil et que l’utilisateur a cliqué sur la notification, entraînant l’ouverture de cette dernière. Cette mesure est similaire au clic local, sauf qu’une ouverture locale ne sera pas déclenchée si la notification a été ignorée.

Pour mettre en œuvre le suivi pour Adobe Campaign Standard, l’application mobile doit inclure les SDK Mobile dans l’application. Ces SDK sont disponibles dans [!DNL Adobe Mobile Services].

Pour envoyer des informations de suivi, trois variables doivent être envoyées : deux font partie des données reçues d’Adobe Campaign et l’autre est une variable d’action qui détermine s’il s’agit d’une impression, d’un clic ou d’une ouverture.

| Variable | Valeur |
| :-: | :-: |
| deliveryId | `deliveryId` des données entrantes (semblable au suivi Push où  `_dld` est utilisé) |
| broadlogId | `broadlogId` des données entrantes (semblable au suivi Push où  `_mld` est utilisé) |
| action | « 1 » pour Ouverture, « 2 » pour Clic et « 7 » pour Impression |

## Mise en oeuvre du suivi des impressions locales {#implement-local-impression-tracking}

Le Adobe Experience Platform Mobile SDK envoie automatiquement le événement d’impression pour Android et iOS sans configuration supplémentaire.

## Mise en oeuvre du suivi des clics {#implementing-click-tracking}

Pour le suivi des clics, vous devez envoyer la valeur &quot;2&quot; pour l’action lors de l’appel des fonctions `collectMessageInfo()` ou `trackAction()`.

### Pour Android {#implement-click-tracking-android}

Pour effectuer le suivi des clics, deux scénarios doivent être gérés :

* L’utilisateur voit la notification, mais l’efface.

   Pour effectuer le suivi des clics en cas de scénario de rejet, ajoutez le récepteur de diffusion `NotificationDismissalHandler` dans le fichier AndroidManifest de votre module d&#39;application.

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* L&#39;utilisateur voit la notification et clique dessus, ce qui se transforme en suivi d’ouvertures.

   Ce scénario doit générer un clic et un ouverture. Le suivi de ce clic fera partie de l’implémentation nécessaire pour suivre l’ouverture. Voir [Implémentation du suivi ouvert](#implement-open-tracking).

### Pour iOS {#implement-click-tracking-ios}

Pour envoyer les informations de suivi des clics, vous devez ajouter les éléments suivants :

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## Mise en oeuvre du suivi ouvert {#implement-open-tracking}

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

        //Opened based on the notification, you need to get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

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
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
