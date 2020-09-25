---
title: Prise en main des processus et de la gestion des données
description: Tirez parti des fonctionnalités de flux de travaux Adobe Campaign pour automatiser les processus grâce à un environnement graphique complet puissant. Découvrez comment charger des données, gérer des audiences, envoyer des messages, mettre en oeuvre des cycles de data Management, automatiser des processus techniques, etc.
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
source-git-commit: 1a7e6bf967cb1745ea357ad7ee054dc42397f6e2
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 90%

---


# Prise en main des processus et de la gestion des données{#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Activités de workflow</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Cas pratiques</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrage des données</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Import/export des données</a></p></td></tr>
</table>

adobe campaign offre un environnement graphique complet qui vous permet de concevoir des processus complexes tels que la segmentation, l’exécution de campagne, le traitement de fichiers, etc. Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d&#39;importer ses enregistrements dans la base de données Adobe Campaign.

Un workflow peut également faire intervenir des utilisateurs, pour leur affecter une tâche ou demander la validation d&#39;une tâche accomplie. Ainsi, il est possible d&#39;assigner une tâche à un ou plusieurs utilisateurs qui seront chargés de saisir son contenu ou spécifier sa cible, puis de faire valider un BAT avant d&#39;envoyer un message.

Les workflows peuvent intervenir dans différents contextes, par exemple :

* Ciblage afin de gérer des audiences ou envoyer des messages.
* Data management (ETL) pour manipuler des données.
* Import de données dans la base de Campaign.
* Processus techniques tels que les tâches de nettoyage de la base (cleanup), la récupération des informations de tracking, etc.

## Activités de workflow {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Différentes activités sont à votre disposition pour vous aider à concevoir vos workflows.

Les [activités de ciblage](../../automating/using/about-targeting-activities.md) permettent de construire une ou plusieurs cibles en définissant des ensembles, puis en partitionnant ou en combinant ces ensembles à l’aide des opérations d’intersection, d’union ou d’exclusion.

Avec les [activités d’exécution](../../automating/using/about-execution-activities.md), vous pouvez coordonner un workflow et ses activités, tandis que les [activités de canal](../../automating/using/about-channel-activities.md) permettent de combiner des canaux de communication de Campaign Standard pour créer des workflows cross-canal.

Enfin, les [activités de data Management](../../automating/using/about-data-management-activities.md) permettent de manipuler les données contenues dans votre base de données.

En savoir plus :

* [Construire un workflow](../../automating/using/building-a-workflow.md)
* [Exécuter un workflow](../../automating/using/about-workflow-execution.md)
* [Bonnes pratiques relatives aux workflows](../../automating/using/best-practices-workflows.md)

## Filtrage des données {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Utilisez l’**éditeur de requêtes** pour filtrer les données de votre base de données et créer une population afin de cibler plus efficacement vos destinataires. L’éditeur de requêtes permet de mettre en œuvre différentes actions dans Campaign Standard : créer des audiences de type Requête, définir des cibles de diffusion ou des populations dans les activités de workflow.

L’éditeur de requêtes contient des **règles et des filtres prédéfinis** pour accélérer et faciliter le filtrage. Cependant, vous pouvez également utiliser des fonctionnalités **avancées d’édition d’expressions**. Vous pouvez ainsi saisir manuellement des conditions et utiliser des fonctions pour créer vos propres règles.

En savoir plus :

* [Edition de requêtes](../../automating/using/editing-queries.md)
* [Edition avancée d’expressions](../../automating/using/advanced-expression-editing.md)
* [Liste des fonctions](../../automating/using/list-of-functions.md)

## Importation/exportation des données {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard propose plusieurs **fonctionnalités de data Management** pour importer et exporter des données.

[Les activités de data Management des workflows](../../automating/using/about-data-management-activities.md) permettent d’importer des données, d’effectuer des mises à jour en masse des champs, de recevoir ou d’envoyer des fichiers ou de lier des données non identifiées à des ressources existantes.

Avec les [modèles d’import](../../automating/using/importing-data-with-import-templates.md), vous pouvez gérer certains types d’imports définis par les administrateurs à l’aide de fonctions d’import simplifiées.

L’[export de logs](../../automating/using/exporting-logs.md) permet d’exporter les données contenues dans les logs à l’aide d’un workflow simple. Vous pouvez ainsi analyser les résultats de vos campagnes marketing dans vos propres outils de reporting ou de BI.

Utilisez les [packages](../../automating/using/managing-packages.md) pour échanger des ressources entre différentes instances de Campaign, par exemple pour répliquer la configuration d’une instance ou pour transférer des données d’un serveur à un autre, y compris des ressources personnalisées.

Enfin, l’[export de listes](../../automating/using/exporting-lists.md) permet d’exporter des listes issues de Campaign Standard, par exemple la liste des profils de test, la liste des adresses email mises en quarantaine, etc.

En savoir plus :

* [Import et export de données](../../automating/using/about-data-import-and-export.md)
* [Cas pratique : export/import de ressources personnalisées](../../automating/using/exporting-importing-custom-resources.md)

## Autres ressources

* [Vidéos contenant des tutoriels relatifs aux processus et à la gestion des données](https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Workflows techniques](../../administration/using/technical-workflows.md)
* [Prise en main du modèle de données de Campaign Standard](../../developing/using/get-started-data-model.md)
