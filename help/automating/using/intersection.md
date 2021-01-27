---
solution: Campaign Standard
product: campaign
title: Intersection
description: L'activité Intersection permet de ne conserver que les éléments communs aux différentes populations entrantes dans l'activité.
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 100%

---


# Intersection{#intersection}

## Description {#description}

![](assets/intersection.png)

L&#39;activité **[!UICONTROL Intersection]** permet de ne conserver que les éléments communs aux différentes populations entrantes dans l&#39;activité.

## Contexte d’utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Intersection]** est essentiellement utilisée afin de réaliser un filtrage supplémentaire sur les populations des transitions entrantes.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Intersection]** dans votre workflow.
1. Connectez-la à la suite d&#39;autres activités telles que des requêtes.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Sélectionnez le **[!UICONTROL Type de réconciliation]** :

   * **[!UICONTROL Uniquement les clés]** : mode par défaut. L&#39;activité ne conserve qu&#39;un élément lorsque des éléments provenant des différentes transitions entrantes ont la même clé.
   * **[!UICONTROL Toutes les colonnes communes]** : les données sont réconciliées sur la base des colonnes communes aux transitions entrantes. Vous devez alors sélectionner l&#39;ensemble principal qui servira de base de comparaison. Cette option peut être utilisée notamment si les dimensions de ciblage des populations entrantes sont différentes.
   * **[!UICONTROL Une sélection de colonnes]** : sélectionnez cette option pour définir la liste des colonnes sur lesquelles sera appliquée la réconciliation des données. Vous devez d&#39;abord sélectionner l&#39;ensemble principal (celui qui contient les données sources), puis définir les champs à utiliser pour la jointure.

1. Cochez la case **[!UICONTROL Utiliser uniquement les données additionnelles communes]** si vous souhaitez ne conserver que les données additionnelles présentes dans toutes les transitions entrantes.
1. Si besoin, gérez les [Transitions](../../automating/using/activity-properties.md) de l&#39;activité afin d&#39;accéder à des options avancées sur la population transmise en sortie.
1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Exemple {#example}

L&#39;exemple suivant montre l&#39;intersection de deux activités de requête visant à filtrer respectivement les profils de la base Adobe Campaign dont l&#39;âge est compris entre 18 et 27 ans et ceux dont l&#39;adresse email renseignée est valide.

![](assets/wkf_intersection_example.png)

