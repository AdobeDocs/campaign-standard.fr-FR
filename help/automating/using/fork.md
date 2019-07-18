---
title: Branchement
seo-title: Branchement
description: Branchement
seo-description: L'activité Branchement permet de créer des transitions sortantes afin de lancer plusieurs activités en parallèle.
page-status-flag: jamais activé
uuid: e 4 eaf 69 b -84 ee -4 f 79-8 b 80-99284697 cd 2 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatisation
content-type: référence
topic-tags: exécution-activités
discoiquuid: f 8 ffe 7 af-e 18 c -4599-8 fd 0-fcd 192565323
context-tags: fork, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Branchement{#fork}

## Description {#description}

![](assets/fork.png)

L'activité **[!UICONTROL Branchement]permet de créer des transitions sortantes afin de lancer plusieurs activités en parallèle.**

## Contexte d'utilisation {#context-of-use}

L'activité **[!UICONTROL Branchement]permet de réaliser, au sein d'un même workflow, plusieurs exécutions distinctes de manière indépendante.**

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Branchement]dans votre workflow.**
1. Connectez-la à la suite d'autres activités telles que des requêtes.
1. Sélectionnez l'activité puis ouvrez-la à l'aide du bouton ![, disponible dans les actions rapides qui s'affichent.](assets/edit_darkgrey-24px.png)
1. Définissez le nombre de transitions sortantes en créant, supprimant ou dupliquant des transitions. Vous pouvez également leur attribuer un nom et un libellé.
1. Validez le paramétrage de l'activité et enregistrez le workflow.

## Exemple {#example}

L'exemple suivant montre l'intersection de deux activités de requête visant à cibler les profils de la base Adobe Campaign qui sont des femmes habitant à Paris. Le branchement permet alors de lancer en parallèle plusieurs activités : d'une part une sauvegarde d'audience permettant de garder en mémoire la population calculée, et d'autre part une segmentation permettant d'envoyer deux emails différents avec du contenu ciblé pour chaque segment. Le premier email est envoyé aux femmes parisiennes dont l'âge est compris entre 18 et 40 ans et le second aux femmes parisiennes de plus de 40 ans.

![](assets/wkf_fork_example.png)

