---
solution: Campaign Standard
product: campaign
title: Directives de supervision
description: Cette section présente des directives générales pour la surveillance de Campaign Standard.
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: Gestion des accès
role: Administrateur
level: Expérimenté
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 42%

---


# Directives de supervision {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Surveillance du système</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Surveillance des workflows</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Surveillance des diffusions</a></p></td></tr>
</table>

Campaign Standard offre plusieurs moyens de surveiller vos instances pour s’assurer que votre système est intègre et de résoudre les problèmes éventuels qui peuvent se produire lors de la configuration des workflows, de l’envoi des diffusions, etc.

## Surveillance du système {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notifications système**

L’interface de Campaign Standard fournit un volet de notification qui vous permet d’être tenu informé de ce qui se passe dans le système : Etat des événements, mises à jour du système, action requise, etc. [En savoir plus](../../start/using/interface-description.md#top-bar)


**Workflows techniques**

Les workflows techniques sont des opérations ou traitements programmés périodiquement pour s&#39;exécuter sur le serveur. Pour vous assurer que votre instance est saine et fonctionne correctement, vous devez vérifier qu’elle est toujours en cours d’exécution. [En savoir plus](../../administration/using/technical-workflows.md)

**Panneau de contrôle**

Le Panneau de Contrôle vous permet de gérer plusieurs paramètres de votre instance : Autorisations d’URL, vérifiez les détails de votre instance tels que les versions de build de vos serveurs, surveillez l’utilisation des profils principaux, etc. Il vous permet également de surveiller l’espace disponible sur les serveurs SFTP connectés à votre instance. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/control-panel/using/control-panel-home.html)

>[!NOTE]
>
>Le Panneau de Contrôle est accessible à tous les utilisateurs administrateurs. Les étapes permettant d’accorder l’accès administrateur à un utilisateur sont détaillées dans [cette page](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel).

**Objets techniques**

Le menu **[!UICONTROL Diagnostic]** est un outil clé pour surveiller et analyser les différents objets techniques générés par l&#39;application : schémas de données, pages Web, tâches par lots, etc. [En savoir plus](../../developing/using/monitoring-data-model-changes.md)

**Audits des exports**

Les audits des exportations vous permettent de contrôler les exportations effectuées sur vos instances : fichiers téléchargés à partir de workflows, d’exportations de listes et de fichiers téléchargés à partir de messages électroniques directs.
[En savoir plus](../../administration/using/auditing-export-logs.md)

**Licences**

Dans le menu **[!UICONTROL Licences]**, surveillez les informations relatives à vos instances : licences installées, versions de build et acceptations des conditions générales.
[En savoir plus](../../administration/using/licenses.md)

## Surveillance des workflows {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Bonnes pratiques et résolution des problèmes**

Suivez les meilleures pratiques et les instructions de dépannage lors de l’utilisation de workflows pour améliorer les performances.
[En savoir plus](../../automating/using/best-practices-workflows.md)

**Journaux et tâches**

La surveillance des journaux de travail est une étape clé pour analyser vos workflows et s&#39;assurer qu&#39;ils s&#39;exécutent correctement.
[En savoir plus](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notifications**


Campaign Standard vous permet d&#39;envoyer des notifications aux superviseurs afin de surveiller l&#39;exécution de vos workflows et de voir si une erreur nécessite votre attention.
[En savoir plus](../../automating/using/monitoring-workflow-execution.md#error-management)

## Surveillance des diffusions {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Délivrabilité**

Campaign Standard fournit plusieurs outils de délivrabilité pour vous aider à améliorer le nombre de messages correctement distribués : rapports sur le débit des diffusions, optimisation du temps d’envoi, prévisualisation des messages, rendu des courriels, gestion des quarantaines, etc.
[En savoir plus](../../sending/using/about-deliverability.md)

**Diffusions**

Une fois vos messages envoyés, des journaux détaillés vous permettent de surveiller les diffusions et de mesurer la réussite de votre campagne, ainsi que de suivre le comportement des messages destinataires.
[En savoir plus](../../sending/using/monitoring-a-delivery.md)

**Alertes de diffusion**

Grâce à la fonction d’alerte de Diffusion, vous pouvez configurer des alertes qui seront automatiquement envoyées à un groupe d’utilisateurs au sujet de l’exécution des diffusions : échec de l&#39;envoi ou de la préparation, mauvais taux de rebonds, faible débit, etc.
[En savoir plus](../../sending/using/receiving-alerts-when-failures-happen.md)

**Rapports dynamiques**

Le rapports dynamique fournit divers rapports pour vous aider à être tenu informé des performances de vos diffusions : rebonds, la plupart des diffusions vues par les destinataires, le débit des diffusions, etc.
[En savoir plus](../../reporting/using/about-dynamic-reports.md)
