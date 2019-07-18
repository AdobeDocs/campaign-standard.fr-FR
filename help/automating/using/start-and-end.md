---
title: Début et Fin
seo-title: Début et Fin
description: Début et Fin
seo-description: Les activités Début et Fin permettent respectivement de marquer graphiquement les points de départ et de fin d'un workflow.
page-status-flag: jamais activé
uuid: 146 b 6337-122 c -453 d -8 ffd -5 c 157 db 29217
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatisation
content-type: référence
topic-tags: exécution-activités
discoiquuid: a 0 a 8 a 725-8 ede -4626-9798-b 86924 b 58 beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Début et Fin{#start-and-end}

## Description {#description}

![](assets/start.png)

![](assets/end.png)

Les activités **[!UICONTROL Début]** et **Fin]permettent respectivement de marquer graphiquement les points de départ et de fin d'un workflow.[!UICONTROL **

## Contexte d'utilisation {#context-of-use}

L'exécution d'un workflow démarre par des activités sans transition entrante, et s'arrête lorsqu'il n'y a plus de tâche en cours. Il est néanmoins possible d'ajouter des activités **[!UICONTROL Début]** et **Fin]pour marquer graphiquement les points de départ et de fin d'un workflow,[!UICONTROL ** en cas de workflow relativement complexe par exemple.

Il est recommandé d'utiliser une activité **[!UICONTROL Fin]au lieu de laisser la dernière transition d'un workflow telle quelle pour s'assurer que le workflow se termine correctement.**

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Début]** ou **Fin]dans votre workflow.[!UICONTROL **
1. Connectez l'activité **[!UICONTROL Début]** en amont d'autres activités telles que des requêtes, et l'activité **Fin]à la suite d'une série d'activités.[!UICONTROL **
1. Sélectionnez l'activité puis ouvrez-la à l'aide du bouton ![, disponible dans les actions rapides qui s'affichent.](assets/edit_darkgrey-24px.png)
1. Vous pouvez paramétrer l'objet **Fin** pour qu'il interrompe toutes les tâches en cours du workflow, y compris celles qui ne sont pas terminées. Pour cela, sélectionnez l'option correspondante.
1. Validez le paramétrage de l'activité et enregistrez le workflow.

## Déclenchement d'un autre workflow {#triggering-another-workflow}

Vous pouvez déclencher un autre workflow à l'aide de l'onglet **[!UICONTROL Signal externe]** d'une activité **Fin.** Consultez la section [Signal externe](../../automating/using/external-signal.md).

## Exemple {#example}

L'exemple suivant montre l'exécution d'un workflow complexe avec une activité **[!UICONTROL Début]** et plusieurs activités **Fin.** La case **[!UICONTROL Arrêter toutes les tâches en cours]** a été cochée pour la première activité **Fin.** Une fois que la tâche correspondante sera terminée, l'ensemble du workflow sera interrompu : l'effet sera le même que si l'on avait sélectionné le bouton ![](assets/stop_darkgrey-24px.png) (voir la section [La barre d'actions](../../automating/using/workflow-interface.md#action-bar)).

![](assets/wkf_start_end_example.png)

