---
title: Mécanisme des métadonnées
description: En savoir plus sur le mécanisme des métadonnées.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 100%
---
# Mécanisme des métadonnées {#metadata-mechanism}

Vous pouvez récupérer les métadonnées des ressources en utilisant **resourceType** dans une requête GET :

`GET /profileAndServices/resourceType/<resourceName>`

La réponse renvoie les métadonnées principales de la ressource (tous les autres champs sont descriptifs ou internes) :

* Le nœud **Content** renvoie les champs de la ressource. Chaque champ du nœud **Content** comporte les champs suivants :

  * &quot;apiName&quot; : nom de l’attribut utilisé dans les API.
  * &quot;type&quot; : définition de type de niveau supérieur (chaîne, nombre, lien, collection, énumération...).
  * &quot;dataPolicy&quot; : la valeur du champ doit respecter les politiques données. Par exemple, si la règle dataPolicy est définie sur &quot;email&quot;, la valeur doit être un email valide. Lors d’un PATCH ou d’un POST, la variable dataPolicy peut vérifier la valeur ou modifier la valeur à transformer (smartCase, par exemple).
  * &quot;category&quot; : indique la catégorie du champ dans le requêteur.
  * &quot;resType&quot; : le type technique.

    Si &quot;type&quot; est renseigné avec la valeur &quot;link&quot; ou &quot;collection&quot;, la valeur resTarget est le nom de la ressource ciblée par le lien.
    Si &quot;type&quot; est renseigné avec la valeur &quot;enumeration&quot;, un champ &quot;values&quot; est ajouté et chaque valeur d’énumération est détaillée dans le nœud **values** .

* Le nœud **Filters** renvoie l’URL permettant de récupérer les filtres associés. Voir à ce propos [cette section](../../api/using/filtering.md).

<!-- créer une section au même niveau sur les liens -->
<!--
dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien
-->
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
