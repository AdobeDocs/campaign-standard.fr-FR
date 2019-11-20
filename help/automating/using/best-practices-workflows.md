---
title: Bonnes pratiques relatives aux workflows
description: Découvrez les bonnes pratiques à appliquer à vos workflows.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Bonnes pratiques relatives aux workflows{#workflow-best-practices}

Avec Adobe Campaign, vous pouvez configurer tous les types de workflows pour effectuer une vaste étendue de tâches. Toutefois, lors de la conception et de l'exécution de vos workflows, vous devez faire très attention, car une mauvaise implémentation peut entraîner de faibles performances, des erreurs et des problèmes de plate-forme. Vous trouverez ci-dessous une liste de bonnes pratiques et de conseils de dépannage.

>[!NOTE]
>
>La conception et l'exécution des workflows doivent être effectuées par un utilisateur expérimenté Adobe Campaign.

## Attribution d'un nom{#naming}

Pour faciliter le dépannage des workflows, Adobe conseille de les nommer et de les libeller explicitement. Renseignez le champ Description du workflow pour résumer le processus à exécuter afin que l'opérateur puisse facilement le comprendre.
Si le workflow fait partie d'un processus impliquant d'autres workflows, vous pouvez utiliser des chiffres lors de la saisie d'un libellé pour les classer clairement.

Par exemple :

* 001 - Import - Import des destinataires
* 002 - Import - Import de ventes
* 003 - Import - Import des détails sur les ventes
* 010 - Export - Export des logs de diffusion
* 011 - Export - Export des logs de tracking

## Duplication des workflows{#duplicating-workflows}

Vous pouvez dupliquer des workflows. Dans **[!UICONTROL Activités marketing]**, pointez sur le workflow et cliquez sur **[!UICONTROL Dupliquer l'élément]**. Une fois le workflow dupliqué, ses modifications ne sont pas appliquées à la copie de celui-ci. La copie du workflow peut être éditée.

![](assets/duplicating_workflow.png)

## Exécution{#execution}

### Nombre de workflows

Par défaut, il est recommandé de ne pas exécuter simultanément plus de 20 workflows actifs. Lorsque cette limite est atteinte, les workflows sont placés en file d'attente afin de ne pas impacter les performances. De même, Adobe recommande d'étaler l'exécution des workflows dans le temps.
Dans des contextes spécifiques, vous devrez peut-être exécuter plus de 20 workflows. Cela ne s'applique pas aux workflows en attente d'une exécution planifiée. Si tel est le cas, vous devez vérifier les possibilités avec un expert de Campaign et contacter le service à la clientèle Adobe pour augmenter la limite.

### Fréquence

Un workflow ne peut pas être exécuté automatiquement plus souvent qu'une fois toutes les dix minutes.
La Fréquence de répétition de l'activité ne peut pas être inférieure à 10 minutes, Si la fréquence de répétition est paramétrée sur 0 (également valeur par défaut), cette option n'est pas prise en compte et le workflow s'exécute selon la fréquence d'exécution définie.

### Workflows en pause

Les workflows en pause ou en échec pendant plus de 7 jours sont arrêtés afin de consommer moins d'espace disque. La tâche de nettoyage s'affiche dans les logs de workflow.

### Transitions

Un workflow contenant des transitions flottantes peut être exécuté : il génère un avertissement et est suspendu une fois qu'il atteint la transition, mais aucune erreur n'est entraînée. Il est aussi possible de démarrer un workflow sans en avoir terminé la conception et de le compléter au fur et à mesure.

Pour plus d'informations, voir [Exécution de workflows](../../automating/using//executing-a-workflow.md).

## Activité{#activity}

### Conception des workflows

Pour vérifier que le workflow se termine correctement, utilisez une **[!UICONTROL activité Fin]**. Evitez de laisser seule la dernière transition d'un workflow.

Pour accéder au détail des transitions, cochez l'option [!UICONTROL Conserver les résultats intermédiaires] dans la section **Exécution** des propriétés du workflow.

>[!CAUTION]
>
>Cette option consomme beaucoup d'espace disque. De plus, elle a été conçue pour vous aider à créer un workflow et à garantir une configuration et un comportement corrects. Laissez-la décochée sur les instances de production.

![](assets/keep_interim_best_practices.png)


### Activités d'attribution de libellé{#activity-labeling}

Lors du développement de votre workflow, un nom est généré pour chaque activité, comme pour tous les objets Adobe Campaign. Bien que le nom d'une activité soit généré par l'outil et ne puisse pas être modifié, il est recommandé de lui attribuer un nom explicite lors de sa configuration.

### Duplication des activités{#activity-duplicating}

Pour dupliquer des activités existantes, vous pouvez effectuer un copier-coller. Ainsi, vous conservez les paramètres qui étaient définis à l'origine. Pour plus d'informations, consultez [Duplication des activités de workflow](../../automating/using/workflow-interface.md).

### Activité Planificateur{#acheduler-activity}

Lors de la construction de votre workflow, n'utilisez qu'une seule **[!UICONTROL activité Planificateur]** par branche. Si une même branche d'un workflow comporte plusieurs planificateurs (liés les uns aux autres), le nombre de tâches à exécuter sera multiplié de manière exponentielle, ce qui surchargerait considérablement la base.

Vous pouvez prévisualiser les dix prochaines exécutions de vos workflows en cliquant sur **[!UICONTROL Aperçu des prochaines exécutions]**.

![](assets/preview_scheduler.png)

Pour plus d'informations, consultez [Activité Planificateur](../../automating/using/scheduler.md).

## Appel d'un workflow avec des paramètres{#workflow-with-parameters}

Assurez-vous que le nom et le nombre de paramètres correspondent à ce qui est défini lors de l'appel du workflow (voir [Définir les paramètres lors de l'appel du workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). De plus, les types des paramètres doivent être cohérents par rapport aux valeurs attendues.

Veillez à ce que tous les paramètres soient déclarés dans l'activité **[!UICONTROL Signal externe]**. Dans le cas contraire, une erreur se produira lors de l'exécution de l'activité.

Pour plus d'informations, voir [Appeler un workflow avec des paramètres externes](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Export de packages{#exporting-packages}

Pour exporter des packages, les ressources exportées ne doivent pas contenir d'identifiants par défaut. Il est donc obligatoire de modifier les identifiants des ressources exportables en s'éloignant des modèles livrés par Adobe Campaign Standard. Pour plus d'informations, consultez [Gestion des packages](../../automating/using/managing-packages.md).

## Export de listes{#exporting-lists}

L'option d'export de liste permet d'exporter un maximum de 100 000 lignes par défaut et est définie par l'option **Nms_ExportListLimit**. Cette option peut être gérée par l'administrateur fonctionnel depuis le menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Paramétrage de l'application]** &gt; **[!UICONTROL Options]**.
Pour plus d'informations, consultez [Export de listes](../../automating/using/exporting-lists.md).

