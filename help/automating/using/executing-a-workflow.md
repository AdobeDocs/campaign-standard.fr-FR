---
title: Exécuter un workflow
description: Découvrez comment exécuter et contrôler un workflow.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e8302a8d3ba914781bd332bc318b65d88afc6d94

---


# Exécuter un workflow{#executing-a-workflow}

## A propos de l&#39;exécution d&#39;un workflow {#about-workflow-execution}

Un workflow est toujours démarré manuellement. Une fois lancé, il peut toutefois rester inactif selon les informations spécifiées via un [planificateur](../../automating/using/scheduler.md).

>[!CAUTION]
>
> Adobe recommande aux clients de hiérarchiser les exécutions de workflows et d&#39;exécuter au maximum 20 workflows simultanément de façon à obtenir constamment des performances maximales sur leur instance. Il est possible de planifier plus de 20 exécutions de workflows simultanées ; elles s&#39;exécuteront en séquence par défaut. Vous pouvez ajuster les paramètres par défaut pour le nombre maximal d&#39;exécutions de workflows simultanées en envoyant un ticket à l&#39;assistance client.

Les actions relatives à l&#39;exécution (lancement, arrêt, pause, etc.) sont des processus **asynchrones** : la commande est enregistrée et sera effective dès que le serveur est disponible pour l&#39;appliquer.

En général, dans un workflow, le résultat de chaque activité est transmis à l&#39;activité suivante via une transition, représentée par une flèche.

Une transition est flottante si elle n&#39;est pas rattachée à une activité de destination.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Un workflow contenant des transitions flottantes peut être exécuté : lors de l&#39;activation d&#39;une telle transition, l&#39;exécution génère un avertissement et se trouve suspendue, mais aucune erreur n&#39;est entraînée. Il est ainsi possible de démarrer un workflow sans en avoir terminé la conception et de le compléter au fur et à mesure.

Lorsqu&#39;une activité a été exécutée, le nombre d&#39;enregistrements transmis dans la transition est affiché au-dessus de cette dernière.

![](assets/wkf_transition_count.png)

Vous pouvez ouvrir les transitions afin de vérifier que les données transmises sont correctes pendant ou après l&#39;exécution du workflow. Vous pouvez visualiser les données présentes ainsi que leur structure.

Pour pouvoir accéder au détail des transitions intermédiaires (autres que la dernière transition du workflow), To be able to access the results of the preceding activities, you need to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties, before starting the workflow.

>[!NOTE]
>
>Cette option consomme beaucoup de mémoire et a été conçue pour vous aider à construire un workflow et à vous assurer que sa configuration et son comportement sont corrects. Laissez-la décochée sur les instances de production.

When a transition is open, you can edit its **[!UICONTROL Label]** or link a **[!UICONTROL Segment code]** to it. Pour cela, éditez les champs correspondants et validez vos modifications.

Using Campaign Standard REST APIs, you can **start**, **pause**, **resume** and **stop** a workflow. Vous trouverez plus d&#39;informations et d&#39;exemples d&#39;appels REST dans la [documentation de l&#39;API.](../../api/using/controlling-a-workflow.md)

## Cycle de vie {#life-cycle}

Le cycle de vie d&#39;un workflow comporte trois grandes étapes, chacune d&#39;elle étant associée à un statut et à une couleur :

* **En édition** (gris)

   C&#39;est la phase de conception initiale d&#39;un nouveau workflow (voir [Créer un workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). Un tel workflow n&#39;est pas encore pris en charge par le serveur, il peut donc être modifié sans risque.

* **En cours** (bleu)

   Une fois la phase de conception terminée, le workflow peut être démarré et il est pris en charge par le serveur.

* **Terminé** (vert)

   Un workflow est terminé lorsqu&#39;il n&#39;a plus de tâche en cours ou lorsque l&#39;exécution a explicitement été arrêtée.

