---
title: Récupération de l’entité organisationnelle d’un profil
description: Découvrez comment récupérer l’entité organisationnelle d’un profil avec les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 37048884-bd03-46ea-8e2e-a73ad568153b
TQID: https://experienceleague.adobe.com/z4Nn2S85xwt4Wz9K8In2pEYPQcQml-cSQXBLZA0yQJc
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 79
ht-degree: 100%

---

# Récupération de l&#39;entité organisationnelle d&#39;un profil {#retrieving-organizational-units}

1. Exécutez une requête GET sur la clé PKey du profil pour récupérer l’URL **orgUnit**.
1. Exécutez une requête GET sur l’URL pour obtenir plus de détails sur l’entité organisationnelle.

<br/>

***Exemple de requête***

Récupérez l’enregistrement du profil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

La requête renvoie l’URL orgUnit du Profil.

```
{
  ...
  "orgUnit": {
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

Exécutez une requête GET sur l’URL pour récupérer des informations supplémentaires.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie des détails sur l’entité organisationnelle.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "label": "Brand 4",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand4)"
}
```
