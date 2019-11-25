---
title: Gestion des unités organisationnelles
description: Découvrez comment gérer les unités d'organisation à l'aide des API.
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gestion des unités organisationnelles {#managing-organizational-units}

Le point de fin **orgUnitBase** vous permet d’interagir avec les unités organisationnelles, ce qui vous permet, par exemple, de mettre à jour leurs attributs ou l’unité organisationnelle d’un profil. Pour plus d’informations sur les unités d’organisation dans Campaign, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html)Campaign.

Le champ Unité **** organisationnelle est ajouté à un profil lors de l’extension de la ressource de profil. Par conséquent, n’oubliez pas d’utiliser toujours le point de terminaison **profileAndServicesExt** pour interagir avec les unités géographiques. Pour plus d’informations sur l’extension de ressource du profil, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)Campaign.

## Récupération de l’unité Organisation d’un profil

1. Exécutez une requête GET sur le profil PKey pour récupérer l’URL **orgUnit** .
1. Effectuez une requête GET sur l’URL pour obtenir plus de détails sur l’unité d’organisation.

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

Il renvoie l’URL orgUnit du profil.

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

Effectuez une requête GET sur l’URL pour récupérer plus d’informations.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Il renvoie des détails sur l'unité d'organisation.

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

## Mise à jour de l’unité d’organisation d’un profil

1. Exécutez une requête GET sur la ressource **orgUnitBase** pour récupérer la clé PK de l'unité d'organisation
1. Exécutez une requête PATCH sur le profil PKey, avec l’unité organisationnelle PKey désirée dans la charge utile.

<br/>

***Exemple de requête***

Récupérez la liste des unités organisationnelles.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie toutes les unités d’organisation. Récupérez la clé PK de l'unité à laquelle vous souhaitez affecter le profil.

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

Exécutez une requête PATCH sur le profil, avec la clé PK de l’unité organisationnelle souhaitée dans la charge utile.

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

## Mise à jour des attributs d'une unité d'organisation

1. Exécutez une requête GET sur la ressource **orgUnitBase** pour récupérer la clé PKey de l’unité d’organisation.
1. Exécutez une requête PATCH sur l’unité d’organisation, avec les attributs à mettre à jour dans la charge utile.

<br/>

***Exemple de requête***

Récupérez la liste des unités organisationnelles.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie toutes les unités d’organisation. Récupérez la clé PK de l'unité souhaitée.

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

Exécutez une requête PATCH sur l’unité d’organisation, avec les attributs à mettre à jour dans la charge utile.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->
