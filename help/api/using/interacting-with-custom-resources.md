---
solution: Campaign Standard
product: campaign
title: Ressources personnalisées
description: En savoir plus sur la gestion des ressources personnalisées avec les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 98%

---


# Interaction avec des ressources personnalisées {#interacting-with-custom-resources}

Le point d’entrée **/customResources** vous permet d’exposer les ressources personnalisées Campaign dans REST. Grâce à cette API, l’intégration entre les entités personnalisées et les points d’entrée externes est possible.

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

