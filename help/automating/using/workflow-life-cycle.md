---
title: Cycle de vie d'un workflow
description: En savoir plus sur le cycle de vie d’un workflow
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '200'
ht-degree: 100%

---


# Cycle de vie d&#39;un workflow {#life-cycle}

Le cycle de vie d’un workflow comporte trois grandes étapes, chacune d’elle étant associée à un statut et à une couleur :

* **En édition** (gris)

   C’est la phase de conception initiale d’un nouveau workflow (voir [Créer un workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). Un tel workflow n’est pas encore pris en charge par le serveur, il peut donc être modifié sans risque.

* **En cours** (bleu)

   Une fois la phase de conception terminée, le workflow peut être démarré et il est pris en charge par le serveur.

* **Terminé** (vert)

   Un workflow est terminé lorsqu’il n’a plus de tâche en cours ou lorsque l’exécution a explicitement été arrêtée.

Une fois qu’il a été démarré, un workflow peut également se voir attribuer deux autres statuts :

* **Avertissement** (jaune)

   Le workflow n’a pas pu se terminer ou a été mis en pause à l’aide des boutons ![](assets/pause_darkgrey-24px.png) ou ![](assets/check_pause_darkgrey-24px.png).

* **En erreur** (rouge)

   Une erreur est survenue pendant l’exécution du workflow. Ce dernier est arrêté et une action est requise de la part de l’utilisateur. Pour connaître l’origine de l’erreur, utilisez le bouton ![](assets/printpreview_darkgrey-24px.png) afin d’accéder au journal du workflow (voir [Contrôle](../../automating/using/monitoring-workflow-execution.md)).

La liste des activités marketing permet d’afficher tous les workflows ainsi que leur statut. Voir à ce sujet la section [Gérer les activités marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
