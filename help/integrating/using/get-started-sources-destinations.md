---
title: Prise en main des sources et des destinations
description: En savoir plus sur les sources et les destinations d’Adobe Experience Platform.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '307'
ht-degree: 100%

---

# Prise en main des sources et des destinations {#rtcdp}

## À propos des sources et des destinations

Adobe Experience Platform permet de partager des données entre Campaign Standard et Adobe Real-time Customer Data Platform (RTCDP). Vous pouvez ainsi cibler des audiences Adobe Experience Platform dans vos workflows Campaign, puis renvoyer à Adobe Real-time Customer Data Platform les données liées à ces audiences, notamment les envois, les ouvertures et les clics.

* Avec **Destinations**, ingérez les audiences d’Adobe Experience Platform dans Campaign Standard. Il est ainsi possible d’activer vos données connues et inconnues pour vos campagnes marketing.
* Avec **Sources**, exportez les données de Campaign Standard (par exemple, envois, ouvertures, clics) dans Adobe Experience Platform. Vous pouvez ainsi centraliser les données collectées à partir de sources disparates dans un seul et même endroit, et utiliser les connaissances acquises pour faire davantage.


>[!IMPORTANT]
>
>Lorsque vous utilisez cette fonctionnalité, gardez à l&#39;esprit les limites du stockage SFTP, les limites du stockage en base de données, et les limites des profils actifs en fonction de votre contrat Adobe Campaign.

Pour un aperçu plus détaillé d’Adobe Real-time Customer Data Platform, des destinations et des sources, consultez les pages suivantes :

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=fr)
* [Documentation sur les destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=fr)
* [Documentation sur les sources](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=fr)

## Connecter Campaign Standard à Adobe Experience Platform

Pour pouvoir partager des données entre Adobe Experience Platform et Campaign Standard, vous devez d’abord connecter Adobe Campaign en tant que **destination** et connecter votre emplacement de stockage AWS S3 ou Azure Blob en tant que **source** dans Adobe Experience Platform.

Une fois les connecteurs configurés, vous pouvez configurer un import ou un export de données dans Campaign Standard à l’aide de workflows.

![](assets/rtcdp-schema.png)

Pour plus d’informations sur la configuration de ces processus d’import et d’export, reportez-vous aux sections suivantes :

* [Ingérer des audiences Adobe Experience Platform dans Campaign](../../integrating/using/ingest-aep-data.md)
* [Exporter des données de Campaign vers Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
