---
title: Présentation d’Experience Data Model
description: Experience Data Model (XDM) est un ensemble standard de schémas de données dans lesquels des données peuvent être ingérées afin d’être utilisées avec les solutions et produits Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 100%
---
# Présentation d’Experience Data Model {#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector est actuellement en version Beta et peut être fréquemment mis à jour sans préavis. L’hébergement des clientes et clients sur Azure (actuellement en version Beta en Amérique du Nord uniquement) est obligatoire pour pouvoir accéder à ces fonctionnalités. Contactez l&#39;Assistance clientèle d&#39;Adobe si vous souhaitez y accéder.

Experience Data Model (XDM) est un ensemble standard de schémas de données dans lesquels des données peuvent être ingérées afin d’être utilisées avec les solutions et produits Adobe Experience Platform.

La création et la gestion des schémas XDM sont possibles à l’aide d’une API dédiée ou de l’interface utilisateur XDM.

## Espace de travail XDM {#xdm-workspace}

L’espace de travail XDM permet d’afficher, de créer et d’étendre des schémas de données.

Pour accéder à l’interface utilisateur XDM, ouvrez Adobe Experience Platform. Accédez à la fenêtre Modèle de données pour créer ou étendre un schéma XDM.

Consultez la [documentation complète sur l’espace de travail XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=fr).

![](assets/aep_xdmworkspace.png)

## API XDM {#xdm-api}

Vous pouvez effectuer les actions suivantes via l’API de schéma XDM :

* afficher la liste des schémas existants ;
* afficher un schéma spécifique et étendre un schéma existant ;
* ajouter des champs à une extension ;
* créer et mettre à jour un nouveau schéma ;
* afficher des descripteurs de schéma ;
* créer, mettre à jour et supprimer des descripteurs de schéma.

Tous les détails relatifs à la manipulation des appels d’API sont disponibles dans le [Guide du développeur](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=fr).
