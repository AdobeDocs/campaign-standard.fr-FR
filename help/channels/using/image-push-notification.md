---
title: Affichage d’une image à partir d’une  Adobe Campaign de notification Push standard
description: Découvrez ici comment afficher une image à partir d’une notification  Adobe Campaign Push sur un périphérique iOS.
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Affichage d’une image à partir d’une  Adobe Campaign de notification Push standard {#image-push}

>[!NOTE]
>
>Ce s’applique uniquement aux appareils iOS.

## Étape 1 : Configuration de la notification Push {#set-up-push}

La notification Push est prise en charge par les SDK de plateforme d’expérience.

Les applications mobiles recevant les notifications push doivent être configurées par un administrateur dans l&#39;interface d&#39;Adobe Campaign.

En configurant Adobe Campaign et Adobe Mobile Services, vous serez en mesure d&#39;utiliser les données de votre application mobile pour vos campagnes. Pour plus d’informations à ce propos, consultez cette [page](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html).

Pour envoyer des notifications Push avec une application SDK Experience Cloud, une application mobile doit être configurée dans Adobe Experience Platform Launch et être configurée dans  Adobe Campaign. Pour plus d’informations à ce propos, consultez cette [page](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

## Étape 2 : Personnaliser votre notification Push dans  Adobe Campaign {#customize-push}

Pour parfaire votre notification push, Adobe Campaign vous permet d&#39;accéder à un ensemble d&#39;options avancées lors de sa création.

1. Créer une notification push. Pour plus d’informations à ce propos, consultez cette page.

1. Dans la page de contenu de la notification Push, accédez à la section Options avancées.

1. Entrez l’URL de votre fichier dans le champ URL du contenu multimédia enrichi.
A partir d&#39;iOS 10, vous pouvez insérer des fichiers image, gif, audio et vidéo.

   ![](assets/push_notif_advanced_6.png)

1.  et enregistrez votre notification Push.

## Étape 3 : Adaptation du code de l’application Mobile {#mobile-app-code}

Après avoir personnalisé votre notification Push dans  Adobe Campaign, vous devez configurer votre application mobile pour afficher l’image sur les périphériques.

>[!NOTE]
>
>Si votre demande se trouve dans Objective-C, reportez-vous à la [documentation](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html)suivante.

Si votre application se trouve dans Swift, procédez comme suit :

1. Ouvrez votre projet xCode.

1. Dans votre projet Xcode, sélectionnez **Fichier** > **Nouveau** > ****.

1. Sélectionnez Notification Service Extension.

   ![](assets/push_notif_advanced_12.png)

1. Vérifiez que la classe de fichier **NotificationService.swift** est créée.

1. Modifiez cette classe et remplacez le contenu par défaut par ce qui suit.
Cela permet à l’application de gérer le paramètre entrant avec l’URL de l’image, de l’analyser, de le copier localement, puis de l’afficher à partir de la notification Push.

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

Le mobile doit recevoir la charge utile suivante pendant l’envoi de la notification.

L’URL de l’image est mappée avec la clé media-pièce jointe-url. Il s’agit de la paire clé/valeur que vous devez gérer du point de vue du code de l’application pour télécharger et afficher l’image.

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## Étape 4 : Test de l’envoi du push {#test-send-push}

Vous pouvez maintenant tester la création de votre application et du que vous avez créé à l’étape 2 ci-dessus. Pour plus d&#39;informations sur la préparation et l&#39;envoi de votre notification Push, consultez cette [page](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)

