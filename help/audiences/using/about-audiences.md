---
title: A propos des audiences
description: Découvrez comment créer des audiences depuis une requête, une liste ou un fichier et comment les importer à partir d'Adobe Experience Cloud.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# A propos des audiences{#about-audiences}

Une audience est une liste de profils reposant sur des règles et des attributs.

Adobe Campaign permet de créer vos audiences manuellement à travers des requêtes ou automatiquement via des workflows dédiés. Il est également possible d'utiliser des audiences partagées à partir d'Adobe Experience Cloud. Toutes les audiences sont regroupées dans une liste accessible à partir de la vignette **[!UICONTROL Audiences]** de la page d'accueil d'Adobe Campaign ou à partir du lien **[!UICONTROL Audiences]**.

![](assets/audience_1.png)

Vous pouvez manipuler différents types d'audiences dans Adobe Campaign. Le type d'une audience correspond à la manière dont elle a été créée :

* **[!UICONTROL Requête]** : indique que l'audience a été créée à partir d'une [requête](../../automating/using/editing-queries.md#about-query-editor) sur les données de la base Adobe Campaign depuis la liste des audiences. Les audiences définies par une requête sont recalculées à chaque utilisation ultérieure.
* **[!UICONTROL Liste]** : indique que l'audience est une liste figée de profils. Ces listes sont créées dans un [workflow](../../automating/using/discovering-workflows.md) lorsque la dimension des données est connue au moment de la sauvegarde de l'audience. Par exemple après des activités de ciblage (notamment **[!UICONTROL Requête]** ) ou après la réconciliation de données importées depuis un fichier.
* **[!UICONTROL Fichier]** : indique que l'audience été créée à partir d'un [import de fichier](../../automating/using/load-file.md) dans un workflow et que la dimension des données était inconnue au moment de la sauvegarde de l'audience.
* **[!UICONTROL Experience Cloud]** : indique que l'audience a été importée depuis Adobe Experience Cloud. Cette option n'est disponible que si la fonctionnalité de partage d'audiences a été configurée. Pour plus d'informations, voir [Import d'une audience depuis Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

