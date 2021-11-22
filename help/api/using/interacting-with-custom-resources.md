---
title: Ressources personnalisées
description: En savoir plus sur la gestion des ressources personnalisées avec les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 100%

---

# Interaction avec des ressources personnalisées {#interacting-with-custom-resources}

Le point d’entrée **/customResources** vous permet d’exposer les ressources personnalisées Campaign dans REST. Grâce à cette API, l’intégration entre les entités personnalisées et les points d’entrée externes est possible.

Le comportement du point d’entrée /customResources est identique à celui du point d’entrée /profileAndServices.

Les ressources personnalisées exposées dans cette API sont les suivantes :

* toutes les entités qui ne sont pas exposées sous /profileAndServicesExt
* toutes les entités non liées au profil et, pour ces entités, leurs enfants et petits-enfants.
* par défaut, toutes les entités qui ne sont liées à rien, ainsi que leurs enfants et petits-enfants.

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
