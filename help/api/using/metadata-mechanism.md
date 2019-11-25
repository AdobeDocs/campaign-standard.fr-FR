---
title: Mécanisme de métadonnées
description: En savoir plus sur le mécanisme de métadonnées.
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


# Mécanisme de métadonnées {#metadata-mechanism}

Vous pouvez récupérer les métadonnées des ressources à l’aide de **resourceType** dans une requête GET :

`GET /profileAndServices/resourceType/<resourceName>`

La réponse renvoie les métadonnées principales de la ressource (tous les autres champs sont descriptifs ou internes) :

* Le noeud **Content** renvoie les champs de la ressource. Pour chaque champ du noeud de **contenu** , nous pouvons trouver les champs suivants :

   * "apiName" : nom de l’attribut utilisé dans les API.
   * "type" : il s’agit de la définition de type de niveau supérieur (chaîne, nombre, lien, collection, énumération...).
   * "dataPolicy" : la valeur du champ doit respecter les règles de stratégie données. Par exemple, si la règle dataPolicy est définie sur "email", la valeur doit être un courrier électronique valide. Lors d’un PATCH ou d’un POST, la variable dataPolicy peut vérifier la valeur ou modifier la valeur à transformer (smartCase, par exemple).
   * "category" : donne la catégorie du champ dans l’éditeur de requêtes.
   * "resType" : c'est le type technique.

      Si "type" est renseigné avec la valeur "link" ou "collection", la valeur resTarget est le nom de la ressource ciblée par le lien.
Si "type" est renseigné avec la valeur "enumeration", un champ "values" est ajouté et chaque valeur d’énumération est détaillée dans le noeud **values** .

* Le noeud **Filters** renvoie l’URL pour récupérer les filtres associés. For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Exemple de requête***

Exécutez une requête GET sur la ressource.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie la description complète de la ressource de profil.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
