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
internal: n
snippet: y
translation-type: ht
source-git-commit: 538739417c4ed28ff2991186dac5fb69d1af3afd

---


# Interaction avec des ressources personnalisées {#interacting-with-custom-resources}

Le point d’entrée **/customResources** vous permet d’exposer les ressources personnalisées ACS dans REST. Grâce à cette API, l’intégration entre les entités personnalisées et les points d’entrée externes est possible.

Le comportement du point d’entrée /customResources est identique à celui du point d’entrée /profileAndServices.

Les ressources personnalisées exposées dans cette API sont les suivantes :

* toutes les entités liées à l’entité de profil ;
* toutes les entités liées aux enfants de l’entité de profil ;
* toutes les entités non liées au profil et, pour ces entités, leurs enfants et petits-enfants.

>[!NOTE]
>Les ressources personnalisées disponibles dans /profileAndServicesExt ne sont pas exposées dans l’API /customResources.

Voici un exemple expliquant comment récupérer les métadonnées d’une ressource personnalisée :

```
GET /customResources/resourceType/<customResourceName>
```

Pour effectuer une création, une mise à jour ou une suppression, utilisez GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>Le point d’entrée et les workflows de l’API de confidentialité (/privacy/privacyTool) ne gèrent pas les ressources personnalisées non liées à l’entité de profil.
>Il vous appartiendra de gérer et de nettoyer les informations d’identification personnelle de ces ressources personnalisées. Pour plus d’informations sur l’outil de confidentialité, [cliquez ici](../../api/using/creating-a-privacy-request.md).

