---
title: Cycle de vie d'un workflow
description: En savoir plus sur le cycle de vie d’un workflow
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
TQID: https://experienceleague.adobe.com/nWv8hOZa2JQgiO2CEnffriIqb6czIA7Gh0AwWCTwRAA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 200
ht-degree: 100%

---

# Cycle de vie d&#39;un workflow {#life-cycle}

Le cycle de vie d’un workflow comporte trois grandes étapes, chacune d’elle étant associée à un statut et à une couleur :

* **En édition** (gris)

  C’est la phase de conception initiale d’un nouveau workflow (voir [Créer un workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). Un tel workflow n’est pas encore pris en charge par le serveur, il peut donc être modifié sans risque.

* **En cours** (bleu)

  Une fois la phase de conception terminée, le workflow peut être démarré et il est pris en charge par le serveur.

* **Terminé** (vert)

  Un workflow est terminé lorsqu’il n’a plus de tâche en cours ou quand un opérateur ou une opératrice a explicitement mis fin à l’instance.

Une fois qu’il a été démarré, un workflow peut également se voir attribuer deux autres statuts :

* **Avertissement** (jaune)

  Le workflow n’a pas pu se terminer ou a été mis en pause à l’aide des boutons ![](assets/pause_darkgrey-24px.png) ou ![](assets/check_pause_darkgrey-24px.png).

* **En erreur** (rouge)

  Une erreur est survenue pendant l’exécution du workflow. Ce dernier est arrêté et une action est requise de la part de l’utilisateur. Pour connaître l&#39;origine de l&#39;erreur, utilisez le bouton ![](assets/printpreview_darkgrey-24px.png) afin d&#39;accéder au log du workflow (voir [Contrôle](../../automating/using/monitoring-workflow-execution.md)).

La liste des activités marketing permet d’afficher tous les workflows ainsi que leur statut. Voir à ce sujet la section [Gérer les activités marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
