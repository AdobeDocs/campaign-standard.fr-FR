---
title: À propos des audiences
description: Découvrez comment créer des audiences depuis une requête, une liste ou un fichier et comment les importer à partir d’Adobe Experience Cloud.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Audiences
role: User
level: Beginner
exl-id: f99987d8-b1bf-4ec7-885c-fb511f4168ac
TQID: 'https://experienceleague.adobe.com/NPcDi1kh8Ye1Y14CAwVxBLW-0qwHnpFRUQ2WYj7BJbI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 100%
---
# À propos des audiences{#about-audiences}

Une audience est une liste de profils reposant sur des règles et des attributs.

Adobe Campaign permet de créer vos audiences manuellement à travers des requêtes ou automatiquement via des workflows dédiés. Il est également possible d’utiliser des audiences partagées à partir d’Adobe Experience Cloud. Toutes les audiences sont regroupées dans une liste accessible à partir de la carte **[!UICONTROL Audiences]** de la page d&#39;accueil d&#39;Adobe Campaign ou à partir du lien **[!UICONTROL Audiences]**.

![](assets/audience_1.png)

Vous pouvez manipuler différents types d’audiences dans Adobe Campaign. Le type d’une audience correspond à la manière dont elle a été créée :

* **[!UICONTROL Requête]** : indique que l’audience a été créée à l’aide d’une [requête](../../automating/using/editing-queries.md#about-query-editor) sur les données de la base Adobe Campaign via la liste des audiences. Les audiences définies par une requête sont recalculées à chaque utilisation ultérieure.
* **[!UICONTROL Liste]** : indique que l’audience est une liste figée de profils. Ces listes sont créées dans un [workflow](../../automating/using/get-started-workflows.md) lorsque la dimension des données est connue au moment de la sauvegarde de l’audience. Par exemple après des activités de ciblage (notamment **[!UICONTROL Requête]**) ou après la réconciliation de données importées depuis un fichier.
* **[!UICONTROL Fichier]** : indique que l’audience été créée à partir d’un [import de fichier](../../automating/using/load-file.md) dans un workflow et que la dimension des données était inconnue au moment de la sauvegarde de l’audience.
* **[!UICONTROL Experience Cloud]** : indique que l’audience a été importée depuis Adobe Experience Cloud. Cette option n’est disponible que si la fonctionnalité de partage d’audiences a été configurée. Pour plus d’informations, voir [Import d’une audience depuis Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)
