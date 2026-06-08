---
title: Instructions de surveillance
description: Cette page présente des directives générales pour le suivi de performance de Campaign Standard
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
TQID: https://experienceleague.adobe.com/4hy5-pubF9F2FDQGaC7GF-BfMHqMDykC4mtypRc-zsk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 502
ht-degree: 100%

---

# Instructions de surveillance {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Surveillance du système</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Surveillance des workflows</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Surveillance des diffusions</a></p></td></tr>
</table>

Campaign Standard offre plusieurs moyens de surveiller vos instances pour s’assurer que votre système est intègre et de résoudre les problèmes éventuels qui peuvent se produire lors de la configuration des workflows, de l’envoi des diffusions, etc.

## Surveillance du système {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notifications système**

L’interface de Campaign Standard propose un volet de notification qui vous permet de vous informer de ce qui se passe dans le système : statuts des événements, mises à jour du système, action requise, etc. [En savoir plus](../../start/using/interface-description.md#top-bar)


**Workflows techniques**

Les workflows techniques sont des opérations ou traitements programmés pour s’exécuter périodiquement sur le serveur. Pour vous assurer que votre instance est saine et fonctionne correctement, vous devez vérifier qu’elle est toujours en cours d’exécution. [En savoir plus](../../administration/using/technical-workflows.md)

**Panneau de contrôle**

Le Panneau de contrôle vous permet de gérer plusieurs paramètres de votre instance : administrer les autorisations d’URL, vérifier les détails de votre instance tels que les versions de build de vos serveurs, surveiller l’utilisation des profils actifs, etc. Il vous permet également de surveiller l’espace disponible sur les serveurs SFTP connectés à votre instance. [En savoir plus](https://experienceleague.adobe.com/fr/docs/control-panel/using/control-panel-home.html?lang=fr).

>[!NOTE]
>
>Le Panneau de contrôle est accessible à tous les utilisateurs administrateurs. Les étapes permettant d&#39;octroyer un accès administrateur à un utilisateur sont présentées sur [cette page](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=fr#discover-control-panel).

**Objets techniques**

Le menu **[!UICONTROL Diagnostic]** est un outil essentiel pour surveiller et analyser les différents objets techniques générés par l’application : schémas de données, pages web, traitements par lots, etc. [En savoir plus](../../developing/using/monitoring-data-model-changes.md)

**Audits des exports**

Les audits des exports vous permettent de surveiller les exports effectués sur vos instances : fichiers chargés à partir de workflows, exports de listes et fichiers téléchargés à partir de messages de type courrier.
[En savoir plus](../../administration/using/auditing-export-logs.md)

**Licences**

Dans le menu **[!UICONTROL Licences]**, surveillez les informations relatives à vos instances : licences installées, versions de build et acceptations des conditions générales.
[En savoir plus](../../administration/using/licenses.md)

## Surveillance des workflows {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Bonnes pratiques et résolution des problèmes**

Suivez les bonnes pratiques et les instructions relatives à la résolution des problèmes lorsque vous utilisez des workflows pour améliorer les performances.
[En savoir plus](../../automating/using/best-practices-workflows.md)

**Logs et tâches**

La surveillance des logs de workflow est une étape essentielle pour analyser vos workflows et vérifier qu’ils s’exécutent correctement.
[En savoir plus](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notifications**

Campaign Standard vous permet d’envoyer des notifications aux personnes responsables afin de surveiller l’exécution de vos workflows et de voir si une erreur nécessite votre attention.
[En savoir plus](../../automating/using/monitoring-workflow-execution.md#error-management)

## Surveillance des diffusions {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Délivrabilité**

Campaign Standard met à votre disposition plusieurs outils de délivrabilité pour améliorer le nombre de messages correctement diffusés : rapports de débit de diffusion, optimisation de l’heure d’envoi, prévisualisation des messages, rendu des e-mails, gestion des quarantaines, etc.
[En savoir plus](../../sending/using/about-deliverability.md)

**Diffusions**

Une fois vos messages envoyés, des logs détaillés vous permettent de surveiller les diffusions et de mesurer le succès de votre campagne, ainsi que de suivre le comportement des personnes destinataires de messages.
[En savoir plus](../../sending/using/monitoring-a-delivery.md)

**Alertes de diffusion**

Grâce à la fonctionnalité d’alertes de diffusion, vous pouvez configurer des alertes qui seront automatiquement envoyées à un groupe d’utilisateurs au sujet de l’exécution des diffusions : échec d’envoi ou de préparation, mauvais taux de rebond, faible débit, etc.
[En savoir plus](../../sending/using/receiving-alerts-when-failures-happen.md)

**Rapports dynamiques**

Les rapports dynamiques fournissent divers rapports pour vous aider à être tenu informé des performances de vos diffusions : rebonds, diffusions les plus consultées par les destinataires, débit des diffusions, etc.
[En savoir plus](../../reporting/using/about-dynamic-reports.md)