Une fois qu&#39;il a été démarré, un workflow peut également se voir attribuer deux autres statuts :

* **Avertissement** (jaune)

   Le workflow n&#39;a pas pu se terminer ou a été mis en pause à l&#39;aide des boutons ![](assets/pause_darkgrey-24px.png) ou ![](assets/check_pause_darkgrey-24px.png).

* **En erreur** (rouge)

   Une erreur est survenue pendant l&#39;exécution du workflow. Ce dernier est arrêté et une action est requise de la part de l&#39;utilisateur. Pour connaître l&#39;origine de l&#39;erreur, utilisez le bouton ![](assets/printpreview_darkgrey-24px.png) afin d&#39;accéder au journal du workflow (voir [Contrôle](#monitoring)).

La liste des activités marketing permet d&#39;afficher tous les workflows ainsi que leur statut. Voir à ce sujet la section [Gérer les activités marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

## Commandes d&#39;exécution   {#execution-commands}

Les icônes de la barre d&#39;actions permettent de lancer, de tracker et de modifier l&#39;exécution d&#39;un workflow. Voir [La barre d&#39;actions](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Les actions disponibles sont les suivantes :

**Début**

Le bouton ![](assets/play_darkgrey-24px.png) permet de lancer l&#39;exécution d&#39;un workflow, qui prend alors le statut **En cours** (bleu). Si le workflow était en pause, il s&#39;agit d&#39;une reprise, sinon il s&#39;agit d&#39;un démarrage et les activités initiales sont alors activées.

>[!NOTE]
>
>Le démarrage est un processus asynchrone : la demande est enregistrée et sera traitée dès que possible par le moteur d&#39;exécution de workflow.

**Pause**

Le bouton ![](assets/pause_darkgrey-24px.png) a pour effet de mettre l&#39;exécution en pause. Le workflow prend le statut **Avertissement** (jaune). Aucune nouvelle activité ne sera activée jusqu&#39;à la prochaine reprise, mais les opérations en cours ne sont pas suspendues.

**Stopper**

Le bouton ![](assets/stop_darkgrey-24px.png) arrête un workflow en cours d&#39;exécution, qui prend alors le statut **Terminé** (vert). Les opérations en cours sont interrompues, si possible, et les imports ou requêtes SQL en cours sont immédiatement annulées. Il n&#39;est pas possible de reprendre à l&#39;endroit où le workflow s&#39;est arrêté.

**Redémarrer**

Le bouton ![](assets/pauseplay_darkgrey-24px.png) consiste à arrêter, puis démarrer un workflow. Dans la plupart des cas, cela permet de redémarrer plus vite. C&#39;est également utile pour automatiser le redémarrage lorsque l&#39;arrêt prend un certain temps, car le bouton ![](assets/play_darkgrey-24px.png) n&#39;est disponible que lorsque l&#39;arrêt est effectif.

Lorsqu&#39;une ou plusieurs activités d&#39;un workflow sont sélectionnées, d&#39;autres actions sont possibles :

**Traitement anticipé**

Le bouton ![](assets/pending_darkgrey-24px.png) permet de lancer dès que possible la ou les activités sélectionnées en attente.

**Exécution normale**

Le bouton ![](assets/check_darkgrey-24px.png) réactive la ou les activités mises en pause ou désactivées.

**Exécution suspendue**

Le bouton ![](assets/check_pause_darkgrey-24px.png) met le workflow en pause à l&#39;activité sélectionnée : cette tâche ainsi que toutes celles qui lui succèdent (dans la même branche) ne sont pas exécutées.

**Pas d&#39;exécution**

Le bouton ![](assets/checkdisable.png) désactive la ou les activités sélectionnées.

>[!NOTE]
>
>Les actions permettant d&#39;agir sur une activité en particulier sont également disponibles depuis les actions rapides, qui s&#39;affichent lors de la sélection d&#39;une activité.

## Contrôle   {#monitoring}

