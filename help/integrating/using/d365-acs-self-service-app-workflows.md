---
title: Workflows d’application d’intégration
description: Workflows d’intégration Campaign et Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---


# Campaign - workflows d&#39;intégration Microsoft Dynamics 365

La page **[!UICONTROL Workflows]** liste les workflows techniques et leur état.

L’application d’intégration est fournie avec trois workflows :

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 à Campaign**
* Envoyer *contacts* de Microsoft Dynamics 365 vers Adobe Campaign
* *Entités* personnalisées : Apportez des tables personnalisées de Microsoft Dynamics 365 à Adobe Campaign. [En savoir plus](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Il s&#39;agit également de **Entrées** (en référence à l&#39;entrée de données de Microsoft Dynamics 365 à Adobe Campaign).

**Campaign vers Microsoft Dynamics 365**
* Les événements de marketing par courriel d&#39;Adobe Campaign Standard sont envoyés à Dynamics 365 (envoi par courriel, ouverture, clic, rebond). [En savoir plus](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Il s&#39;agit également de **Étape** (en référence à l&#39;absence de données d&#39;Adobe Campaign vers Microsoft Dynamics 365).

**Entrée/Sortie**

Les états d&#39;exclusion (par exemple, liste bloquée) peuvent être synchronisés de Microsoft Dynamics 365 à Adobe Campaign ou de Adobe Campaign à Microsoft Dynamics 365. Les données peuvent également être synchronisées bidirectionnellement (c&#39;est-à-dire que les flux de données dans les deux directions). [En savoir plus](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Il est fortement recommandé d&#39;arrêter le flux de travaux **Microsoft Dynamics 365 à Campaign** avant de publier les modifications apportées à Adobe Campaign Standard ou Microsoft Dynamics 365. Ces modifications comprennent des mises à jour des ressources/entités (et de leurs champs associés), des liens, des colonnes d&#39;identifiants, etc... qui sont actuellement utilisées par l&#39;intégration. Si vous ne le faites pas, vous risquez de perdre des données et/ou d’interrompre le flux de travaux de manière inattendue.

## Arrière-plan du processus

Cette application d’intégration commence par lire les données, puis écrit les données vers la destination. La colonne **[!UICONTROL Backlog]** indique le nombre d&#39;enregistrements placés en file d&#39;attente et en attente d&#39;écriture. Cette valeur devrait augmenter lorsque vous devez traiter une grande quantité de données (par exemple, lorsque vous exécutez l’intégration pour la première fois, que vous réexécutez les données, etc.).

>[!NOTE]
>Si vos enregistrements Microsoft Dynamics 365 et/ou Campaign ne sont pas mis à jour, vous devez d&#39;abord vérifier s&#39;il y a un grand nombre d&#39;enregistrements en attente d&#39;écriture sur la destination.


## Workflow status {#workflow-status}

La colonne **[!UICONTROL Status]** indique l&#39;état des processus en arrière-plan associés au flux de travail. Les valeurs possibles sont les suivantes :

* **EN COURS** : Le processus est en cours d’exécution et vos données doivent être synchronisées.
* **ARRÊTÉ** : Le processus n’est pas en cours d’exécution. Vous ne devez donc pas vous attendre à ce que vos données soient synchronisées.
* **DÉBUT** : Vous avez demandé que le flux de travail soit traité en début. L&#39;application n&#39;a pas encore commencé à synchroniser les données associées à ce flux de travail, mais vous pouvez vous attendre à ce qu&#39;elle le fasse après quelques minutes (quand elle affichera ensuite l&#39;état de **EN COURS**).
* **ÉCHEC** : Les processus de workflow étaient en cours d&#39;exécution, mais ils ont rencontré des erreurs et n&#39;ont pas pu les récupérer.

## Actions disponibles

Les actions possibles sont répertoriées ci-dessous.

* **Modifier** : En cliquant sur l&#39;icône représentant un crayon, vous accédez à une autre page qui vous permet d&#39;apporter des mises à jour au flux de travail. Gardez à l’esprit que les modifications que vous apportez ne prendront pas effet tant que vous n’arrêterez pas le flux de travail, puis que vous ne le redémarrerez pas.

* **Début** : Un bouton Début demande qu’un processus arrêté soit démarré. Ce bouton s’affiche uniquement lorsque les processus associés au processus sont actuellement arrêtés. Les processus passent d’abord à &quot;DÉMARRER&quot;, puis à &quot;EN COURS&quot;. Les données associées au processus ne début pas la synchronisation tant que le processus n’est pas en cours d’exécution.

   Le bouton début est une bascule. Si les processus du processus ont déjà été démarrés, le bouton devient un bouton **Arrêter**.

* **Arrêter** : Un bouton  **** Arrêt demande l’arrêt d’un processus en cours d’exécution. Ce bouton s’affiche uniquement lorsque les processus associés au processus sont en cours d’exécution.

Lorsque vous modifiez un processus, vos mises à jour ne sont PAS immédiatement intégrées aux règles des processus en cours d’exécution, jusqu’à ce que vous arrêtiez le processus, puis que vous cliquiez sur le bouton **Début**. Vos mises à jour sont ensuite intégrées aux processus en cours d’exécution (une fois que le processus revient à un état **EN COURS**).

Une indication d&#39;avertissement est ajoutée au bouton **Arrêter** afin de vous indiquer à quel moment (a) vous avez mis à jour votre flux de travail, mais (b) vous n&#39;avez pas arrêté/Début de ce flux de travail.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
