---
title: Interaction avec l’historique marketing
description: Découvrez comment interagir avec l’historique marketing des profils.
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
source-wordcount: '147'
ht-degree: 100%

---


# Interaction avec l’historique marketing {#interacting-with-marketing-history}

Le point d’entrée **history** vous permet d’interagir avec l’historique marketing d’un profil.
Vous pouvez ainsi, par exemple, récupérer facilement la page miroir d’une diffusion envoyée à un profil. Pour ce faire, procédez comme suit :

1. Exécutez une requête GET avec le point d’entrée **history** et la clé primaire du profil.
1. Exécutez une requête GET sur l’adresse href **events** renvoyée.
1. Elle renvoie la liste des événements du profil, avec des liens vers des pages miroir dans le nœud **mirrorPage** .

<br/>

***Exemple de requête***

Récupérez l’historique marketing du profil à l’aide d’une requête GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Le nœud « events » renvoie l’URL qui vous donne accès aux événements du profil.

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

Exécutez une requête GET sur l’adresse href events renvoyée.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie la liste des événements du profil, avec des liens vers des pages miroir dans le nœud « mirrorPage ».

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
