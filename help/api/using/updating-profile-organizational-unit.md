---
title: Mise à jour de l’entité organisationnelle d’un profil
description: Découvrez comment mettre à jour l’entité organisationnelle d’un profil avec les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 6ce49aeb-a113-43ee-bfe3-f26a4a9e2a56
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 100%

---

# Mise à jour de l&#39;entité organisationnelle d&#39;un profil {#managing-organizational-units}

1. Exécutez une requête GET sur la ressource **orgUnitBase** pour récupérer la clé PKey de l’entité organisationnelle.
1. Exécutez une requête PATCH sur la clé PKey du profil, avec la clé PKey de l’entité organisationnelle souhaitée dans la payload.

<br/>

***Exemple de requête***

Récupérez la liste des entités organisationnelles.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle contient toutes les entités organisationnelles. Récupérez la clé PKey de l’entité à laquelle vous souhaitez affecter le profil.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

Exécutez une requête PATCH sur le profil, avec la clé PKey de l’entité organisationnelle souhaitée dans la payload.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "orgUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
