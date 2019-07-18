---
title: Interface des workflows
seo-title: Interface des workflows
description: Interface des workflows
seo-description: Découvrez l'interface et les options pour créer, éditer et exécuter un workflow.
page-status-flag: jamais activé
uuid: aafe 33 ed-fa 07-4 dd 9-825 e -242099334 f 1 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatisation
content-type: référence
topic-tags: about-workflows-and-data-management
discoiquuid: 147 fbb 0 d -17 d 2-444 b-a 215-9 ad 14179 c 549
context-tags: workflow, main ; flux de travail, présentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff0b995533f34dd8eab7a9a82feaab3ceed4ff29

---


# Interface des workflows{#workflow-interface}

Dans le cadre de vos campagnes et programmes, vous pouvez créer des workflows afin de gérer des processus complets.

L'écran d'édition d'un workflow se compose des éléments suivants:

* la [palette](../../automating/using/workflow-interface.md#palette), référençant les activités disponibles
* l'[espace de travail](../../automating/using/workflow-interface.md#workspace), dans lequel les activités sont paramétrées et organisées
* la [barre d'actions](../../automating/using/workflow-interface.md#action-bar), composée des boutons permettant d'interagir avec le workflow et ses composants.
* les [actions rapides](../../automating/using/workflow-interface.md#quick-actions), qui s'affichent autour d'une activité sélectionnée, permettant d'interagir avec cette dernière.

![](assets/wkf_overview.png)

## Palette {#palette}

La palette se situe sur la partie gauche de l'écran. Toutes les activités disponibles sont réparties en plusieurs catégories:

* [Ciblage](../../automating/using/about-targeting-activities.md) : activités spécifiques à la réalisation d'un ciblage, à la manipulation et au filtrage de populations
* [Exécution](../../automating/using/about-execution-activities.md) : activités spécifiques à l'organisation et à l'exécution du workflow
* [Canaux](../../automating/using/about-channel-activities.md) : activités représentant les différents canaux de communication disponibles
* [Data Management (ETL)](../../automating/using/about-data-management-activities.md) : activités de manipulation des données

Pour utiliser une activité de la palette dans votre workflow, faites-la glisser jusqu'à l'emplacement de votre choix dans l'espace de travail.

Vous devez paramétrer chaque activité ajoutée depuis la palette avant de démarrer le workflow.

![](assets/workflow_palette.png)

## Espace de travail {#workspace}

L'espace de travail est la zone centrale de l'éditeur de workflows. C'est dans cette zone que vous pouvez déposer vos activités, les relier entre-elles à l'aide de transitions et les paramétrer.

Pour lier deux activités, déplacez l'extrémité de la transition de la première activité jusqu'à l'activité suivante. Vous pouvez aussi déplacer la seconde activité sur l'extrémité de la flèche de la première. Si vous déplacez l'une des deux activités, elles restent liées.

Les transitions qui suivent les activités traitant des données contiennent les populations intermédiaires. Vous pouvez y accéder si vous avez coché l'option **[!UICONTROL Conserver les résultats intermédiaires]** dans la section **Exécution]des propriétés du workflow.[!UICONTROL **

Lorsqu'une activité est sélectionnée, des actions rapides s'affichent autour de celle-ci et permettent d'interagir avec. Par exemple pour paramétrer une activité, sélectionnez-la puis ouvrez-la à l'aide du bouton ![ des actions rapides.](assets/edit_darkgrey-24px_table.png)

Certains raccourcis sont activés uniquement au niveau de l'espace de travail :

* sélection de plusieurs activités et transitions en dessinant une zone autour de ces dernières.
* touche **Ctrl** + clic gauche pour sélectionner plusieurs activités et/ou transitions.
* touche **Entrée** pour accéder au détail de l'activité ou de la transition actuellement sélectionnée.
* touche **Suppr** pour supprimer l'activité actuellement sélectionnée.
* touches **Ctrl + C** pour copier les activités sélectionnées et touches **Ctrl + V** pour les coller dans l'espace de travail.

![](assets/workflow_workspace.png)

## La barre d'actions {#action-bar}

En fonction des éléments sélectionnés dans l'espace de travail ou du statut d'exécution du workflow, les boutons disponibles dans la barre d'actions peuvent différer.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Ouvrir activitypermet]**<br/>de modifier les propriétés du processus.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Startlance]**<br/>le processus.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pausepauses]**<br/>le processus.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stopinterromts workflow execution]**<br/>. Sans possibilité de reprendre à l'endroit où il s'est arrêté.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restartredémarre]**<br/>le processus.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Journal et tasksopens]**<br/>le journal d'exécution du flux de travaux.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Activer multi-selectionactive le mode]**<br/>de sélection multiple. Le workflow doit comporter au minimum deux activités.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Désactiver multi-selectiondésactive]**<br/>le mode de sélection multiple.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Ouvrir la transition Ouvre]**<br/>la transition sélectionnée.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal executionréactive]**<br/>la sélection si elle a été désactivée ou marquée comme mise en pause.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Exécution suspendedpauses]**<br/>le workflow à l'activité sélectionnée.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL Aucun executiondésactive]**<br/>l'activité.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Supprimer la selectionsupprime]**<br/>les activités sélectionnées.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copier le sélectioncopie]**<br/>les activités sélectionnées.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Pastepastes]**<br/>les activités qui ont été copiées.

