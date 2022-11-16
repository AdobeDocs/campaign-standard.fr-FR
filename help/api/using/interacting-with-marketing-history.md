---
title: Interagir avec l’historique marketing
description: Découvrez comment interagir avec l’historique marketing des profils
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 100%

---

# Interagir avec l’historique marketing{#interacting-with-marketing-history}

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
