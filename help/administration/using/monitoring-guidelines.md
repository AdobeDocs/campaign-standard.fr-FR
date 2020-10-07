---
title: Directives de supervision
description: Cette section présente des directives générales pour la surveillance des Campaign Standards.
page-status-flag: never-activated
uuid: cf0d782d-47bf-40ae-ab6f-d1d47fa15792
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: production
content-type: reference
topic-tags: introduction
discoiquuid: 8b33e6af-15c3-4b30-8ad6-d76a1f33be21
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 17%

---


# Directives de supervision {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Surveillance du système</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Surveillance des workflows</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Suivre les diffusions</a></p></td></tr>
</table>

Campaign Standard fournit plusieurs méthodes de surveillance de vos instances pour s’assurer que votre système est sain et éventuellement résoudre les problèmes qui peuvent se produire lors de la configuration de workflows, de l’envoi de diffusions, etc.

## Surveillance du système {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**L&#39;interface du** Campaign Standard de notifications système fournit un volet de notification qui vous permet d&#39;être tenu informé de ce qui se passe dans le système : Etat des événements, mises à jour du système, action requise, etc. [En savoir plus](../../start/using/interface-description.md#top-bar)


**Les workflows techniques** Workflows techniques sont des opérations ou des tâches dont l’exécution est planifiée sur une base régulière sur le serveur. Pour vous assurer que votre instance est saine et fonctionne correctement, vous devez vous assurer qu’elle est toujours en cours d’exécution. [En savoir plus](../../administration/using/technical-workflows.md)

**Panneau de Contrôle** Le Panneau de Contrôle vous permet de gérer plusieurs paramètres de votre instance : Autorisations d’URL, vérifiez les détails de votre instance tels que les versions de build de vos serveurs, surveillez l’utilisation des profils principaux, etc. Il vous permet également de surveiller l’espace disponible sur les serveurs SFTP connectés à votre instance. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/control-panel/using/control-panel-home.html)

>[!NOTE]
>
>Veuillez noter que le panneau de contrôle est accessible uniquement aux administrateurs et est disponible pour tous les clients qui utilisent les Managed Services d’Adobe.

**Objets** techniques Le menu **[!UICONTROL Diagnostic]** est un outil clé pour surveiller et analyser les différents objets techniques générés par l&#39;application : schémas de données, pages Web, tâches par lots, etc. [En savoir plus](../../developing/using/monitoring-data-model-changes.md)

**Audits**d’exportation Les audits d’exportation vous permettent de contrôler les exportations effectuées sur vos instances : fichiers téléchargés à partir de workflows, d’exportations de listes et de fichiers téléchargés à partir de messages électroniques directs.
[En savoir plus](../../administration/using/auditing-export-logs.md)

**Licences** Dans le menu **[!UICONTROL Licences]** , contrôlez les informations relatives à vos instances : les licences installées, les versions de build et les acceptations de conditions générales.
[En savoir plus](../../administration/using/licenses.md)

## Surveillance des workflows {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Meilleures pratiques et dépannage**Suivez les meilleures pratiques et les instructions de dépannage lorsque vous utilisez des workflows pour améliorer les performances.
[En savoir plus](../../automating/using/best-practices-workflows.md)

**La surveillance des journaux et des tâches**Worklow est une étape clé pour analyser vos workflows et s&#39;assurer qu&#39;ils s&#39;exécutent correctement.
[En savoir plus](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Le**Campaign Standard de notifications vous permet d&#39;envoyer des notifications aux superviseurs afin de surveiller l&#39;exécution de vos processus et de voir s&#39;il y a une erreur qui nécessite votre attention.
[En savoir plus](../../automating/using/monitoring-workflow-execution.md#error-management)

## Surveillance des diffusions {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Le**Campaign Standard de la délivrabilité fournit plusieurs outils de délivrabilité pour vous aider à améliorer le nombre de messages correctement distribués : rapports de pensée de diffusion, optimisation du temps d’envoi, prévisualisation des messages, rendu des courriels, gestion des quarantaines, etc.
[En savoir plus](../../sending/using/about-deliverability.md)

**Diffusions**Une fois vos messages envoyés, des journaux détaillés vous permettent de surveiller les diffusions et de mesurer la réussite de votre campagne, ainsi que de suivre le comportement des destinataires de messages.
[En savoir plus](../../sending/using/monitoring-a-delivery.md)

**Alertes**de diffusion Grâce à la fonction d&#39;alerte de Diffusion, vous pouvez configurer des alertes qui seront automatiquement envoyées à un groupe d&#39;utilisateurs au sujet de l&#39;exécution des diffusions : échec de l&#39;envoi ou de la préparation, mauvais taux de rebonds, faible débit, etc.
[En savoir plus](../../sending/using/receiving-alerts-when-failures-happen.md)

**Le rapports dynamique de rapports**dynamique fournit divers rapports pour vous aider à être tenu informé des performances de vos diffusions : rebonds, livraisons les plus consultées par les destinataires, débit des diffusions, etc.
[En savoir plus](../../reporting/using/about-dynamic-reports.md)
