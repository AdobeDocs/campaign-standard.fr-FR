---
title: Intersection
seo-title: Intersection
description: Intersection
seo-description: L'activité Intersection permet de ne conserver que les éléments communs aux différentes populations entrantes dans l'activité.
page-status-flag: jamais activé
uuid: a 60 f 9811-0158-44 b 3-952 b -392685 c 006 cc
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatisation
content-type: référence
topic-tags: ciblage-activités
discoiquuid: 7 a 107 d 6 b-edc 3-44 c 3-bbb 7-ba 3 dec 8 e 43 f 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Intersection{#intersection}

## Description {#description}

![](assets/intersection.png)

L'activité **[!UICONTROL Intersection]permet de ne conserver que les éléments communs aux différentes populations entrantes dans l'activité.**

## Contexte d'utilisation {#context-of-use}

L'activité **[!UICONTROL Intersection]est essentiellement utilisée afin de réaliser un filtrage supplémentaire sur les populations des transitions entrantes.**

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Intersection]dans votre workflow.**
1. Connectez-la à la suite d'autres activités telles que des requêtes.
1. Sélectionnez l'activité puis ouvrez-la à l'aide du bouton ![, disponible dans les actions rapides qui s'affichent.](assets/edit_darkgrey-24px.png)
1. Select the **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Uniquement les clés : mode par défaut.]** L'activité ne conserve qu'un élément lorsque des éléments provenant des différentes transitions entrantes ont la même clé.
   * **[!UICONTROL Toutes les colonnes communes : les données sont réconciliées sur la base des colonnes communes aux transitions entrantes.]** Vous devez alors sélectionner l'ensemble principal qui servira de base de comparaison. Cette option peut être utilisée notamment si les dimensions de ciblage des populations entrantes sont différentes.
   * **[!UICONTROL Une sélection de colonnes]** : sélectionnez cette option pour définir la liste des colonnes sur lesquelles sera appliquée la réconciliation des données. Vous devez d'abord sélectionner l'ensemble principal (celui qui contient les données sources), puis définir les champs à utiliser pour la jointure.

1. Cochez la case **[!UICONTROL Utiliser uniquement les données additionnelles communes]si vous souhaitez ne conserver que les données additionnelles présentes dans toutes les transitions entrantes.**
1. Si besoin, gérez les [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) de l'activité afin d'accéder à des options avancées sur la population transmise en sortie.
1. Validez le paramétrage de l'activité et enregistrez le workflow.

## Exemple {#example}

L'exemple suivant montre l'intersection de deux activités de requête visant à filtrer respectivement les profils de la base Adobe Campaign dont l'âge est compris entre 18 et 27 ans et ceux dont l'adresse email renseignée est valide.

![](assets/wkf_intersection_example.png)

