---
title: Présentation de la structure de la payload des notifications push Campaign Standard
description: L’objectif de ce document est de décrire la structure de la payload reçue dans les applications mobiles.
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
source-wordcount: '1148'
ht-degree: 100%

---


# Présentation de la structure de la payload des notifications push {#push-payload}

 Adobe Campaign vous permet d’envoyer des notifications push personnalisées et segmentées sur les appareils mobiles iOS et Android vers les applications mobiles (app mobiles).

Chaque notification push reçue sur une application mobile comporte des informations utilisées par l’application pour afficher la notification push en cas d’envoi d’une notification push d’alerte, et probablement pour effectuer d’autres calculs, en particulier si une notification push silencieuse est envoyée.

Ces informations sont reçues par le code de l’application mobile dans un gestionnaire d’événement qui indique qu’une notification push a été reçue. Lors de l&#39;envoi de notifications push depuis Adobe Campaign Standard, les informations reçues dans l&#39;application mobile peuvent également contenir des informations spécifiques à Campaign Standard qui peuvent être utilisées pour tirer parti de certaines fonctionnalités fournies par Campaign Standard. En outre, la payload peut contenir des données personnalisées qui peuvent être consommées par l’application mobile.

Ce document décrit la structure de la payload reçue dans une application mobile lorsqu’une notification push est envoyée avec succès à une application à partir d’Adobe Campaign Standard.

>[!NOTE]
>
>La structure de la payload varie selon le type d’application mobile (application iOS, application Android compatible FCM, par exemple).

## Structure de la payload push {#push-payload-structure}

Cette section décrit la structure d’un exemple de payload pour diverses plateformes mobiles et décrit les principaux attributs qu’elle contient. Il s’agit de la structure de la payload reçue dans le code de l’application mobile dans le gestionnaire d’événement qui indique qu’une notification push a été reçue.

Les attributs de payload et leurs valeurs varient en fonction des configurations fournies dans les options avancées de notification push. Cette section fournit également un mappage entre ces configurations dans l’interface utilisateur Campaign Standard et les attributs dans la payload afin de clarifier la façon dont la payload changera lors de la configuration d’une option dans Campaign Standard.

### Pour l’application mobile iOS {#payload-structure-ios}

