---
title: Interface des workflows
description: Découvrez l’interface et les options pour créer, éditer et exécuter un workflow.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
role: Data Architect
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: ea524bdcef0324c7fc4b9da0bb443b6abc66a23a
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 100%

---

# Interface des workflows{#workflow-interface}

Dans le cadre de vos campagnes et programmes, vous pouvez créer des workflows afin de gérer des processus complets.

L’écran d’édition d’un workflow se compose des éléments suivants :

* La [palette](#palette), référençant les activités disponibles.
* L’[espace de travail](#workspace), dans lequel les activités sont paramétrées et organisées.
* La [barre d’actions](#action-bar), composée des boutons permettant d’interagir avec le workflow et ses composants.
* Les [actions rapides](#quick-actions), qui s’affichent autour d’une activité sélectionnée, permettant d’interagir avec cette dernière.

![](assets/wkf_overview.png)

![](assets/do-not-localize/how-to-video.png) [Découvrir comment créer un workflow en vidéo](#video)

## Palette {#palette}

La palette se situe sur la partie gauche de l’écran. Toutes les activités disponibles sont réparties en plusieurs catégories :

* [Ciblage](../../automating/using/about-targeting-activities.md) : activités spécifiques à la réalisation d’un ciblage, à la manipulation et au filtrage de populations
* [Exécution](../../automating/using/about-execution-activities.md) : activités spécifiques à l’organisation et à l’exécution du workflow
* [Canaux](../../automating/using/about-channel-activities.md) : activités représentant les différents canaux de communication disponibles
* [Data Management (ETL)](../../automating/using/about-data-management-activities.md) : activités de manipulation des données

Pour utiliser une activité de la palette dans votre workflow, faites-la glisser jusqu’à l’emplacement de votre choix dans l’espace de travail.

Vous devez paramétrer chaque activité ajoutée depuis la palette avant de démarrer le workflow.

![](assets/workflow_palette.png)

## Espace de travail {#workspace}

L’espace de travail est la zone centrale de l’éditeur de workflows. C’est dans cette zone que vous pouvez déposer vos activités, les relier entre-elles à l’aide de transitions et les paramétrer.

Pour lier deux activités, déplacez l’extrémité de la transition de la première activité jusqu’à l’activité suivante. Vous pouvez aussi déplacer la seconde activité sur l’extrémité de la flèche de la première. Si vous déplacez l’une des deux activités, elles restent liées.

Les transitions qui suivent les activités traitant des données contiennent les populations intermédiaires. Vous pouvez y accéder si vous avez coché l’option **[!UICONTROL Conserver les résultats intermédiaires]** dans la section **[!UICONTROL Exécution]** des propriétés du workflow.

>[!CAUTION]
>
>Cette option consomme beaucoup d’espace disque. De plus, elle a été conçue pour vous aider à créer un workflow et à garantir une configuration et un comportement corrects. Laissez-la décochée sur les instances de production.


Lorsqu’une activité est sélectionnée, des actions rapides s’affichent autour de celle-ci et permettent d’interagir avec. Par exemple pour paramétrer une activité, sélectionnez-la puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px_table.png) des actions rapides.

Certains raccourcis sont activés uniquement au niveau de l’espace de travail :

* Sélection de plusieurs activités et transitions en dessinant une zone autour de ces dernières.
* Touche **Ctrl** + clic gauche pour sélectionner plusieurs activités et/ou transitions.
* Touche **Entrée** pour accéder au détail de l’activité ou de la transition actuellement sélectionnée.
* Touche **Suppr** pour supprimer l’activité actuellement sélectionnée.
* Touches **Ctrl + C** pour copier les activités sélectionnées et touches **Ctrl + V** pour les coller dans l’espace de travail.

![](assets/workflow_workspace.png)

## La barre d&#39;actions  {#action-bar}

En fonction des éléments sélectionnés dans l’espace de travail ou du statut d’exécution du workflow, les boutons disponibles dans la barre d’actions peuvent différer.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Ouvrir l’activité]**<br/>Permet d’éditer les propriétés du workflow.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Démarrer]**<br/>Démarre le workflow.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Mettre en pause]**<br/>Met le workflow en pause.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Arrêter]**<br/>Interrompt l’exécution du workflow. Sans possibilité de reprendre à l’endroit où il s’est arrêté.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Redémarrer]**<br/>Redémarre le workflow.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Journal et tâches]**<br/>Ouvre le log d’exécution du workflow.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Activer le mode multi-sélection]**<br/>Active le mode multi-sélection. Le workflow doit comporter au minimum deux activités.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Désactiver le mode multi-sélection]**<br/>Désactive le mode multi-sélection.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Ouvrir la transition]**<br/>Ouvre la transition sélectionnée.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Exécution normale]**<br/>Réactive la sélection après qu’elle a été marquée comme en pause ou désactivée.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Exécution suspendue]**<br/>Met le workflow en pause à l’activité sélectionnée.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL Pas d’exécution]**<br/>Désactive l’activité.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Supprimer la sélection]**<br/>Supprime les activités sélectionnées.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copier la sélection]**<br/>Copie les activités sélectionnées.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Coller]**<br/>Colle les activités qui ont été copiées.