L&#39;icône ![](assets/printpreview_darkgrey-24px.png) permet d&#39;accéder au menu Journal et tâches du workflow.

L&#39;historique d&#39;un workflow est conservé pendant la durée que vous indiquez dans les options d&#39;exécution du workflow (voir [Propriétés des workflows](#workflow-properties)). Pendant cette durée, tous les messages sont donc conservés, même après un redémarrage. Si vous ne voulez pas conserver les messages d&#39;une exécution précédente, vous devez purger l&#39;historique en cliquant sur le bouton ![](assets/delete_darkgrey-24px.png).

The **[!UICONTROL Log]** tab contains the execution history of all the activities or any selected activities. Il répertorie par ordre chronologique les opérations réalisées et les erreurs d&#39;exécution.

![](assets/wkf_execution_4.png)

The **[!UICONTROL Tasks]** tab details the execution sequencing of the activities. Cliquez sur une tâche pour obtenir plus d&#39;informations.

![](assets/wkf_execution_5.png)

Dans ces deux listes :

* Cliquez sur le compteur pour obtenir le nombre total des activités selon le filtrage appliqué. Le comptage est affiché par défaut si le nombre d&#39;éléments dans la liste est inférieur à 30.
* The **[!UICONTROL Configure list]** button allows you to choose the information displayed, define the column order, and sort the list.
* Vous pouvez utiliser des filtres pour trouver plus rapidement les informations dont vous avez besoin. Utilisez le champ de recherche pour rechercher du texte spécifique dans les noms des activités de workflow (par exemple &quot;requête&quot;) et les logs.

## Gestion des erreurs   {#error-management}

Lorsqu&#39;une erreur se produit, le workflow se met en pause et l&#39;activité qui était en cours d&#39;exécution lorsque l&#39;erreur s&#39;est produite clignote alors en rouge.

Le statut du workflow passe au rouge et l&#39;erreur est consignée dans le journal.

Vous pouvez paramétrer le workflow pour qu&#39;il ne se mette pas en pause et continue son exécution en cas d&#39;erreur. To do this, go to the workflow properties via the ![](assets/edit_darkgrey-24px.png) button and, in the **[!UICONTROL Execution]** section, select the **Ignore** option in the **In case of error** field.

Dans ce cas, la tâche en erreur est abandonnée. Ce mode est particulièrement adapté aux workflows conçus pour permettre de retenter l&#39;opération ultérieurement (actions périodiques).

>[!NOTE]
>
>Vous pouvez appliquer ce paramétrage au niveau de chaque activité. Pour cela, sélectionnez l&#39;activité de votre choix puis ouvrez-là à l&#39;aide de l&#39;action rapide ![](assets/edit_darkgrey-24px.png) et sélectionnez le mode de gestion des erreurs dans l&#39;onglet **Options d&#39;exécution.** Voir [Options d&#39;exécution d&#39;une activité](#activity-execution-options).