## Actions rapides {#quick-actions}

Lorsqu'une activité est sélectionnée, des boutons d'actions rapides apparaissent autour de l'activité, permettant d'interagir avec cette dernière.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Ouvrir activityopen]**<br/>l'activité sélectionnée.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copier le sélectioncopie]**<br/>de l'activité sélectionnée.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Ouvrez les options avancées de l'activité pour les]**<br/>options avancées de l'activité de remise par courrier électronique ou par SMS sélectionnée.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal executionréactive]**<br/>la sélection si elle a été désactivée ou marquée comme mise en pause.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Exécution suspendedpauses]**<br/>le workflow à l'activité sélectionnée.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL Aucun executiondésactive]**<br/>l'activité.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Executionforce immédiatement]**<br/>le traitement immédiat de la sélection. Ce bouton est uniquement disponible pour les activités <span class="uicontrol">Planificateur</span> et <span class="uicontrol">Attente</span>.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Supprimer la selectionsupprime]**<br/>les activités sélectionnées.

## Duplication des activités de workflow {#duplicating-workflow-activities}

L'espace de travail permet de dupliquer des activités de workflow en les copiant et en les collant dans le même workflow ou dans un autre depuis une même instance de Campaign.

Une fois une activité dupliquée, l'ensemble de sa configuration est conservée. Pour les activités de diffusion (email, SMS, notification push, etc.), l'objet de diffusion associé à l'activité est dupliqué.

>[!NOTE]
>
>Les activités de workflow ne peuvent pas être dupliquées d'une instance à une autre. Les activités des workflows techniques ne peuvent pas être dupliquées.

Pour dupliquer une activité, procédez comme suit :

1. Sélectionnez l'activité, puis cliquez sur le bouton **[!UICONTROL Copier la sélection]dans les actions rapides.**

   Vous pouvez également utiliser le raccourci clavier **Ctrl + C**.

   ![](assets/wkf_copypaste1.png)

1. Cliquez avec le bouton droit dans l'espace de travail du workflow cible, puis cliquez sur le bouton **[!UICONTROL Coller].**

   Vous pouvez également utiliser le raccourci clavier **Ctrl + V**.

   ![](assets/wkf_copypaste2.png)

1. L'activité est dupliquée avec tous les paramètres configurés initialement.

Il est également possible de copier-coller plusieurs activités, ce qui permet de dupliquer un workflow entier.

Pour ce faire, sélectionnez les activités en traçant une zone autour d'elles. Cliquez ensuite sur le bouton **[!UICONTROL Copier la sélection]** dans la barre d'actions (ou appuyez sur **Ctrl + C**). Vous pouvez coller les activités à l'emplacement de votre choix.

![](assets/wkf_copypaste3.png)

