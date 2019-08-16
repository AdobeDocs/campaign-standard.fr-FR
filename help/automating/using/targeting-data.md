---
title: Cibler les données
seo-title: Cibler les données
description: Cibler les données
seo-description: Découvrez les différentes manières de cibler et sélectionner les données dont vous avez besoin.
page-status-flag: never-activated
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Cibler les données{#targeting-data}

## Sélectionner les données {#selecting-data}

Vous pouvez sélectionner les données à l'aide des activités suivantes :

* L'activité **[!UICONTROL Requête]** permet de filtrer et d'extraire une population d'éléments de la base de données Adobe Campaign. Consultez la section [Requête](../../automating/using/query.md).
* L'activité **[!UICONTROL Requête incrémentale]** permet de filtrer et d'extraire une population d'éléments de la base de données Adobe Campaign. A chaque nouvelle exécution de cette activité, les résultats des exécutions précédentes sont exclus. Cela vous permet de cibler uniquement les nouveaux éléments. Voir la section [Requête incrémentale](../../automating/using/incremental-query.md).
* L'activité **[!UICONTROL Lecture d'audience]** vous permet de récupérer une audience existante et de les affiner en appliquant des conditions de filtrage additionnel. Voir la section [Lecture d'audience](../../automating/using/read-audience.md).

## Segmenter des données {#segmenting-data}

Adobe Campaign permet de procéder à des traitements d'ensembles sur des données en entrée. Il est ainsi possible de regrouper plusieurs populations, d'en exclure une partie ou de ne conserver que les données communes entre plusieurs cibles.

* L'activité **[!UICONTROL Union]** permet de regrouper le résultat de plusieurs activités dans une même cible. Voir la section [Union](../../automating/using/union.md).
* L'activité **[!UICONTROL Intersection]** permet de ne conserver que les éléments communs aux différentes populations entrantes dans l'activité. Voir la section [Intersection](../../automating/using/intersection.md).
* L'activité **[!UICONTROL Exclusion]** permet d'exclure des éléments d'une population selon certains critères. Voir la section [Exclusion](../../automating/using/exclusion.md).
* L'activité **[!UICONTROL Segmentation]** permet de créer un ou plusieurs segments à partir d'une population calculée par des activités placées en amont. En sortie de l'activité, ils peuvent être traités dans une seule transition ou dans des transitions distinctes. Consultez la section [Segmentation](../../automating/using/segmentation.md).

## Enrichir des données {#enriching-data}

Les données identifiées et collectées peuvent être enrichies, regroupées et manipulées afin d'optimiser la construction de la cible. Vous pouvez simplifier et optimiser les processus de ciblage en incluant des données qui ne sont pas modélisées dans le datamart.

L'onglet **[!UICONTROL Données additionnelles]** des activités **[!UICONTROL Requête]** et **[!UICONTROL Requête incrémentale]** permet d'enrichir les données ciblées par la requête et de transmettre ces données aux activités suivantes du workflow, où elles pourront être exploitées. Il est notamment possible d'ajouter :

* des données simples.
* des agrégats.
* des collections

