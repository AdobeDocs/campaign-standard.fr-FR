---
solution: Campaign Standard
product: campaign
title: Requête incrémentale
description: L'activité Requête incrémentale permet de filtrer et d'extraire une population d'éléments de la base de données Adobe Campaign.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 100%

---


# Requête incrémentale{#incremental-query}

## Description {#description}

![](assets/incremental.png)

L&#39;activité **[!UICONTROL Requête incrémentale]** permet de filtrer et d&#39;extraire une population d&#39;éléments de la base de données Adobe Campaign. A chaque nouvelle exécution de cette activité, les résultats des exécutions précédentes sont exclus. Cela permet de ne cibler que les éléments nouveaux.

Vous pouvez définir des **[!UICONTROL Données additionnelles]** pour la population ciblée via un onglet dédié. Ces données sont stockées dans des colonnes additionnelles et sont exploitables uniquement pour le workflow en cours.

L’activité utilise l’outil d’édition de requêtes, dont le fonctionnement est détaillé dans une [section dédiée](../../automating/using/editing-queries.md#about-query-editor).

## Contexte d’utilisation {#context-of-use}

Une **[!UICONTROL Requête incrémentale]** doit être associée à un **[!UICONTROL Planificateur]** afin de définir la récurrence de l&#39;exécution du workflow, et donc de la requête.

L&#39;onglet **[!UICONTROL Données traitées]**, spécifique à cette activité, permet de visualiser les résultats des exécutions précédentes de l&#39;activité, le cas échéant.

L&#39;activité **[!UICONTROL Requête incrémentale]** peut être utilisée dans plusieurs cas d&#39;utilisation type :

* segmentation d’individus afin de définir la cible d’un message, une audience, etc.

* export des données.

   Vous pouvez utiliser une activité **[!UICONTROL Requête incrémentale]** pour exporter de manière régulière les nouveaux logs vers des fichiers. Cet export peut s&#39;avérer utile si vous souhaitez par exemple utiliser les données des logs dans des outils de Business Intelligence ou de reporting externes. Un exemple complet est présenté dans la section [Exporter des logs](../../automating/using/exporting-logs.md).

**Rubriques connexes :**

* [Cas pratique : requête incrémentale sur les abonnés à un service](../../automating/using/incremental-query-on-subscribers.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Requête incrémentale]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Si vous souhaitez effectuer la requête sur une autre ressource que celle des profils, accédez à l’onglet **[!UICONTROL Propriétés]** de l’activité et sélectionnez une **[!UICONTROL Ressource]** et une **[!UICONTROL Dimension de ciblage]**.

   La **[!UICONTROL Ressource]** permet d’affiner les filtres affichés dans la palette tandis que la **[!UICONTROL Dimension de ciblage]**, contextuelle à la ressource sélectionnée, correspond au type de population que vous souhaitez obtenir (profils identifiés, diffusions, etc.).

1. Depuis l’onglet **[!UICONTROL Cible]**, effectuez votre requête en définissant et combinant des règles.
1. Dans l&#39;onglet **[!UICONTROL Données traitées]**, sélectionnez le mode incrémental que vous souhaitez utiliser pour les prochaines exécutions du workflow :

   * **[!UICONTROL Exclure les résultats des exécutions précédentes]** : à chaque nouvelle exécution, les résultats des exécutions précédentes sont exclus.
   * **[!UICONTROL Utiliser un champ date]** : les prochaines exécutions tiennent compte uniquement des résultats pour lesquels le champ date sélectionné est postérieur ou égal à la date de dernière exécution de l&#39;activité **[!UICONTROL Requête incrémentale]**. Vous pouvez sélectionner un champ date associé à la ressource sélectionnée dans l&#39;onglet **[!UICONTROL Propriétés]**. Ce mode offre de meilleures performances lors de l&#39;interrogation de ressources volumineuses telles que des données de log.

      Après la première exécution du workflow, vous pouvez voir dans cet onglet la date de dernière exécution qui sera utilisée pour la prochaine exécution. Cette date est automatiquement mise à jour à chaque exécution du workflow. Vous avez toujours la possibilité de remplacer cette valeur en en saisissant une autre qui répond à vos besoins.
   >[!NOTE]
   >
   >Le mode **[!UICONTROL Utiliser un champ date]** offre davantage de flexibilité selon le champ date sélectionné. Par exemple, si le champ sélectionné correspond à une date de modification, le mode du champ date vous permet de récupérer les données qui ont été récemment mises à jour. L&#39;autre mode, en revanche, exclut simplement les enregistrements qui ont déjà été ciblés dans une exécution précédente, même s&#39;ils ont été modifiés depuis la dernière exécution du workflow.

   ![](assets/incremental_query_usedatefield.png)

1. Vous pouvez définir des **[!UICONTROL Données additionnelles]** pour la population ciblée via un onglet dédié. Ces données sont stockées dans des colonnes additionnelles et sont exploitables uniquement pour le workflow en cours. Vous pouvez notamment ajouter des données provenant des tables de la base Adobe Campaign liées à la dimension de ciblage de la requête. Consultez la section [Enrichir des données](../../automating/using/query.md#enriching-data).
1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Enrichir des données {#enriching-data}

De la même manière que pour une requête, vous pouvez enrichir les données issues d&#39;une **[!UICONTROL Requête incrémentale]**. Consultez la section [Enrichir des données](../../automating/using/query.md#enriching-data).
