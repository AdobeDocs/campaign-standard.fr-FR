---
solution: Campaign Standard
product: campaign
title: Rendez-vous
description: L'activité Rendez-vous permet de synchroniser plusieurs branches d'exécution d'un workflow.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '183'
ht-degree: 100%

---


# Rendez-vous{#and-join}

## Description {#description}

![](assets/and_join.png)

L&#39;activité **[!UICONTROL Rendez-vous]** permet de synchroniser plusieurs branches d&#39;exécution d&#39;un workflow.

## Contexte d’utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Rendez-vous]** ne déclenche sa transition sortante qu&#39;une fois toutes les transitions entrantes activées, c&#39;est-à-dire quand toutes les activités précédentes sont terminées.

## Configuration {#configuration}

1. Placez dans votre workflow plusieurs activités telles que des requêtes pour former au moins deux branches d&#39;exécution distinctes.
1. Placez une activité **[!UICONTROL Rendez-vous]** dans votre workflow.
1. Connectez-la à la suite des différentes branches que vous souhaitez synchroniser.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Sélectionnez l&#39;ensemble principal à conserver dans la transition sortante. Si vous ne choisissez aucun ensemble, la population transmise en sortie de l&#39;activité est aléatoire.
1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Exemple {#example}

L&#39;exemple suivant montre l&#39;exécution de deux branches d&#39;un workflow avant qu&#39;elles ne se rejoignent avec l&#39;activité **[!UICONTROL Rendez-vous]**. L&#39;extraction de fichier ne pourra avoir lieu que lorsque les trois transitions entrantes de l&#39;activité **[!UICONTROL Rendez-vous]** seront activées.

![](assets/wkf_and-join_example.png)

