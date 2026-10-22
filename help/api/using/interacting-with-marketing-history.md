---
title: Interagir avec l’historique marketing
description: Découvrez comment interagir avec l’historique marketing des profils
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
TQID: 'https://experienceleague.adobe.com/C5r-qK6kpvssv6eFdJNuOw61OXFapg8L8hrlxyb0vcA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '160'
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
