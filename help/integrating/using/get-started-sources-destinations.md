---
title: Commencer avec les sources et les destinations
description: En savoir plus sur les sources et les destinations d’Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
TQID: 'https://experienceleague.adobe.com/r1rASYXuo-xeKH80eZVYG-jUhxy93GuTa8CIDyouSNY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 100%
---
# Commencer avec les sources et les destinations {#rtcdp}

## À propos des sources et des destinations

Adobe Experience Platform vous permet de partager des données entre Campaign Standard et Adobe Real-time Customer Data Platform (RTCDP). Vous pouvez ainsi cibler des audiences Adobe Experience Platform dans vos workflows Campaign, puis renvoyer à Adobe Real-time Customer Data Platform les données liées à ces audiences, notamment les envois, les ouvertures et les clics.

* Avec **Destinations**, ingérez les audiences d&#39;Adobe Experience Platform dans Campaign Standard. Il est ainsi possible d&#39;activer vos données connues et inconnues pour vos opérations marketing.
* Avec **Sources**, exportez les données de Campaign Standard (par exemple, envois, ouvertures, clics) dans Adobe Experience Platform. Vous pouvez ainsi centraliser les données collectées à partir de sources disparates dans un seul et même endroit, et utiliser les informations acquises pour faire davantage.


>[!IMPORTANT]
>
>Lorsque vous utilisez cette fonctionnalité, gardez à l&#39;esprit les limites du stockage SFTP, les limites du stockage en base de données, et les limites des profils actifs en fonction de votre contrat Adobe Campaign.

Pour un aperçu plus détaillé d’Adobe Real-time Customer Data Platform, des destinations et des sources, consultez les pages suivantes :

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=fr)
* [Documentation sur les destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=fr)
* [Documentation sur les sources](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=fr)

## Connecter Campaign Standard à Adobe Experience Platform

Pour pouvoir partager des données entre Adobe Experience Platform et Campaign Standard, vous devez d&#39;abord connecter Adobe Campaign en tant que **destination** et connecter votre enregistrement AWS S3 ou Azure Blob en tant que **source** dans la Adobe Experience Platform.

Une fois les connecteurs configurés, vous pouvez configurer un import ou un export de données dans Campaign Standard à l’aide de workflows.

![](assets/rtcdp-schema.png)

Pour plus d&#39;informations sur la configuration de ces processus d&#39;import et d&#39;export, reportez-vous aux sections suivantes :

* [Ingérer des audiences Adobe Experience Platform dans Campaign](../../integrating/using/ingest-aep-data.md)
* [Exporter des données de Campaign vers Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
