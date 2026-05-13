---
title: Mise à jour de l’entité géographique d’un profil
description: Découvrez comment gérer les entités géographiques avec les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 9dc07d86-00b2-4885-b6ac-0a6f9bc45236
TQID: https://experienceleague.adobe.com/1RVk3P72UhhJ8RG7sGv9cu-opebJRAX-PdQQCbZM6vk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 94
ht-degree: 100%

---

# Mise à jour de l&#39;entité géographique d&#39;un profil {#updating-a-geographical-unit}

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