**Exemple de payload envoyée d’Adobe Campaign à l’application iOS :**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**Exemple de payload JSON à utiliser avec[iOS APNS Tester](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

La section la plus importante de la payload est le dictionnaire aps, qui contient des clés définies par Apple et est utilisé pour déterminer comment le système qui reçoit la notification doit alerter l’utilisateur, le cas échéant. Cette section contient des clés prédéfinies utilisées par l’application mobile pour formuler le comportement de la notification push.

Vous trouverez des informations détaillées sur les attributs dans aps dans la documentation destinée aux développeurs Apple : [Création de la payload de notification à distance](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### Pour l’application Android {#payload-structure-android}

**Exemple d&#39;envoi de payload depuis Adobe Campaign vers l&#39;application Android**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**Exemple de charge utile JSON pour utiliser le[Google FCM tester](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

La payload contient un message de données qui inclut tout le contenu de la diffusion de la notification push, y compris les paires clé/valeur personnalisées. L’application cliente doit gérer le message pour créer et afficher la notification push, si nécessaire, ou pour ajouter toute autre logique métier.

Pour comprendre les aspects d’une payload Android, consultez la section [Concepts et options de messagerie (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>La prise en charge des messages de notification dans la payload Android a été supprimée en janvier 2018 afin de permettre la réactivation de l’application et la transmission du contrôle à l’application mobile sans que l’utilisateur ait à interagir avec l’application.

### Mappage entre les configurations Campaign Standard et les attributs de payload {#mapping-payload}

| Configuration Campaign | Attribut concerné dans iOS | Attribut concerné dans Android | Description |
|:-:|:-:|:-:|:-:|
| Titre du message <br>Corps du message | alerte → titre <br> alerte → corps | titre <br>corps | Ces données contiennent des détails du message d’alerte.<br>Le titre et les clés de corps fournissent le contenu de l’alerte. |
| Jouer un son | sound | sound | Son personnalisé à jouer avec l’alerte. |
| Valeur du badge | badge | badge | Valeur entière à utiliser pour marquer l’icône de l’application. |
| Ajouter un lien profond  | uri | NA | Un lien profond vous permet d&#39;amener directement les utilisateurs à un contenu situé dans l&#39;application (au lieu d&#39;ouvrir une page de navigateur Web). |
| Catégorie | category | category | Pour afficher des actions personnalisées avec une notification à distance. <br>La clé de catégorie permet au système d’afficher les actions pour cette catégorie sous forme de boutons dans l’interface d’alerte. |
| Champs personnalisés | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Toute donnée personnalisée que vous souhaitez envoyer à votre application. |
| URL de contenu multimédia (images, gif, fichiers audio et vidéo)<br>(Applicable uniquement pour iOS 10 ou version ultérieure) | media-attachement-url | NA | URL de vos fichiers multimédia pour ajouter du contenu enrichi à votre notification. <br>Lorsque vous fournissez une valeur pour cette URL, le drapeau de contenu mutable est automatiquement envoyé dans le payload. <br> (Uniquement applicable pour iOS 10 ou version ultérieure) |
| Contenu mutable <br> (Applicable uniquement pour iOS 10 ou version ultérieure) | mutable-content | NA | L’extension du service de notification dans votre application « intercepte » toutes les notifications distantes avec la clé de contenu mutable et vous permet de gérer/manipuler le contenu de la payload de requête, qui peut ensuite être utilisée pour personnaliser la notification. Cette fonctionnalité permet notamment de télécharger et d’afficher plusieurs médias, de décrypter toutes les données cryptées présentes dans la payload push. Vous trouverez plus d’informations dans [Modification de la payload d’une notification à distance](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(Uniquement applicable pour iOS 10 ou version ultérieure) |
| Contenu disponible | content-available | NA | La sélection de cette option permet de réactiver une application iOS lorsqu’elle est en arrière-plan/suspendue. La réactivation implique que l’application s’exécute en arrière-plan et que le gestionnaire d’événement approprié responsable de la réception de la payload des données de notification push obtient un contrôle et peut utiliser les données pour effectuer n’importe quel calcul, y compris, mais sans s’y limiter, la création d’une notification push personnalisée et l’affichage de cette dernière. Pour plus d’informations, reportez-vous à la section [Mise en éveil d’une application avec la diffusion d&#39;une notification](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| URL de contenu multimédia (fichiers image)<br>(Applicable uniquement pour Android) | NA | media-attachement-url | URL de vos fichiers image pour ajouter du contenu enrichi à votre notification. |
| NA | _mId<br>_dId | _mId <br>_dId | Valeurs de broadlogId et deliveryId.<br>Ces attributs sont requis si votre application souhaite appeler un postback de suivi pour effectuer le suivi du moment où l’utilisateur a cliqué sur/ouvert la notification push. Ces informations sont calculées et envoyées en interne par le serveur applicatif, sans intervention de l’utilisateur.<br>Vous trouverez des informations sur les postbacks sur cette [page](https://helpx.adobe.com/fr/campaign/kb/config-app-in-launch.html#PIIpostback). |

### Comment récupérer les informations de payload dans le code d’application mobile {#payload-information}

Les informations de payload envoyées par le serveur de l’application sont reçues par le code de l’application mobile dans un gestionnaire d’événement qui indique qu’une notification push a été reçue. Cet événement varie selon la plateforme mobile sur laquelle l’application est en cours d’exécution et selon que l’application est exécutée au premier plan ou en arrière-plan. La documentation suivante vous aidera à identifier le gestionnaire d’événement que vous souhaitez gérer en fonction de votre cas d&#39;utilisation.

* Applications iOS : **Gestion des notifications à distance** dans [Notifications à distance](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
* Applications Android : [Réception de messages sur une application client Android](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Exemple pour une application mobile iOS**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Exemple pour une application FCM mobile Android**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```
