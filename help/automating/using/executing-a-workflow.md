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
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

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

Pour pouvoir accéder au détail des transitions intermédiaires (autres que la dernière transition du workflow), vous devez cocher l&#39;option **[!UICONTROL Conserver les résultats intermédiaires]**dans la section**[!UICONTROL  Exécution]** des propriétés du workflow avant de démarrer le workflow.

>[!NOTE]
>
>Cette option consomme beaucoup de mémoire et a été conçue pour vous aider à construire un workflow et à vous assurer que sa configuration et son comportement sont corrects. Laissez-la décochée sur les instances de production.

Lorsqu&#39;une transition est ouverte, vous pouvez modifier son **[!UICONTROL Libellé]**ou lui associer un**[!UICONTROL  Code segment]**. Pour cela, éditez les champs correspondants et validez vos modifications.

## Contrôle d&#39;un workflow à partir de l&#39;API REST  {#controlling-a-workflow-from-the-rest-api}

L&#39;API REST vous permet de **démarrer**, **mettre en pause**, **reprendre** et **arrêter** un workflow.

Vous trouverez plus d&#39;informations et d&#39;exemples d&#39;appels REST dans la [documentation de l&#39;API.](../../api/using/controlling-a-workflow.md)

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

## Commandes d&#39;exécution  {#execution-commands}

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

## Contrôle  {#monitoring}

L&#39;icône ![](assets/printpreview_darkgrey-24px.png) permet d&#39;accéder au menu Journal et tâches du workflow.

L&#39;historique d&#39;un workflow est conservé pendant la durée que vous indiquez dans les options d&#39;exécution du workflow (voir [Propriétés des workflows](#workflow-properties)). Pendant cette durée, tous les messages sont donc conservés, même après un redémarrage. Si vous ne voulez pas conserver les messages d&#39;une exécution précédente, vous devez purger l&#39;historique en cliquant sur le bouton ![](assets/delete_darkgrey-24px.png).

L&#39;onglet **[!UICONTROL Journal]**contient l&#39;historique de l&#39;exécution de toutes les activités ou des activités sélectionnées. Il répertorie par ordre chronologique les opérations réalisées et les erreurs d&#39;exécution.

![](assets/wkf_execution_4.png)

L&#39;onglet **[!UICONTROL Tâches]**permet de voir le séquencement de l&#39;exécution des activités. Cliquez sur une tâche pour obtenir plus d&#39;informations.

![](assets/wkf_execution_5.png)

Dans ces deux listes :

* Cliquez sur le compteur pour obtenir le nombre total des activités selon le filtrage appliqué. Le comptage est affiché par défaut si le nombre d&#39;éléments dans la liste est inférieur à 30.
* Le bouton **[!UICONTROL Configurer la liste]**permet de choisir les informations affichées, de définir l&#39;ordre des colonnes et d&#39;appliquer un tri.
* Vous pouvez utiliser des filtres pour trouver plus rapidement les informations dont vous avez besoin. Utilisez le champ de recherche pour rechercher du texte spécifique dans les noms des activités de workflow (par exemple &quot;requête&quot;) et les logs.

## Gestion des erreurs  {#error-management}

Lorsqu&#39;une erreur se produit, le workflow se met en pause et l&#39;activité qui était en cours d&#39;exécution lorsque l&#39;erreur s&#39;est produite clignote alors en rouge.

Le statut du workflow passe au rouge et l&#39;erreur est consignée dans le journal.

Vous pouvez paramétrer le workflow pour qu&#39;il ne se mette pas en pause et continue son exécution en cas d&#39;erreur. Pour cela, accédez aux propriétés du workflow à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png) et, dans la section **[!UICONTROL Exécution]**, sélectionnez l&#39;option** Ignorer **dans le champ** En cas d&#39;erreur **.

Dans ce cas, la tâche en erreur est abandonnée. Ce mode est particulièrement adapté aux workflows conçus pour permettre de retenter l&#39;opération ultérieurement (actions périodiques).

>[!NOTE]
>
>Vous pouvez appliquer ce paramétrage au niveau de chaque activité. Pour cela, sélectionnez l&#39;activité de votre choix puis ouvrez-là à l&#39;aide de l&#39;action rapide ![](assets/edit_darkgrey-24px.png) et sélectionnez le mode de gestion des erreurs dans l&#39;onglet **Options d&#39;exécution.** Voir [Options d&#39;exécution d&#39;une activité](#activity-execution-options).

