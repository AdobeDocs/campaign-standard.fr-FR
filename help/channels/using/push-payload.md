---
title: Présentation de la structure de la payload des notifications push Campaign Standard
description: Ce est destiné à décrire la structure de la charge utile reçue dans les applications mobiles.
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
source-git-commit: 302159577f5a7d917ba253994ff23c4980d518e5

---


# Présentation de la structure de la payload des notifications push Campaign Standard {#push-payload}

 Adobe Campaign vous permet d’envoyer des notifications Push personnalisées et segmentées sur les périphériques mobiles iOS et Android aux applications mobiles (applications mobiles).

Chaque notification Push reçue sur une application mobile comporte des informations utilisées par l’application pour afficher la notification Push en cas d’envoi d’une notification Push d’alerte, et probablement pour effectuer d’autres calculs, en particulier si une notification Push silencieuse est envoyée.

Ces informations sont reçues par le code de l’application mobile dans un gestionnaire de  qui indique qu’une notification Push a été reçue. Lors de l&#39;envoi de notifications Push à partir de  Adobe Campaign Standard, les informations reçues dans l&#39;application mobile peuvent également contenir des informations spécifiques à Campaign Standard qui peuvent être utilisées pour tirer parti de certaines fonctionnalités fournies par le. En outre, la charge peut contenir des données personnalisées qui peuvent être utilisées par l’application mobile.

Ce décrit la structure de la charge utile reçue dans une application mobile lorsqu’une notification Push est correctement envoyée à une application à partir de  Standard.

>[!NOTE]
>
>La structure de la charge utile varie selon le type d’application mobile (application iOS, application Android compatible FCM, par exemple).

## Structure de charge utile push {#push-payload-structure}

Cette section décrit la structure d’un exemple de charge utile pour diverses plateformes mobiles et décrit les principaux attributs qu’elle contient. Il s’agit de la structure de la charge utile reçue dans le code de l’application mobile dans le gestionnaire de  du qui indique qu’une notification Push a été reçue.

Les attributs de charge utile et leurs valeurs varient en fonction des configurations fournies dans les options avancées de notification Push. Cette section fournit également un mappage entre ces configurations dans l’interface utilisateur Campaign Standard et les attributs dans la charge utile afin de clarifier comment la charge utile changera lors de la configuration d’une option dans Campaign Standard.

### Pour les applications mobiles iOS {#payload-structure-ios}

**Exemple de charge utile envoyée de  Adobe Campaign à l’application iOS :**

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

