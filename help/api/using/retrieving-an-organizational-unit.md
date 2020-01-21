---
title: Récupération de l’entité organisationnelle d’un profil
description: Découvrez comment récupérer l’entité organisationnelle d’un profil avec les API.
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
translation-type: ht
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Récupération de l’entité organisationnelle d’un profil {#retrieving-organizational-units}

1. Exécutez une requête GET sur la clé PKey du profil pour récupérer l’URL **orgUnit**.
1. Exécutez une requête GET sur l’URL pour obtenir plus de détails sur l’entité organisationnelle.

<br/>

***Exemple de requête ***

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
