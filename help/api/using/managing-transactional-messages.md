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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d54f036c394db7abdba805ea2c21436c0ef5212c

---


# Managing transactional messages {#managing-transactional-messages}

## A propos des messages transactionnels

Une fois que vous avez créé l&#39;événement de votre choix, il vous faut intégrer le déclenchement de cet événement à votre site web.

>[!NOTE]
>
>La création et la publication d’un événement sont présentées dans <a href="https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html">la documentation</a>de la campagne.

Par exemple, vous souhaitez qu’un événement &quot;abandon de panier&quot; soit déclenché chaque fois qu’un client quitte votre site Web avant d’acheter les produits dans son panier. Pour ce faire, votre développeur Web doit utiliser l’API de messages transactionnels REST.

1. Le développeur envoie une requête selon la méthode POST, qui déclenche l’ [envoi de l’événement](#sending-a-transactional-event)transactionnel.
1. La réponse à la requête POST contient une clé primaire, qui permet au développeur d’envoyer une ou plusieurs requêtes par le biais d’une requête GET. De cette façon, il peut obtenir le statut [de l&#39;](#transactional-event-status)événement.

## Envoi d’un événement transactionnel {#sending-a-transactional-event}

L’événement transactionnel est envoyé via une requête POST avec la structure d’URL suivante :

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZATION>**: votre ID d’ORGANISATION personnel. Consultez [cette section](../../api/using/must-read.md).

* **&lt;transactionalAPI>**: les points de fin de l’API Messages transactionnels.

   Le nom du point de fin de l’API Messages transactionnels dépend de la configuration de votre instance. Il correspond à la valeur &quot;mc&quot; suivie de votre ID d’organisation personnel. Prenons l’exemple de la société Geometrixx, avec &quot;geometrixx&quot; comme ID d’organisation. Dans ce cas, la requête POST serait la suivante :

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Notez que le point de fin de l’API des messages transactionnels est également visible pendant l’aperçu de l’API)

* **&lt;eventID>**: type d’événement à envoyer. Cet identifiant est généré lors de la création de la définition d’événement. Refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

### En-tête de requête POST

La requête doit contenir un &quot;Content-Type: en-tête application/json&quot;.

Vous devez ajouter un jeu de caractères, par exemple **utf-8**. Notez que cette valeur dépend de l’application REST utilisée.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### Corps de requête POST

Les données d’événement sont contenues dans le corps de la publication JSON. La structure de l’événement dépend de sa définition. Le bouton d’aperçu de l’API dans l’écran de définition des ressources fournit un exemple de requête. Refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

Les paramètres facultatifs suivants peuvent être ajoutés au contenu de l’événement pour gérer l’envoi de messages transactionnels liés à l’événement :

* **expiration** (facultatif) : après cette date, l&#39;envoi de l&#39;événement transactionnel sera annulé.
* **planifié** (facultatif) : à partir de cette date, l&#39;événement transactionnel sera traité et le message transactionnel sera envoyé.

>[!NOTE]
>
>Les valeurs des paramètres &quot;expiration&quot; et &quot;programmé&quot; suivent le format ISO 8601. ISO 8601 spécifie l&#39;utilisation de la lettre majuscule &quot;T&quot; pour séparer la date et l&#39;heure. Il peut toutefois être supprimé de l’entrée ou de la sortie pour une meilleure lisibilité.

### Réponse à la demande POST

La réponse POST renvoie l’état de l’événement transactionnel au moment de sa création. Pour récupérer son état actuel (données d’événement, état d’événement...), utilisez la clé primaire renvoyée par la réponse POST dans une requête GET :

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Exemple de requête ***

Demande POST pour envoyer l’événement.

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

Réponse à la demande POST.

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

### Statut d’événement transactionnel {#transactional-event-status}

Dans la réponse, le champ &quot;status&quot; vous permet de savoir si l’événement a été traité ou non :

* **en attente**: l’événement est en attente ; l’événement prend cet état lorsqu’il vient d’être déclenché.
* **traitement**: l&#39;événement est en attente de livraison - il est transformé en message et le message est envoyé.
* **en pause**: le processus d’événement est en pause. Elle n’est plus traitée, mais conservée dans une file d’attente dans la base de données Adobe Campaign. For more on this, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **traité**: l’événement a été traité et le message a bien été envoyé.
* **ignoré**: l’événement a été ignoré par la diffusion, généralement lorsqu’une adresse est en quarantaine.
* **deliveryFailed**: une erreur de remise s&#39;est produite pendant le traitement de l&#39;événement.
* **routageFailed**: la phase de routage a échoué - cela peut se produire par exemple lorsque le type d&#39;événement spécifié est introuvable.
* **tooOld**: l’événement a expiré avant d’être traité ; cela peut se produire pour diverses raisons, par exemple lorsqu’une envoi échoue plusieurs fois (l’événement n’est plus à jour) ou lorsque le serveur ne peut plus traiter les événements après une surcharge.
* **targetingFailed**: Campaign Standard n’a pas pu enrichir un lien utilisé pour le ciblage des messages.