## Actions rapides {#quick-actions}

Lorsqu’une activité est sélectionnée, des boutons d’actions rapides apparaissent autour de l’activité, permettant d’interagir avec cette dernière.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Ouvrir l’activité]**<br/>Ouvre l’activité sélectionnée.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copier la sélection]**<br/>Copie l’activité sélectionnée.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Ouvrir les options avancées de l’activité]**<br/>Ouvre les options avancées de l’activité de diffusion email ou SMS sélectionnée.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Exécution normale]**<br/>Réactive la sélection après qu’elle a été marquée comme en pause ou désactivée.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Exécution suspendue]**<br/>Met le workflow en pause à l’activité sélectionnée.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL Pas d’exécution]**<br/>Désactive l’activité.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Traitement anticipé]**<br/>Lance la sélection en traitement anticipé. Ce bouton est uniquement disponible pour les activités <span class="uicontrol">Planificateur</span> et <span class="uicontrol">Attente</span>.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Supprimer la sélection]**<br/>Supprime les activités sélectionnées.

## Duplication des activités de workflow {#duplicating-workflow-activities}

L’espace de travail permet de dupliquer des activités de workflow en les copiant et en les collant dans le même workflow ou dans un autre depuis une même instance de Campaign.

Une fois une activité dupliquée, l’ensemble de sa configuration est conservée. Pour les activités de diffusion (email, SMS, notification push, etc.), l’objet de diffusion associé à l’activité est dupliqué.

>[!NOTE]
>
>Les activités de workflow ne peuvent pas être dupliquées d’une instance à une autre. Les activités des workflows techniques ne peuvent pas être dupliquées.

Pour dupliquer une activité, procédez comme suit :

1. Sélectionnez l’activité, puis cliquez sur le bouton **[!UICONTROL Copier la sélection]** dans les actions rapides.

   Vous pouvez également utiliser le raccourci clavier **Ctrl + C**.

   ![](assets/wkf_copypaste1.png)

1. Cliquez avec le bouton droit dans l’espace de travail du workflow cible, puis cliquez sur le bouton **[!UICONTROL Coller]**.

   Vous pouvez également utiliser le raccourci clavier **Ctrl + V**.

   ![](assets/wkf_copypaste2.png)

1. L’activité est dupliquée avec tous les paramètres configurés initialement.

Il est également possible de copier-coller plusieurs activités, ce qui permet de dupliquer un workflow entier.

Pour ce faire, sélectionnez les activités en traçant une zone autour d’elles. Cliquez ensuite sur le bouton **[!UICONTROL Copier la sélection]** dans la barre d’actions (ou appuyez sur **Ctrl + C**). Vous pouvez coller les activités à l’emplacement de votre choix.

![](assets/wkf_copypaste3.png)

## Tutoriel vidéo {#video}

Cette vidéo montre comment créer un workflow.

>[!VIDEO](https://video.tv.adobe.com/v/23937?quality=12)

D’autres vidéos pratiques sur Campaign Standard sont disponibles [ici](https://experienceleague.adobe.com/fr/docs/campaign-standard-learn/tutorials/overview).