## Résolution des problèmes{#workflow-troubleshooting}

Adobe Campaign propose divers logs pour mieux comprendre les problèmes liés aux workflows.

### Utilisation des logs de workflow{#using-workflow-logs}

Vous pouvez accéder aux logs de workflow pour surveiller l'exécution de vos activités. Ils répertorient par ordre chronologique les opérations réalisées et les erreurs d'exécution. L'onglet Logs contient l'historique de l'exécution de toutes les activités ou de celles sélectionnées.
L'onglet Tâches permet de voir le séquencement de l'exécution des activités. Pour obtenir plus d'informations sur une activité, cliquez sur une tâche. Pour plus d'informations, consultez [Surveiller l'exécution des workflows](../../automating/using/executing-a-workflow.md#monitoring).

#### Résolution des problèmes liés aux activités Data Management{#troubleshooting-data-management-activities}

Vous pouvez analyser les requêtes SQL dans l'onglet Journal.

1. Dans l'espace de travail du workflow, cliquez sur **[!UICONTROL Editer les propriétés]**.
1. Dans **[!UICONTROL Général]** &gt; **[!UICONTROL Exécution]**, cochez les options **[!UICONTROL Enregistrer les requêtes SQL dans le journal]** et **[!UICONTROL Exécuter dans le moteur]**, puis cliquez sur **[!UICONTROL .Confirmer]**.

**Pour voir les requêtes SQL dans Journal :**
1. Cliquez sur **[!UICONTROL Journal et tâches]**.
1. Dans l'onglet **[!UICONTROL Logs]**, ouvrez le panneau **[!UICONTROL Recherche]**.
1. Cochez l'option **[!UICONTROL Afficher les logs SQL uniquement]**.

La requête est affichée dans la colonne **[!UICONTROL Message]** des logs.

### Utilisation des logs de diffusion{#using-delivery-logs}

Les logs de diffusion permettent de surveiller le succès de vos diffusions. Les logs d'exclusion renvoient les messages exclus lors de la préparation de l'envoi. Les logs d'envoi indiquent l'état de la diffusion pour chaque profil.
Pour plus d'informations, voir [Comprendre les diffusions en échec](../../sending/using/understanding-delivery-failures.md).

### Utilisation des alertes de diffusion{#delivery-alerting}

La fonctionnalité Alertes de diffusion est un système de gestion des alertes qui permet à un groupe d'utilisateurs de recevoir automatiquement des notifications contenant des informations sur l'exécution de leurs diffusions.
Pour plus d'informations, consultez [Alertes de diffusion](../../sending/using/receiving-alerts-when-failures-happen.md).

**Rubriques connexes :**

* [Gestion des erreurs](../../automating/using/executing-a-workflow.md#error-management)
