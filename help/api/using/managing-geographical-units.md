---
title: Gestion des unités géographiques
description: Découvrez comment gérer des unités géographiques à l’aide d’API.
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


# Gestion des unités géographiques {#managing-geographical-units}

>[!CAUTION]
>
>La fonctionnalité Unité géographique a été abandonnée avec la version 18.7 de Campaign Standard.
Par conséquent, les nouvelles instances de Campaign Standard, ainsi que les instances existantes sans unités géographiques créées, ne peuvent pas avoir cette fonctionnalité mise en oeuvre à partir de la version 18.7.
For more on this, refer to the <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">Deprecated features</a> page.

Le point de fin **geoUnitBase** vous permet d’interagir avec les unités géographiques, ce qui vous permet, par exemple, de mettre à jour leurs attributs ou l’unité d’un profil.

Le champ Unité **** géographique est ajouté à un profil lors de l’extension de la ressource de profil. Par conséquent, n’oubliez pas d’utiliser toujours le point de terminaison **profileAndServicesExt** pour interagir avec les unités géographiques. Pour plus d’informations sur l’extension de ressource du profil, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)Campaign.

## Récupération de l’unité géographique d’un profil

1. Exécutez une requête GET sur le profil PKey pour récupérer l’URL **geoUnit** .
1. Effectuez une requête GET sur l’URL pour obtenir plus de détails sur l’unité géographique.

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

Elle renvoie l’URL de l’unité géographique du profil.

```
{
  ...
  "geoUnit": {
    "PKey": "@zYV4vIjP1wpBebml6s71hjGiDhs4_gHgbC_UhuJFk8h7XTZxZ5QnZrPnQPEfB__TxwR2ge6sz61D8RR4zvD75CLDZtc<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

Effectuez une requête GET sur l’URL pour récupérer plus d’informations.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Il renvoie des détails sur l’unité géographique.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "Default geographical entity (accessible to everyone)",
  "label": "All",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "all",
  "parentTitle": "",
  "title": "All (all)"
}
```

## Mise à jour de l’unité géographique d’un profil

1. Exécutez une requête GET sur la ressource **geoUnitBase** pour récupérer la clé PKey de l’unité géographique.
1. Exécutez une requête PATCH sur le PKey du profil, avec l’unité géographique PKey désirée dans la charge utile.

<br/>

***Exemple de requête***

Récupérez la liste des unités géographiques.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie toutes les unités géographiques. Récupérez la clé PK de l'unité à laquelle vous souhaitez affecter le profil.

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

Effectuez une requête PATCH sur le profil, avec la clé PK de l’unité géographique souhaitée dans la charge utile.

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

## Mise à jour des attributs d’une unité géographique

1. Exécutez une requête GET sur la ressource **geoUnitBase** pour récupérer la clé PKey de l’unité géographique.
1. Exécutez une requête PATCH sur l’unité géographique, avec les attributs à mettre à jour dans la charge utile.

<br/>

***Exemple de requête***

Récupérez la liste des unités géographiques.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie toutes les unités géographiques. Récupérez la clé PK de l'unité souhaitée.

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

Exécutez une requête PATCH sur l’unité géographique, avec les attributs à mettre à jour dans la charge utile.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->
