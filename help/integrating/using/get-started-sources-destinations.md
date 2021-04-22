---
solution: Campaign Standard
product: campaign
title: Prise en main des sources et destinations
description: En savoir plus sur les sources et les destinations Adobe Experience Platform.
audience: integrating
content-type: reference
feature: Sources et destinations
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
translation-type: ht
source-git-commit: 27cbb2f8a202b3361122fdadfcfe8d0820aa3cb3
workflow-type: ht
source-wordcount: '310'
ht-degree: 100%

---

# Prise en main des sources et destinations {#rtcdp}

## À propos des sources et des destinations

Adobe Experience Platform vous permet de partager des données entre Campaign Standard et Adobe Real-time Customer Data Platform (RTCDP). Cela vous permet de cibler des audiences Adobe Experience Platform dans vos workflows Campaign, puis de renvoyer à Adobe Real-time Customer Data Platform les données liées à ces audiences, telles que les envois, les ouvertures et les clics.

* Avec **Destinations**, ingérez les audiences d&#39;Adobe Experience Platform dans Campaign Standard. Cela vous permet d’activer vos données connues et inconnues pour vos campagnes marketing.
* Avec **Sources**, exportez les données de Campaign Standard (par exemple, envois, ouvertures, clics) dans Adobe Experience Platform. Cela vous permet de centraliser les données que vous collectez à partir de sources disparates dans un seul et même endroit, et d&#39;utiliser les connaissances acquises pour faire davantage.


>[!IMPORTANT]
>
>Lorsque vous utilisez cette fonctionnalité, gardez à l&#39;esprit les limites du stockage SFTP, les limites du stockage en base de données, et les limites des profils actifs en fonction de votre contrat Adobe Campaign.

Pour un aperçu plus détaillé de Adobe Real-time Customer Data Platforml, des destinations et des sources, consultez les pages suivantes :

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html)
* [Documentation sur les destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html)
* [Documentation sur les sources](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html)

## Connecter Campaign Standard à Adobe Experience Platform

Pour pouvoir partager des données entre Adobe Experience Platform et Campaign Standard, vous devez d&#39;abord connecter Adobe Campaign en tant que **destination** et connecter votre enregistrement AWS S3 ou Azure Blob en tant que **source** dans la Adobe Experience Platform.

Une fois les connecteurs configurés, vous pouvez configurer un import ou un export de données dans Campaign Standard à l’aide de workflows.

![](assets/rtcdp-schema.png)

Pour plus d&#39;informations sur la configuration de ces processus d&#39;import et d&#39;export, reportez-vous aux sections suivantes :

* [Ingérer des audiences Adobe Experience Platform dans Campaign](../../integrating/using/ingest-aep-data.md)
* [Export de données de Campaign vers Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
