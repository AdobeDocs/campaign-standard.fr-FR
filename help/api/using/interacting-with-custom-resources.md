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
source-git-commit: 538739417c4ed28ff2991186dac5fb69d1af3afd

---


# Interaction avec des ressources personnalisées {#interacting-with-custom-resources}

Le point de fin **/customResources** vous permet d’exposer les ressources personnalisées ACS dans REST. En fonction de cette API, une intégration entre les entités personnalisées et les points de fin externes est disponible.

Le point de fin /customResources a exactement le même comportement que le point de fin /profileAndServices.

Les ressources personnalisées exposées dans cette API sont les suivantes :

* toutes les entités liées à l&#39;entité de profil
* toutes les entités liées aux enfants de l&#39;entité de profil
* toutes les entités qui ne sont pas liées au profil et, pour ces entités, à leurs enfants et petits-enfants.

>[!NOTE]
>Les ressources personnalisées disponibles sous /profileAndServicesExt ne sont pas exposées dans l&#39;API /customResources.

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
>Vous aurez la responsabilité de gérer et de nettoyer les informations d’identification personnelle de ces ressources personnalisées. Pour plus d&#39;informations sur l&#39;outil de confidentialité, [cliquez ici](../../api/using/creating-a-privacy-request.md).

