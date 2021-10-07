---
title: Récupération de l’entité organisationnelle d’un profil
description: Découvrez comment récupérer l’entité organisationnelle d’un profil avec les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 37048884-bd03-46ea-8e2e-a73ad568153b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '79'
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
