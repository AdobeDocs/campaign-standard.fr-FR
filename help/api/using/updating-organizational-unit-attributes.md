---
title: Mise à jour des attributs d’une entité organisationnelle
description: Découvrez comment mettre à jour les attributs d’une entité organisationnelle
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '84'
ht-degree: 100%

---


# Mise à jour des attributs d’une entité organisationnelle {#updating-organizational-unit-attributes}

1. Exécutez une requête GET sur la ressource **orgUnitBase** pour récupérer la clé PKey de l’entité organisationnelle.
1. Exécutez une requête PATCH sur l’entité organisationnelle, avec les attributs à mettre à jour dans la payload.

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

Elle contient toutes les entités organisationnelles. Récupérez la clé PKey de l’entité souhaitée.

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

Exécutez une requête PATCH sur l’entité organisationnelle, avec les attributs à mettre à jour dans la payload.

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