Dans les propriétés [du](#workflow-properties)processus, d’autres options liées à la gestion des erreurs sont disponibles.

![](assets/wkf_execution_error.png)

Les options possibles sont les suivantes :

* **[!UICONTROL Supervisors]**: vous permet de définir le groupe de personnes à notifier (courrier électronique et notification in-app) si le flux de travaux rencontre une erreur. Si aucun groupe n&#39;est défini, personne ne sera notifié. Pour plus d&#39;informations sur les notifications d&#39;Adobe Campaign, voir [Notifications Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: vous permet de spécifier l’action à exécuter en cas d’erreur du  . Deux options sont disponibles :

   * **Suspendre le processus** : le workflow est automatiquement suspendu. Le statut du workflow est alors **En erreur** et la couleur qui lui est associée passe au rouge. Lorsque le problème est résolu, relancez le workflow.
   * **Ignorer** : l&#39;activité n&#39;est pas exécutée, de même que, par voie de conséquence, toutes celles qui lui succèdent (dans la même branche). Cela peut s&#39;avérer utile dans le cas de tâches récurrentes. Si la branche comporte un planificateur placé en amont, celui-ci se déclenchera normalement à sa prochaine date d&#39;exécution.

* **[!UICONTROL Consecutive errors]** : vous permet de définir un certain nombre d’erreurs consécutives autorisées avant que l’exécution du flux de travaux ne soit automatiquement suspendue.

   * Si le nombre indiqué est **[!UICONTROL 0]** ou tant que ce nombre n&#39;est pas atteint, les activités qui rencontrent des erreurs sont ignorées. Les autres branches du workflow sont exécutées normalement.

   * If the number specified is reached, the whole of the workflow is suspended and becomes **[!UICONTROL Erroneous]**. Si des superviseurs ont été définis, ils sont automatiquement notifié par un email. Voir [Notifications d&#39;Adobe Campaign](../../administration/using/sending-internal-notifications.md).

## Propriétés d&#39;exécution   {#workflow-properties}

To modify a workflow&#39;s execution options, use the ![](assets/edit_darkgrey-24px.png) button to access the workflow properties and select the **[!UICONTROL Execution]** section.

![](assets/wkf_execution_6.png)

Les options possibles sont les suivantes :

* **[!UICONTROL Default affinity]**: ce champ vous permet de forcer un workflow ou un workflow  à s&#39;exécuter sur une machine particulière.

* **[!UICONTROL History in days]**: indique le nombre de jours après lesquels l’historique doit être purgé. L&#39;histoire se compose de tous les éléments liés comme les journaux, les , les et les . La valeur par défaut est de 30 jours pour les modèles de processus prêts à l’emploi.

   La purge de l&#39;historique est effectuée par le workflow technique de nettoyage de base de données, qui est exécuté par défaut tous les jours (voir [de](../../administration/using/technical-workflows.md)de).

   >[!IMPORTANT]
   >
   >Si le **[!UICONTROL History in days]** champ n’est pas renseigné, sa valeur sera considérée comme &quot;1&quot;, ce qui signifie que l’historique sera purgé après 1 jour.

* **[!UICONTROL Save SQL queries in the log]**: vous permet d&#39;enregistrer les  SQL du flux de travail dans les journaux.

* ***[!UICONTROL Keep interim results]**: check this option if you would like to be able to view the detail of transitions. Attention, en cochant cette option, l&#39;exécution du workflow peut être fortement ralentie.

* **[!UICONTROL Execute in the engine (do not use in production)]**: vous permet d’exécuter le processus localement, à des fins de test d’environnement de développement.

* **[!UICONTROL Severity]**: vous permet de spécifier un niveau de priorité pour l’exécution des  de dans votre instance . Les workflows critiques seront exécutés en priorité.

La **[!UICONTROL Error management]** section fournit des options supplémentaires qui vous permettent de gérer le comportement des en cas d’erreur. Ces options sont détaillées dans la section Gestion [des](#error-management) erreurs.

## Propriétés d&#39;une activité   {#activity-properties}

### Propriétés générales d&#39;une activité {#general-properties-of-an-activity}

Each activity has a **[!UICONTROL Properties]** tab. Cet onglet permet de modifier les paramètres généraux de l&#39;activité, notamment le libellé et l&#39;identifiant. La configuration de cet onglet est facultative.

### Gestion des transitions sortantes d&#39;une activité   {#managing-an-activity-s-outbound-transitions}

Par défaut, certaines activités ne possèdent pas de transition sortante. You can add one from the **[!UICONTROL Transitions]** tab or from the activity&#39;s **[!UICONTROL Properties]** tab to apply other processes to your population in the same workflow.

En fonction des activités, vous pouvez ajouter plusieurs types de transitions sortantes :

* Transition standard : population calculée par l&#39;activité.
* Transition sans population : ce type de transition sortante peut être ajouté pour continuer le workflow et ne contient pas de population afin de ne pas occuper d&#39;espace inutilement sur le système.
* Rejets : population rejetée. Par exemple, si des données en entrée d&#39;une activité n&#39;ont pas pu être traitées car incorrectes ou non complètes.
* Complémentaire : population restante après exécution de l&#39;activité. Par exemple, si une activité de segmentation est paramétrée pour ne conserver qu&#39;un pourcentage de la population entrante.

If applicable, specify a **[!UICONTROL Segment code]** for the activity&#39;s outbound transition. Ce code segment permet d&#39;identifier d&#39;où viennent les sous-ensembles de la population cible finale, et peut par la suite servir à des fins de personnalisation dans un message.

### Options d&#39;exécution d&#39;une activité   {#activity-execution-options}

In the activity&#39;s properties screen, there is an **[!UICONTROL Advanced options]** tab that lets you define the activity&#39;s execution mode and behavior in case of errors.

Pour y accéder, sélectionnez l&#39;activité de votre choix dans un workflow, puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png) de la barre d&#39;actions.

![](assets/wkf_advanced_parameters.png)

The **[!UICONTROL Execution]** field allows you to define the action to be carried out when the task is started. Trois options sont disponibles :

* **Normale** : l&#39;activité est exécutée normalement.
* **Activer mais ne pas exécuter** : l&#39;activité est mise en pause, de même que, par voie de conséquence, les futurs traitements qui en découlent. Cela peut s&#39;avérer utile si vous souhaitez assister au déclenchement de la tâche.
* **Ne pas activer** : l&#39;activité n&#39;est pas exécutée, de même que, par voie de conséquence, toutes celles qui lui succèdent (dans la même branche).

The **[!UICONTROL In case of error]** field allows you to specify the action to be carried out should the activity encounter an error. Deux options sont disponibles :

* **Suspendre le processus** : le workflow est automatiquement suspendu. Le statut du workflow est alors **En erreur** et la couleur qui lui est associée passe au rouge. Lorsque le problème est résolu, relancez le workflow.
* **Ignorer** : l&#39;activité n&#39;est pas exécutée, de même que, par voie de conséquence, toutes celles qui lui succèdent (dans la même branche). Cela peut s&#39;avérer utile dans le cas de tâches récurrentes. Si la branche comporte un planificateur placé en amont, celui-ci se déclenchera normalement à sa prochaine date d&#39;exécution.

The **[!UICONTROL Behavior]** field allows you to define the procedure to follow if asynchronous tasks are used. Deux options sont disponibles :

* **Plusieurs tâches autorisées** : plusieurs tâches peuvent être exécutées en même temps, même si la première n&#39;est pas terminée.
* **La tâche en cours est prioritaire** : lorsqu&#39;une tâche est en cours, celle-ci est prioritaire. Tant qu&#39;une tâche est toujours en cours, aucune autre tâche ne sera exécutée.

The **[!UICONTROL Max. execution duration]** field allows you to specify a duration such as &quot;30s&quot; or &quot;1h&quot;. Si l&#39;activité n&#39;est pas terminée une fois cette durée écoulée, une alerte est déclenchée, ce qui n&#39;a par ailleurs aucun impact sur le fonctionnement du workflow.

The **[!UICONTROL Affinity]** field allows you to force a workflow or a workflow activity to execute on a particular machine. Vous devez pour cela définir une ou plusieurs affinités au niveau du workflow ou de l&#39;activité concernée.

The **[!UICONTROL Time zone]** field allows you to select the time zone of the activity. Adobe Campaign permet de gérer les décalages horaires entre plusieurs pays concernés par la même instance. La configuration appliquée est paramétrée lors de la création de l&#39;instance.

>[!NOTE]
>
>Par défaut, si aucun fuseau horaire n’est sélectionné, l’activité utilise le fuseau horaire défini dans les propriétés du workflow.

Le champ **Commentaire** est un champ libre vous permettant d&#39;ajouter une note.