La section **[!UICONTROL Exécution]**des propriétés du workflow permet également de définir un nombre d&#39;**[!UICONTROL  erreurs consécutives]** autorisées avant que l&#39;exécution du workflow ne soit automatiquement suspendue. Tant que ce nombre n&#39;est pas atteint, les éléments en erreur sont ignorés et les autres branches du workflow sont exécutées normalement. Si ce nombre est atteint, le workflow est suspendu et les superviseurs du workflow sont informés automatiquement (email et notification dans l&#39;application). Voir [Propriétés des workflows](#workflow-properties) et [Notifications Adobe Campaign](../../administration/using/sending-internal-notifications.md).

Les superviseurs peuvent également être définis dans les propriétés d&#39;exécution du workflow.

## Propriétés d&#39;exécution  {#workflow-properties}

Pour modifier les propriétés d&#39;exécution de l&#39;ensemble d&#39;un workflow, utilisez le bouton ![](assets/edit_darkgrey-24px.png) pour accéder aux propriétés du workflow et sélectionnez la section **[!UICONTROL Exécution]**.

Le champ **[!UICONTROL Affinité par défaut]**vous permet de forcer l&#39;exécution d&#39;un workflow ou d&#39;une activité de workflow sur une machine en particulier.

Dans le champ **[!UICONTROL Jours d&#39;historique]**, indiquez la durée au bout de laquelle l&#39;historique doit être purgé.

Vous pouvez choisir de cocher les cases **[!UICONTROL Enregistrer les requêtes SQL dans le journal]**et**[!UICONTROL  Exécuter dans le moteur (ne pas utiliser en production)]** le cas échéant.

Cochez la case **[!UICONTROL Conserver les résultats intermédiaires]**si vous souhaitez pouvoir visualiser le détail des transitions. Attention, en cochant cette option, l&#39;exécution du workflow peut être fortement ralentie.

Le champ **[!UICONTROL Niveau de criticité]**permet de définir un niveau de priorité pour l&#39;exécution des workflows de votre instance Adobe Campaign. Les workflows critiques seront exécutés en priorité.

Le champ **[!UICONTROL Superviseurs]**permet de définir le groupe de personnes à avertir (email et notification dans l&#39;application) si le workflow est en erreur. Si aucun groupe n&#39;est défini, personne ne sera notifié. Pour plus d&#39;informations sur les notifications d&#39;Adobe Campaign, voir[Notifications Adobe Campaign](../../administration/using/sending-internal-notifications.md).

Le champ **[!UICONTROL En cas d&#39;erreur]**vous permet de définir l&#39;action à effectuer lorsque l&#39;activité a rencontré une erreur. Deux options sont disponibles :

* **Suspendre le processus** : le workflow est automatiquement suspendu. Le statut du workflow est alors **En erreur** et la couleur qui lui est associée passe au rouge. Lorsque le problème est résolu, relancez le workflow.
* **Ignorer** : l&#39;activité n&#39;est pas exécutée, de même que, par voie de conséquence, toutes celles qui lui succèdent (dans la même branche). Cela peut s&#39;avérer utile dans le cas de tâches récurrentes. Si la branche comporte un planificateur placé en amont, celui-ci se déclenchera normalement à sa prochaine date d&#39;exécution.

   En sélectionnant cette option, vous pouvez également définir un nombre d&#39;**[!UICONTROL Erreurs consécutives]**autorisées :

   * Si le nombre indiqué est **[!UICONTROL 0]**ou tant que ce nombre n&#39;est pas atteint, les activités qui rencontrent des erreurs sont ignorées. Les autres branches du workflow sont exécutées normalement.
   * Si le nombre indiqué est atteint, l&#39;ensemble du workflow est suspendu et passe **[!UICONTROL En erreur]**. Si des superviseurs ont été définis, ils sont automatiquement notifié par un email.

![](assets/wkf_execution_6.png)

## Propriétés d&#39;une activité  {#activity-properties}

### Propriétés générales d&#39;une activité {#general-properties-of-an-activity}

Chaque activité possède un onglet **[!UICONTROL Propriétés]**. Cet onglet permet de modifier les paramètres généraux de l&#39;activité, notamment le libellé et l&#39;identifiant. La configuration de cet onglet est facultative.

### Gestion des transitions sortantes d&#39;une activité  {#managing-an-activity-s-outbound-transitions}

Par défaut, certaines activités ne possèdent pas de transition sortante. Vous pouvez en ajouter à partir de l&#39;onglet **[!UICONTROL Transitions]**ou de l&#39;onglet**[!UICONTROL  Propriétés]** de l&#39;activité afin d&#39;appliquer d&#39;autres traitements à votre population dans un même workflow.

En fonction des activités, vous pouvez ajouter plusieurs types de transitions sortantes :

* Transition standard : population calculée par l&#39;activité.
* Transition sans population : ce type de transition sortante peut être ajouté pour continuer le workflow et ne contient pas de population afin de ne pas occuper d&#39;espace inutilement sur le système.
* Rejets : population rejetée. Par exemple, si des données en entrée d&#39;une activité n&#39;ont pas pu être traitées car incorrectes ou non complètes.
* Complémentaire : population restante après exécution de l&#39;activité. Par exemple, si une activité de segmentation est paramétrée pour ne conserver qu&#39;un pourcentage de la population entrante.

Vous pouvez indiquer un **[!UICONTROL Code segment]**pour la transition sortante d&#39;une l&#39;activité. Ce code segment permet d&#39;identifier d&#39;où viennent les sous-ensembles de la population cible finale, et peut par la suite servir à des fins de personnalisation dans un message.

### Options d&#39;exécution d&#39;une activité  {#activity-execution-options}

L&#39;écran des propriétés d&#39;une activité comporte un onglet **[!UICONTROL Options d&#39;exécution]**vous permettant notamment de définir son mode d&#39;exécution et le comportement en cas d&#39;erreur.

Pour y accéder, sélectionnez l&#39;activité de votre choix dans un workflow, puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png) de la barre d&#39;actions.

![](assets/wkf_advanced_parameters.png)

Le champ **[!UICONTROL Exécution]**vous permet de définir l&#39;action à effectuer au moment du déclenchement de la tâche. Trois options sont disponibles :

* **Normale** : l&#39;activité est exécutée normalement.
* **Activer mais ne pas exécuter** : l&#39;activité est mise en pause, de même que, par voie de conséquence, les futurs traitements qui en découlent. Cela peut s&#39;avérer utile si vous souhaitez assister au déclenchement de la tâche.
* **Ne pas activer** : l&#39;activité n&#39;est pas exécutée, de même que, par voie de conséquence, toutes celles qui lui succèdent (dans la même branche).

Le champ **[!UICONTROL En cas d&#39;erreur]**vous permet de définir l&#39;action à effectuer lorsque l&#39;activité a rencontré une erreur. Deux options sont disponibles :

* **Suspendre le processus** : le workflow est automatiquement suspendu. Le statut du workflow est alors **En erreur** et la couleur qui lui est associée passe au rouge. Lorsque le problème est résolu, relancez le workflow.
* **Ignorer** : l&#39;activité n&#39;est pas exécutée, de même que, par voie de conséquence, toutes celles qui lui succèdent (dans la même branche). Cela peut s&#39;avérer utile dans le cas de tâches récurrentes. Si la branche comporte un planificateur placé en amont, celui-ci se déclenchera normalement à sa prochaine date d&#39;exécution.

Le champ **[!UICONTROL Comportement]**vous permet de définir la marche à suivre en cas de tâches asynchrones. Deux options sont disponibles :

* **Plusieurs tâches autorisées** : plusieurs tâches peuvent être exécutées en même temps, même si la première n&#39;est pas terminée.
* **La tâche en cours est prioritaire** : lorsqu&#39;une tâche est en cours, celle-ci est prioritaire. Tant qu&#39;une tâche est toujours en cours, aucune autre tâche ne sera exécutée.

Le champ **[!UICONTROL Durée max. d&#39;exécution]**vous permet d&#39;indiquer une durée de type &quot;30s&quot; ou &quot;1h&quot;. Si l&#39;activité n&#39;est pas terminée une fois cette durée écoulée, une alerte est déclenchée, ce qui n&#39;a par ailleurs aucun impact sur le fonctionnement du workflow.

Le champ **[!UICONTROL Affinité]**vous permet de forcer l&#39;exécution d&#39;un workflow ou d&#39;une activité de workflow sur une machine en particulier. Vous devez pour cela définir une ou plusieurs affinités au niveau du workflow ou de l&#39;activité concernée.

Le champ **[!UICONTROL Fuseau horaire]**vous permet de sélectionner le fuseau horaire de l&#39;activité. Adobe Campaign permet de gérer les décalages horaires entre plusieurs pays concernés par la même instance. La configuration appliquée est paramétrée lors de la création de l&#39;instance.

>[!NOTE]
>
>Par défaut, si aucun fuseau horaire n’est sélectionné, l’activité utilise le fuseau horaire défini dans les propriétés du flux de travail.

Le champ **Commentaire** est un champ libre vous permettant d&#39;ajouter une note.
