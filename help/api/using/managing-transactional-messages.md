---
title: Gestion des messages transactionnels
description: Découvrez comment gérer les messages transactionnels avec les API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 100%

---


# Gestion des messages transactionnels {#managing-transactional-messages}

## A propos des messages transactionnels

Une fois que vous avez créé l’événement de votre choix, il vous faut intégrer le déclenchement de cet événement à votre site web.

>[!NOTE]
>
>La création et la publication d’un événement sont présentées dans la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/administration/using/configuring-transactional-messaging.html).

Par exemple, vous souhaitez qu’un événement de type « Abandon de panier » soit déclenché lorsque l’un de vos clients quitte votre site web avant d’avoir acheté les produits de son panier. Pour ce faire, le développeur web de votre site doit se servir de l’API REST des messages transactionnels.

1. Il exécute une requête selon la méthode POST, qui déclenche l’[envoi de l’événement transactionnel](#sending-a-transactional-event).
1. La réponse à la requête POST contient une clé primaire, qui permet au développeur d’exécuter une ou plusieurs requêtes par le biais d’une requête GET. De cette façon, il peut obtenir le [statut de l’événement](#transactional-event-status).

## Envoi d’un événement transactionnel {#sending-a-transactional-event}

L’événement transactionnel est envoyé via une requête POST avec la structure d’URL suivante :

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZATION>** : votre ORGANIZATION ID personnel. Consultez [cette section](../../api/using/must-read.md).

* **&lt;transactionalAPI>** : les points d’entrée (endPoints) de l’API des messages transactionnels.

   Le nom du point d’entrée de l’API des messages transactionnels dépend de la configuration de votre instance. Il correspond à la valeur &quot;mc&quot; suivie de votre identifiant d’organisation personnel. Prenons l’exemple de la société Geometrixx, dont l’identifiant d’organisation est &quot;geometrixx&quot;. Dans ce cas, la requête POST serait la suivante :

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Notez que le point d’entrée de l’API des messages transactionnels est également visible pendant l’aperçu de l’API)

* **&lt;eventID>** : type d’événement à envoyer. Cet identifiant est généré lors de la création de la définition d’événement. Consultez la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/administration/using/configuring-transactional-messaging.html).

### En-tête de requête POST

La requête doit contenir un en-tête &quot;Content-Type: application/json&quot;.

Vous devez ajouter un jeu de caractères, par exemple **utf-8**. Cette valeur dépend de l’application REST utilisée.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### Corps de requête POST

Les données d’événement sont contenues dans le corps JSON POST. La structure de l’événement dépend de sa définition. Le bouton d’aperçu de l’API dans l’écran de définition des ressources donne un exemple de requête. Consultez la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/administration/using/configuring-transactional-messaging.html).

Il est possible d’ajouter les paramètres facultatifs suivants au contenu de l’événement pour gérer l’envoi de messages transactionnels liés à cet événement :

* **expiration** (facultatif) : après cette date, l’envoi de l’événement transactionnel sera annulé.
* **scheduled** (facultatif) : à partir de cette date, l’événement transactionnel sera traité et le message transactionnel sera envoyé.

>[!NOTE]
>
>Les valeurs des paramètres &quot;expiration&quot; et &quot;scheduled&quot; suivent le format ISO 8601. Ce format spécifie l’utilisation de la lettre majuscule &quot;T&quot; pour séparer la date et l’heure. Il peut toutefois être supprimé de l’entrée ou de la sortie pour une meilleure lisibilité.

### Réponse à la requête POST

La réponse POST renvoie l’état de l’événement transactionnel au moment de sa création. Pour récupérer son état actuel (données de l’événement, statut de l’événement...), utilisez la clé primaire renvoyée par la réponse POST dans une requête GET :

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Exemple de requête***

Requête POST pour envoyer l’événement.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

Réponse à la requête POST.

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### Statut de l’événement transactionnel {#transactional-event-status}

Dans la réponse, le champ &quot;status&quot; vous permet de savoir si l’événement a été traité ou non :

* **pending** : l’événement est en attente ; il se trouve dans cet état lorsqu’il vient d’être déclenché.
* **processing** : l’événement est en attente de diffusion ; il est transformé en message et ce message est envoyé.
* **paused** : le processus d’événement est en pause. L’événement n’est plus traité, mais il est conservé dans une file d’attente, dans la base de données Adobe Campaign. Consultez à ce sujet la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **processed** : l’événement a été traité et le message a bien été envoyé.
* **ignored** : l’événement a été ignoré par la diffusion, généralement lorsqu’une adresse est en quarantaine.
* **deliveryFailed** : une erreur de diffusion s’est produite pendant le traitement de l’événement.
* **routageFailed** : la phase de routage a échoué ; cette situation peut se produire, par exemple, lorsque le type d’événement spécifié est introuvable.
* **tooOld** : l’événement a expiré avant d’être traité ; cette situation peut se produire pour diverses raisons, par exemple lorsqu’un envoi échoue à plusieurs reprises (l’événement n’est plus à jour) ou lorsque le serveur ne peut plus traiter les événements après une surcharge.
* **targetingFailed** : Campaign Standard n’a pas pu enrichir un lien utilisé pour le ciblage des messages.
