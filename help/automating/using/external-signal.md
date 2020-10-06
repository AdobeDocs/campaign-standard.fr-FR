---
title: Signal externe
description: L'activité Signal externe déclenche un workflow lorsque certaines conditions sont remplies dans un autre workflow.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 3cb37426410eeb8be04c9c75afa4505894b15140
workflow-type: ht
source-wordcount: '649'
ht-degree: 100%

---


# Signal externe{#external-signal}

## Description {#description}

![](assets/signal.png)

L&#39;activité **[!UICONTROL Signal externe]** déclenche un workflow lorsque certaines conditions sont remplies dans un autre workflow ou un appel de l&#39;API REST.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Signal externe]** permet d&#39;organiser et d&#39;orchestrer différents processus qui composent un même parcours client dans différents workflows. Elle permet de démarrer un workflow à partir d&#39;un autre, supportant ainsi des parcours client plus complexes tout en améliorant le contrôle et la réactivité en cas de problèmes.

L&#39;activité **[!UICONTROL Signal externe]** est conçue pour être utilisée comme première activité de workflow. Elle peut être déclenchée à partir de l&#39;activité **[!UICONTROL Fin]** d&#39;un autre workflow ou d&#39;un appel API REST (voir à ce propos la [documentation de l&#39;API](../../api/using/triggering-a-signal-activity.md)).

Quand elle est déclenchée, des paramètres externes peuvent être définis et disponibles dans les variables d&#39;événements du workflow. Le processus d&#39;appel d&#39;un workflow avec des paramètres externes est détaillé dans [cette section](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>L&#39;activité ne peut pas être déclenchée plus souvent que toutes les 10 minutes.

Notez qu&#39;une activité **[!UICONTROL Signal externe]** peut être déclenchée via plusieurs événements différents. Dans ce cas, le **[!UICONTROL Signal externe]** est déclenché dès que l&#39;un des workflows source ou l&#39;appel de l&#39;API est exécuté. Il n&#39;est pas nécessaire que tous les workflows source aient terminé leur exécution.

**Rubriques connexes :**

* [Cas pratique : activité de signaux externes et import de données](../../automating/using/external-signal-data-import.md).
* [Cas pratique : appel d’un workflow pour créer une audience à partir d’un fichier à l’aide de paramètres externes](../../automating/using/use-case-calling-workflow.md)

## Configuration {#configuration}

Lors de la configuration d&#39;un signal externe, il est important de commencer par configurer l&#39;activité **[!UICONTROL Signal externe]** dans le workflow de destination. Une fois cette configuration terminée, l&#39;activité **[!UICONTROL Signal externe]** de ce workflow devient disponible et vous pouvez configurer l&#39;activité **[!UICONTROL Fin]** du workflow source.

1. Placez une activité **[!UICONTROL Signal externe]** dans votre workflow de destination.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.
1. Editez le libellé de l&#39;activité. Le libellé est requis lors de la configuration du workflow source qui déclenche le **[!UICONTROL Signal externe]**.

   Si vous voulez appeler le workflow avec des paramètres, utilisez la zone **[!UICONTROL Paramètres]** pour les déclarer. Voir à ce propos cette section : [](../../automating/using/declaring-parameters-external-signal.md).

   ![](assets/external_signal_configuration.png)

1. Confirmez la configuration de votre activité, ajoutez les éventuelles autres activités souhaitées et sauvegardez votre workflow.

   >[!NOTE]
   >
   >Si vous souhaitez déclencher le workflow de destination à partir d&#39;un autre workflow, effectuez la procédure suivante. Si vous souhaitez déclencher le workflow de destination depuis un appel de l&#39;API REST, consultez la [documentation de l&#39;API](../../api/using/triggering-a-signal-activity.md) pour plus d&#39;informations.

1. Ouvrez le workflow source et sélectionnez une activité **[!UICONTROL Fin]**. Si aucune activité **[!UICONTROL Fin]** n&#39;est disponible, ajoutez-en une après la dernière activité d&#39;une branche du workflow.

   Certaines activités ne sont pas dotées d&#39;une transition sortante par défaut. L&#39;onglet **[!UICONTROL Propriétés]** de cet onglet vous permet d&#39;ajouter une transition sortante.

   Par exemple, dans une activité **[!UICONTROL Mise à jour de données]**, allez dans l&#39;onglet **[!UICONTROL Transitions]** et cochez l&#39;option **[!UICONTROL Ajouter une transition sortante sans la population]**. Cette option vous permet d&#39;ajouter une transition qui ne contient pas de données et n&#39;occupe pas d&#39;espace inutilement sur votre système. Elle sert uniquement à relier l&#39;activité **[!UICONTROL Fin]** supplémentaire qui déclenche le workflow de destination.

   ![](assets/external_signal_empty_transition.png)

1. Dans l&#39;onglet **[!UICONTROL Signal externe]** de l&#39;activité **[!UICONTROL Fin]**, sélectionnez le workflow de destination et l&#39;activité **[!UICONTROL Signal externe]** à déclencher dans ce workflow.

   Lorsque vous configurez une activité **[!UICONTROL Fin]** pour qu&#39;elle déclenche un autre workflow, un symbole signal supplémentaire vient s&#39;ajouter à son icône.

   Si vous voulez appeler le workflow avec des paramètres, utilisez la zone **[!UICONTROL Paramètres et valeurs]**. Voir à ce propos cette section : [](../../automating/using/defining-parameters-calling-workflow.md).

   ![](assets/external_signal_end.png)

1. Sauvegardez le workflow source.

Une fois que l&#39;activité **[!UICONTROL Fin]** du workflow source ou que l&#39;appel de l&#39;API REST est exécuté, le workflow de destination est déclenché automatiquement via l&#39;activité **[!UICONTROL Signal externe]**.

>[!NOTE]
>
>Le workflow de destination doit être démarré manuellement avant de pouvoir être déclenché. Une fois démarrée, l&#39;**[!UICONTROL Activité externe]** est activée et attend le signal du workflow source.
