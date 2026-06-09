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
TQID: https://experienceleague.adobe.com/1-9VY3TjBBHAb-7bFikis3Ue5eWy5KXKSR4hXxXDLwc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 216
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
