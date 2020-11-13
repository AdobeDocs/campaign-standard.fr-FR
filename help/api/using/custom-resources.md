---
title: Ressources personnalisées
description: En savoir plus sur la gestion des ressources personnalisées avec les API.
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
source-wordcount: '204'
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
* [Définir les liens avec d’autres ressources](https://helpx.adobe.com/fr/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
