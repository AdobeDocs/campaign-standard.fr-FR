---
title: Présentation des workflows
description: Adobe Campaign propose un environnement graphique complet qui permet de concevoir et automatiser des processus.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Présentation des workflows{#discovering-workflows}

Adobe Campaign propose un [environnement graphique](../../automating/using/workflow-interface.md) qui permet de construire des [processus complexes](../../automating/using/workflow-operating-principles.md) englobant segmentation, exécution de campagnes, manipulation de fichiers, validations, etc. Les principes et les bonnes pratiques sont présentés dans [cette section](../../automating/using/building-a-workflow.md).

Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d'importer ses enregistrements dans la base de données Adobe Campaign.

Un workflow peut également faire intervenir des utilisateurs, pour leur affecter une tâche ou demander la validation d'une tâche accomplie. Ainsi, il est possible d'assigner une tâche à un ou plusieurs utilisateurs qui seront chargés de saisir son contenu ou spécifier sa cible, puis de faire valider un BAT avant d'envoyer un message.

Les workflows peuvent intervenir dans **différents contextes**, par exemple :

* Ciblage afin de gérer des audiences ou envoyer des messages. Voir à ce propos les sections [Activités des canaux](../../automating/using/about-channel-activities.md) et [Activités de ciblage](../../automating/using/about-targeting-activities.md).
* Data management (ETL) pour manipuler des données. Voir à ce propos [Activités de Data Management](../../automating/using/about-data-management-activities.md).
* Import de données dans la base de Campaign. Voir à ce sujet [Import et export de données](../../automating/using/about-data-import-and-export.md).
* Processus techniques tels que les tâches de nettoyage de la base (cleanup), la récupération des informations de tracking, etc. En savoir plus sur les workflows techniques dans [cette section](../../administration/using/technical-workflows.md).

Les workflows sont également accessibles depuis l'API Adobe Campaign Standard. Consultez à ce sujet la [documentation dédiée](../../api/using/managing-workflows.md).

**Rubriques connexes :**

* [Principes opérationnels des workflows](../../automating/using/workflow-operating-principles.md)
* [A propos de l'import et de l'export de données](../../automating/using/about-data-import-and-export.md)
* [Cas pratique : création d'une diffusion email une fois par semaine](../../automating/using/workflow-weekly-offer.md)
* [Cas pratique : création d'une diffusion segmentée sur la localisation](../../automating/using/workflow-segmentation-location.md)
* [Cas pratique : création de diffusions avec un complément](../../automating/using/workflow-created-query-with-complement.md)
* [Cas pratique : workflow de reciblage envoyant une nouvelle diffusion aux personnes n'ayant pas ouvert l'email](../../automating/using/workflow-cross-channel-retargeting.md)
