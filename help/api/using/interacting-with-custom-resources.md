---
title: Ressources personnalisées
description: En savoir plus sur la gestion des ressources personnalisées avec les API/
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
source-git-commit: 5c4d3fc9853bf9bad4efcefaea242fecc9c4c61f

---


# Interaction avec des ressources personnalisées {#interacting-with-custom-resources}

Le point de fin **/customResources** vous permet d’exposer les entités personnalisées ACS dans REST. En fonction de cette API, une intégration entre les entités personnalisées et les points de fin externes est disponible.

Le comportement de /customResources est identique à celui du point de terminaison /profileAndServices.

Les entités personnalisées exposées dans cette API sont les suivantes :

* toutes les entités liées à l'entité de profil
* toutes les entités liées aux enfants de l'entité de profil
* toutes les entités qui ne sont pas liées au profil et, pour ces entités, à leurs enfants et petits-enfants.

>[!NOTE]
>Les entités personnalisées disponibles sous /profileAndServicesExt ne sont pas exposées dans l'API /customResources.

Voici un exemple pour récupérer les métadonnées d’une ressource personnalisée :

```
GET /customResources/resourceType/<customResourceName>
```

Pour effectuer une création, une mise à jour ou une suppression, utilisez GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>Le point de fin et les processus de l’API de confidentialité (/privacy/privacyTool) ne gèrent pas les ressources personnalisées qui ne sont pas liées à l’entité de profil.
>Vous aurez la responsabilité de gérer et de nettoyer les informations d’identification personnelle de ces ressources personnalisées. Pour plus d'informations sur l'outil de confidentialité, [cliquez ici](../../api/using/privacy-management.md).