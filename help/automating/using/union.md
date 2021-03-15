---
solution: Campaign Standard
product: campaign
title: Union
description: L'activité Union permet de regrouper le résultat de plusieurs activités dans une même cible.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: union,main
feature: Workflows
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 99%

---


# Union{#union}

## Description {#description}

![](assets/union.png)

L&#39;activité **[!UICONTROL Union]** permet de regrouper le résultat de plusieurs activités dans une même cible.

>[!NOTE]
>
>Les ensembles ne doivent pas nécessairement être homogènes.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Union]** est utilisée afin de réunir les populations des transitions entrantes dans le cadre d&#39;une segmentation, d&#39;une définition d&#39;audience ou en vue de la préparation de la cible d&#39;un message par exemple.

**Rubriques connexes :**

* [Cas pratique : union sur deux audiences affinées](../../automating/using/union-on-two-refined-audiences.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Union]** dans votre workflow.
1. Connectez-la à la suite d&#39;autres activités telles que des requêtes.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Sélectionnez le **[!UICONTROL Type de réconciliation]** pour définir la gestion des doublons issus de la confrontation des populations entrantes :

   * **[!UICONTROL Uniquement les clés]** : c&#39;est le mode par défaut. L&#39;activité ne conserve qu&#39;un élément lorsque des éléments provenant des différentes transitions entrantes ont la même clé. Cette option ne peut être utilisée que si les populations en entrée sont homogènes.
   * **[!UICONTROL Toutes les colonnes communes]** : les données sont réconciliées sur la base de toutes les colonnes communes aux transitions entrantes. Vous devez alors sélectionner l&#39;ensemble principal qui sera conservé en cas de doublon. Cette option peut être utilisée notamment si les dimensions de ciblage des populations entrantes sont différentes.
   * **[!UICONTROL Une sélection de colonnes]** : sélectionnez cette option pour définir la liste des colonnes sur lesquelles sera appliquée la réconciliation des données. Vous devez d&#39;abord sélectionner l&#39;ensemble principal (celui qui contient les données sources), puis les colonnes à utiliser pour la jointure.

1. Cochez la case **[!UICONTROL Utiliser uniquement les données additionnelles communes]** si vous souhaitez ne conserver que les données additionnelles présentes dans toutes les transitions entrantes.
1. Cochez la case **[!UICONTROL Limiter la taille de la population générée]** si vous souhaitez limiter la taille de la population à un nombre donné d&#39;enregistrements, que vous indiquez dans le champ **[!UICONTROL Nombre maximum d&#39;enregistrements]**.
1. Si besoin, gérez les [Transitions](../../automating/using/activity-properties.md) de l&#39;activité afin d&#39;accéder à des options avancées sur la population calculée.
1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Exemple {#example}

L&#39;exemple suivant montre le résultat de deux activités de requête visant à regrouper les profils de la base Adobe Campaign dont l&#39;âge est compris entre 18 et 27 ans et ceux dont l&#39;âge est compris entre 34 et 40 ans. Le résultat contient l&#39;ensemble des profils des deux requêtes ou le nombre d&#39;enregistrements maximum défini lors du paramétrage, le cas échéant.

![](assets/wkf_union_example.png)