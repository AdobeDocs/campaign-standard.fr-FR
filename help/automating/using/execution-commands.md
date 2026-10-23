---
title: Commandes d’exécution
description: Découvrez comment utiliser les commandes d’exécution des workflows.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
TQID: 'https://experienceleague.adobe.com/jDS-3Rz--h6N17JfbijrtOaj8jVDPDW9HiOoiLwPHSY'
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
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 100%
---
# Commandes d’exécution {#execution-commands}

Les icônes de la barre d’actions permettent de lancer, de tracker et de modifier l’exécution d’un workflow. Voir [La barre d’actions](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Les actions disponibles sont les suivantes :

**Début**

Le bouton ![](assets/play_darkgrey-24px.png) permet de lancer l’exécution d’un workflow, qui prend alors le statut **En cours** (bleu). Si le workflow était en pause, il s’agit d’une reprise, sinon il s’agit d’un démarrage et les activités initiales sont alors activées.

>[!NOTE]
>
>Le démarrage est un processus asynchrone : la demande est enregistrée et sera traitée dès que possible par le moteur d’exécution de workflow.

**Pause**

Le bouton ![](assets/pause_darkgrey-24px.png) a pour effet de mettre l’exécution en pause. Le workflow prend le statut **Avertissement** (jaune). Aucune nouvelle activité ne sera activée jusqu’à la prochaine reprise, mais les opérations en cours ne sont pas suspendues.

**Stopper**

Le bouton ![](assets/stop_darkgrey-24px.png) arrête un workflow en cours d’exécution, qui prend alors le statut **Terminé** (vert). Les opérations en cours sont interrompues, si possible, et les imports ou requêtes SQL en cours sont immédiatement annulées. Il n’est pas possible de reprendre à l’endroit où le workflow s’est arrêté.

**Redémarrer**

Le bouton ![](assets/pauseplay_darkgrey-24px.png) consiste à arrêter, puis redémarrer un workflow. Dans la plupart des cas, cela permet de redémarrer plus vite. C’est également utile pour automatiser le redémarrage lorsque l’arrêt prend un certain temps, car le bouton ![](assets/play_darkgrey-24px.png) n’est disponible que lorsque l’arrêt est effectif.

Lorsqu’une ou plusieurs activités d’un workflow sont sélectionnées, d’autres actions sont possibles :

**Traitement anticipé**

Le bouton ![](assets/pending_darkgrey-24px.png) permet de lancer dès que possible la ou les activités sélectionnées en attente.

**Exécution normale**

Le bouton ![](assets/check_darkgrey-24px.png) réactive la ou les activités mises en pause ou désactivées.

**Exécution suspendue**

Le bouton ![](assets/check_pause_darkgrey-24px.png) met le workflow en pause à l&#39;activité sélectionnée : cette tâche ainsi que toutes celles qui lui succèdent (dans la même branche) ne sont pas exécutées.

**Pas d’exécution**

Le bouton ![](assets/checkdisable.png) désactive la ou les activités sélectionnées.

>[!NOTE]
>
>Les actions permettant d’agir sur une activité en particulier sont également disponibles depuis les actions rapides, qui s’affichent lors de la sélection d’une activité.
