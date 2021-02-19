---
title: Workflows de l’application d’intégration
description: Workflows d’intégration Campaign et Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 100%

---


# Workflows d&#39;intégration Campaign - Microsoft Dynamics 365

La page **[!UICONTROL Workflows]** répertorie les workflows techniques et leur état.

L’application d’intégration est fournie avec trois workflows :

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 vers Campaign**
* Envoi de *contacts* de Microsoft Dynamics 365 vers Adobe Campaign
* *Entités personnalisées* : import des tables personnalisées de Microsoft Dynamics 365 vers Adobe Campaign. [En savoir plus](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* On utilise également le terme **entrée** (en référence à l&#39;entrée de données de Microsoft Dynamics 365 vers Adobe Campaign).

**Campaign vers Microsoft Dynamics 365**
* Les événements de marketing par email d&#39;Adobe Campaign Standard sont envoyés à Dynamics 365 (envoi par email, ouverture, clic, bounce). [En savoir plus](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* On utilise également le terme **sortie** (en référence à la sortie des données d&#39;Adobe Campaign vers Microsoft Dynamics 365).

**Opt-in/opt-out**

Les états d&#39;opt-out (par exemple, liste bloquée) peuvent être synchronisés de Microsoft Dynamics 365 vers Adobe Campaign ou d’Adobe Campaign vers Microsoft Dynamics 365. Les données peuvent également être synchronisées de façon bidirectionnelle (c&#39;est-à-dire que les données sont acheminées dans les deux sens). [En savoir plus](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Il est fortement recommandé d&#39;arrêter le workflow **Microsoft Dynamics 365 vers Campaign** avant de publier les modifications apportées à Adobe Campaign Standard ou Microsoft Dynamics 365. Ces modifications comprennent des mises à jour de ressources/entités (et de leurs champs associés), de liens, de colonnes d&#39;identifiant, etc., qui sont actuellement utilisés par l&#39;intégration. Si vous ne le faites pas, vous risquez de perdre des données et/ou d’interrompre le workflow de manière inattendue.

## Backlog des workflows

Cette application d’intégration commence par lire les données, puis les écrit vers la destination. La colonne **[!UICONTROL Backlog]** indique le nombre d&#39;enregistrements placés en file d&#39;attente et en attente d&#39;écriture. Cette valeur doit augmenter lorsque une grande quantité de données doit être traitée (par exemple, lorsque vous exécutez l’intégration pour la première fois, que vous relisez les données, etc.).

>[!NOTE]
>Si vos enregistrements Microsoft Dynamics 365 et/ou Campaign ne sont pas mis à jour, vous devez d&#39;abord vérifier si un grand nombre d&#39;enregistrements est en attente d&#39;écriture sur la destination.


## Etat du workflow {#workflow-status}

La colonne **[!UICONTROL Statut]** indique l&#39;état des processus en arrière-plan associés au workflow. Les valeurs possibles sont les suivantes :

* **EXÉCUTION EN COURS** : le processus est en cours d’exécution et vos données doivent être synchronisées.
* **ARRÊTÉ** : le processus n’est pas en cours d’exécution. Vous ne devez donc pas vous attendre à ce que vos données soient synchronisées.
* **DÉMARRAGE EN COURS** : vous avez demandé le démarrage des processus de workflow. L&#39;application n&#39;a pas encore commencé à synchroniser les données associées à ce workflow, mais vous pouvez vous attendre à ce qu&#39;elle le fasse après quelques minutes (quand elle affichera l&#39;état **EXÉCUTION EN COURS**).
* **ÉCHEC** : les processus de workflow étaient en cours d&#39;exécution, mais ils ont rencontré des erreurs et n&#39;ont pas pu reprendre.

## Actions disponibles

Les actions possibles sont répertoriées ci-dessous.

* **Modifier** : en cliquant sur l&#39;icône représentant un crayon, vous accédez à une autre page qui vous permet d&#39;apporter des mises à jour au workflow. Souvenez-vous que les modifications que vous apportez NE prendront PAS effet tant que vous n’arrêterez pas le workflow, puis que vous ne le redémarrerez pas.

* **Démarrer** : un bouton Démarrer demande qu’un workflow arrêté soit démarré. Ce bouton s’affiche uniquement lorsque les processus associés au workflow sont actuellement arrêtés. Les processus passent d’abord aux statuts « DÉMARRER » puis « EXÉCUTION EN COURS ». Les données associées au workflow ne démarrent pas la synchronisation tant que le workflow n’est pas en cours d’exécution.

   Le bouton Démarrer est un bouton bascule. Si les processus de workflow ont déjà été démarrés, le bouton se transforme en bouton **Arrêter**.

* **Arrêter** : un bouton **Arrêter** demande l’arrêt d’un workflow en cours d’exécution. Ce bouton s’affiche uniquement lorsque les processus associés au workflow sont en cours d’exécution.

Lorsque vous modifiez un workflow, vos mises à jour NE sont PAS immédiatement intégrées aux règles des processus en cours d’exécution. Vous devez arrêter le workflow, puis cliquer sur le bouton **Démarrer**. Vos mises à jour sont ensuite intégrées aux processus en cours d’exécution (une fois que le processus revient à un statut **EXÉCUTION EN COURS**).

Un avertissement est ajouté au bouton **Arrêter** afin de vous indiquer à quel moment (a) vous avez mis à jour votre workflow et (b) que vous n&#39;avez pas arrêté / démarré ce workflow.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
