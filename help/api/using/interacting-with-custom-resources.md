---
title: Interagir avec des ressources personnalisées
description: En savoir plus sur la gestion des ressources personnalisées avec les API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
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
source-wordcount: '198'
ht-degree: 100%
---
# Interagir avec des ressources personnalisées {#interacting-with-custom-resources}

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
