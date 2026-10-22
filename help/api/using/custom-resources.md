---
title: Ressources personnalisées
description: En savoir plus sur la gestion des ressources personnalisées avec les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
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
source-wordcount: '217'
ht-degree: 100%
---
# Ressources personnalisées {#custom-resources}

Adobe Campaign s’accompagne d’un modèle de données prédéfini, dans lequel les données sont définies au moyen de différentes ressources. Il est possible d’enrichir le modèle de données fourni en étendant les ressources pour ajouter vos propres champs personnalisés ou tables personnalisées, comme des tables d’achats ou de produits par exemple.

Les ressources personnalisées sont accessibles via les API à l’aide du point d’entrée **/profileAndServicesExt** et du nom de la ressource personnalisée.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Pour les ressources qui ne sont pas prêtes à l’emploi, utilisez toujours le préfixe <b>&quot;cus&quot;</b> avant le nom de la ressource.

Vous pouvez effectuer toutes les opérations possibles avec des ressources personnalisées à condition qu’elles soient liées à la table Profile. Prenons par exemple la structure des tables ci-dessous :

![texte alternatif](assets/cusresources.png)

Dans ce cas, toutes les ressources des tables **Transaction**, **TransactionDetails** et **Product** sont disponibles tant qu’elles sont liées à la table **Profile**.

<br/>

***Exemple de requête***

Exemple de requête GET pour accéder à la ressource étendue profileAndServicesExt.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Elle renvoie la liste de toutes les ressources personnalisées liées. Vous pouvez ensuite utiliser les URL des ressources pour effectuer toutes les tâches d’API décrites dans cette documentation.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

Pour plus d’informations sur l’extension du modèle de données, voir la documentation de Campaign :

* [Notions de modèle de données](../../developing/using/data-model-concepts.md)
* [Étendre l’API](../../developing/using/about-extending-the-api.md)
* [Définition de liens avec d’autres ressources](https://helpx.adobe.com/fr/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
