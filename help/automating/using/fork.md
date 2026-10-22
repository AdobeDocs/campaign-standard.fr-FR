---
title: Branchement
description: L'activité Branchement permet de créer des transitions sortantes afin de lancer plusieurs activités en parallèle.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1a5e1ecd-b3f1-4dbe-a816-12d27a3bc0f7
TQID: 'https://experienceleague.adobe.com/1-9VY3TjBBHAb-7bFikis3Ue5eWy5KXKSR4hXxXDLwc'
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
source-wordcount: '216'
ht-degree: 100%
---
# Branchement{#fork}

## Description {#description}

![](assets/fork.png)

L&#39;activité **[!UICONTROL Branchement]** permet de créer des transitions sortantes afin de lancer plusieurs activités en parallèle.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Branchement]** permet de réaliser, au sein d&#39;un même workflow, plusieurs exécutions distinctes de manière indépendante.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Branchement]** dans votre workflow.
1. Connectez-la à la suite d&#39;autres activités telles que des requêtes.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Définissez le nombre de transitions sortantes en créant, supprimant ou dupliquant des transitions. Vous pouvez également leur attribuer un nom et un libellé.
1. Validez le paramétrage de l’activité et enregistrez le workflow.

## Exemple {#example}

L&#39;exemple suivant montre l&#39;intersection de deux activités de requête visant à cibler les profils de la base Adobe Campaign qui sont des femmes habitant à Paris. Le branchement permet alors de lancer en parallèle plusieurs activités : d&#39;une part une sauvegarde d&#39;audience permettant de garder en mémoire la population calculée, et d&#39;autre part une segmentation permettant d&#39;envoyer deux emails différents avec du contenu ciblé pour chaque segment. Le premier email est envoyé aux femmes parisiennes dont l&#39;âge est compris entre 18 et 40 ans et le second aux femmes parisiennes de plus de 40 ans.

![](assets/wkf_fork_example.png)
