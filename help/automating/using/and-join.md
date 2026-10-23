---
title: Rendez-vous
description: L'activité Rendez-vous permet de synchroniser plusieurs branches d'exécution d'un workflow.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b03c6df3-0104-4900-9468-46824d62e0a6
TQID: 'https://experienceleague.adobe.com/ydaYzPE9SwLuC-d4nVSaFgLLp-R0Kuceq7hUI89aN1Y'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%
---
# Rendez-vous{#and-join}

## Description {#description}

![](assets/and_join.png)

L&#39;activité **[!UICONTROL Rendez-vous]** permet de synchroniser plusieurs branches d&#39;exécution d&#39;un workflow.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Rendez-vous]** ne déclenche sa transition sortante qu&#39;une fois toutes les transitions entrantes activées, c&#39;est-à-dire quand toutes les activités précédentes sont terminées.

## Configuration {#configuration}

1. Placez dans votre workflow plusieurs activités telles que des requêtes pour former au moins deux branches d&#39;exécution distinctes.
1. Placez une activité **[!UICONTROL Rendez-vous]** dans votre workflow.
1. Connectez-la à la suite des différentes branches que vous souhaitez synchroniser.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Sélectionnez l&#39;ensemble principal à conserver dans la transition sortante. Si vous ne choisissez aucun ensemble, la population transmise en sortie de l&#39;activité est aléatoire.
1. Validez le paramétrage de l’activité et enregistrez le workflow.

## Exemple {#example}

L&#39;exemple suivant montre l&#39;exécution de deux branches d&#39;un workflow avant qu&#39;elles ne se rejoignent avec l&#39;activité **[!UICONTROL Rendez-vous]**. L&#39;extraction de fichier ne pourra avoir lieu que lorsque les trois transitions entrantes de l&#39;activité **[!UICONTROL Rendez-vous]** seront activées.

![](assets/wkf_and-join_example.png)