**Exemple de charge utile JSON à utiliser avec APNS Tester[iOS](https://pushtry.com/)**

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

La section la plus importante de la charge utile est le dictionnaire aps, qui contient des clés définies par Apple et est utilisé pour déterminer comment le système qui reçoit la notification doit alerter l’utilisateur, le cas échéant. Cette section contient des clés prédéfinies utilisées par l’application mobile pour formuler le comportement de la notification Push.

Vous trouverez des informations détaillées sur les attributs des applications dans la documentation destinée aux développeurs Apple : [Création de la charge utile](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)de notification à distance.

### Pour l’application Android {#payload-structure-android}

**Exemple d&#39;envoi de données utiles depuis  Adobe Campaign vers l&#39;application Android**

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

**Exemple de charge utile JSON pour utiliser le testeur FCM[Google](https://pushtry.com/)**

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

La charge utile contient un message de données qui inclut tout le contenu du de notification Push  le contenu, y compris les paires clé/valeur personnalisées. L’application cliente doit gérer le message pour créer et afficher la notification Push, si nécessaire ou pour ajouter toute autre logique métier.

Pour comprendre les aspects d’une charge utile androïde, consultez Concepts et options de [messagerie (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>La prise en charge des messages de notification dans la charge utile Android a été supprimée à compter de janvier 2018 afin de permettre la réactivation de l’application et la transmission du contrôle à l’application mobile sans que l’utilisateur ait à interagir avec l’application.

### Mappage entre les configurations Campaign Standard et les attributs de charge {#mapping-payload}

| Configuration Campaign | Attribut affecté dans iOS | Attribut affecté dans Android | Description |
|:-:|:-:|:-:|:-:|
| Titre du message <br>Corps du message | alerte → titre <br> alerte → corps | titre <br>corps | Ces données contiennent des détails du message d’alerte.<br>Le titre et les clés de corps fournissent le contenu de l’alerte. |
| Jouer un son | sound | sound | Son personnalisé à lire avec l’alerte. |
| Valeur du badge | badge | badge | Valeur entière à utiliser pour marquer l’icône de l’application. |
| Ajouter un lien profond  | uri | NA | Un lien profond vous permet d&#39;amener directement les utilisateurs à un contenu situé dans l&#39;application (au lieu d&#39;ouvrir une page de navigateur Web). |
| Catégorie | category | category | Pour afficher des actions personnalisées avec une notification à distance. <br>La clé  du permet au système d’afficher les actions de ce  sous forme de boutons dans l’interface d’alerte. |
| Champs personnalisés | custom_field1, custom_field2... | custom_field1, custom_field2... | Toute donnée personnalisée que vous souhaitez envoyer à votre application. |
| URL de contenu multimédia enrichi (images, gif, fichiers audio et vidéo)<br>(applicable uniquement pour iOS 10 ou version ultérieure) | media-attachement-url | NA | URL de vos fichiers multimédia pour ajouter du contenu enrichi à votre notification. <br>Lorsque vous fournissez une valeur pour cette URL, l’indicateur de contenu modifiable est automatiquement envoyé dans la charge utile. <br> (Uniquement applicable pour iOS 10 ou version ultérieure) |
| Contenu mutable <br> (applicable uniquement pour iOS 10 ou version ultérieure) | mutable-content | NA | L’extension du service de notification dans votre application &quot;intercepte&quot; toutes les notifications distantes avec la clé de contenu modifiable et vous permet de gérer/manipuler le contenu de la charge utile de requête, qui peut ensuite être utilisée pour personnaliser la notification. Cette fonctionnalité permet notamment de télécharger et d’afficher plusieurs médias, de déchiffrer toutes les données chiffrées présentes dans la charge utile push. Vous trouverez plus d’informations dans [Modification de la charge utile d’une notification](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)distante. <br>(Uniquement applicable pour iOS 10 ou version ultérieure) |
| Contenu disponible | content-available | NA | La sélection de cette option permet de réveiller une application iOS lorsqu’elle est en arrière-plan/suspendue. Le réveil implique que l’application s’exécute en arrière-plan et que le gestionnaire de  approprié responsable de la réception de la charge utile des données de notification Push obtient un contrôle et peut utiliser les données pour effectuer n’importe quel calcul, y compris, mais sans s’y limiter, la création d’une notification Push personnalisée et l’affichage de la même valeur. Pour plus d’informations, reportez-vous à la section [Mise en veille avec le](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)de notification. |
| URL de contenu multimédia enrichi (fichiers d’image)<br>(applicable uniquement pour Android) | NA | media-attachement-url | URL de vos fichiers image pour ajouter du contenu enrichi à votre notification. |
| NA | _mId<br>_dId | _mId <br>_dId | Valeurs de BroadlogId et de deliveryId.<br>Ces attributs sont requis si votre application souhaite appeler un postback de suivi pour effectuer le suivi du moment où l’utilisateur a cliqué/ouvert la notification Push. Ces informations sont calculées et envoyées en interne par le serveur d’applications sans intervention de l’utilisateur.<br>Vous trouverez des informations sur les postbacks sur cette [page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback). |

### Comment récupérer les informations de charge utile dans le code d’application mobile {#payload-information}

Les informations de charge utile envoyées par le serveur d’applications sont reçues par le code de l’application mobile dans un gestionnaire de  qui indique qu’une notification Push a été reçue. Ce  varie selon la plateforme mobile sur laquelle l’application est en cours d’exécution et selon que l’application est en avant-plan ou en arrière-plan. La documentation suivante vous aidera à identifier le gestionnaire de  que vous souhaitez gérer en fonction de votre cas d&#39;utilisation.

* Applications iOS : **Gestion des notifications** distantes dans Notifications [](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)distantes.
* Applications Android : [Réception de messages sur une application cliente Android](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Exemple d’application mobile iOS**

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

**Exemple d’application FCM mobile Android**

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
