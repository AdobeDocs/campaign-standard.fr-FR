---
solution: Campaign Standard
product: campaign
title: Mise à jour de l’entité géographique d’un profil
description: Découvrez comment gérer les entités géographiques avec les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 100%

---


# Mise à jour de l’entité géographique d’un profil {#updating-a-geographical-unit}

1. Exécutez une requête GET sur la ressource **geoUnitBase** pour récupérer la clé PKey de l’entité géographique.
1. Exécutez une requête PATCH sur la clé PKey du profil, avec la clé PKey de l’entité géographique souhaitée dans la payload.

<br/>

***Exemple de requête***

Récupérez la liste des entités géographiques.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle contient toutes les entités géographiques. Récupérez la clé PKey de l’entité à laquelle vous souhaitez affecter le profil.

```
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

Exécutez une requête PATCH sur le profil, avec la clé PKey de l’entité géographique souhaitée dans la payload.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
