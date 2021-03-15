---
solution: Campaign Standard
product: campaign
title: Chevauchement de l'exécution de workflows planifiés
description: Découvrez comment empêcher le chevauchement de l’exécution de workflows planifiés.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 99%

---


# Chevauchement de l&#39;exécution de workflows planifiés{#preventing-overlapping-execution-of-scheduled-workflows}

## À propos du chevauchement de l’exécution de workflows planifiés

Dans Campaign Standard, le moteur de workflow garantit l’exécution par un seul processus d’une instance de workflow. Le blocage d’activités telles que les imports, les requêtes à exécution longue ou les écritures dans la base de données empêchent l’exécution simultanée de toute autre tâche.

D’un autre côté, les activités non bloquantes ne bloquent pas l’exécution d’autres tâches (il s’agit en général d’activités qui attendent un événement, comme l’activité **[!UICONTROL Planificateur]**).

Cela peut conduire à un scénario dans lequel un workflow basé sur une planification est susceptible de commencer à s’exécuter même lorsque l’exécution précédente de ce workflow n’est pas encore terminée, et entraîner ainsi des problèmes de données inattendus.

Par conséquent, lorsque vous concevez un workflow planifié qui inclut plusieurs activités, vous devez vous assurer que ce workflow n’est pas replanifié tant qu’il n’est pas terminé. Pour ce faire, vous devez configurer votre workflow afin d’empêcher son exécution si une ou plusieurs tâches d’une exécution précédente sont toujours en attente.

## Configuration du workflow

Pour vérifier si une ou plusieurs tâches d’une exécution de workflow précédente sont toujours en attente, vous devez utiliser une activité **[!UICONTROL Requête]** et une activité **[!UICONTROL Test]**.

1. Ajoutez une activité **[!UICONTROL Requête]** après l’activité **[!UICONTROL Planificateur]**, puis configurez-la comme suit.

1. Remplacez la ressource de l’activité par **[!UICONTROL WorkflowTaskDetail]** afin qu’elle cible les tâches en cours du workflow.

   ![](assets/scheduled-wkf-resource.png)

1. Configurez la requête avec les règles suivantes :

   ![](assets/scheduled-wkf-query.png)

   * La première règle filtre la tâche en cours (query2) ainsi que la tâche de planification suivante (schedule2) du workflow en cours.

      >[!NOTE]
      >
      >Lorsqu’une activité **[!UICONTROL Planificateur]** démarre, elle ajoute immédiatement une autre tâche de planification à exécuter à la prochaine heure planifiée et débute le workflow. Par conséquent, il est important de filtrer la requête ainsi que les tâches de planification lors de la recherche de tâches en attente dans une exécution précédente.

   * La deuxième règle détermine si les tâches d’une exécution précédente du workflow sont toujours actives (en attente), ce qui correspond au statut d’exécution 0.

1. Ajoutez une activité **[!UICONTROL Test]** afin de déterminer le nombre de tâches en attente renvoyées par l’activité **[!UICONTROL Requête]**. Pour ce faire, configurez deux transitions sortantes.

   ![](assets/scheduled-wkf-test.png)

   * La première transition reprend l’exécution du workflow s’il n’existe pas de tâches en attente,
   * la seconde transition annule l’exécution du workflow s’il existe des tâches en attente.

   ![](assets/scheduled-wkf-workflow.png)

Vous pouvez maintenant configurer le reste de votre workflow en fonction de vos besoins. Si l’exécution du workflow est annulée en raison de tâches en attente, le workflow peut suivre ces étapes en s’exécutant de nouveau selon la planification. Ainsi, l’exécution du workflow ne se poursuivra que s’il n’existe aucune tâche active (en attente) issue d’une exécution précédente.
