---
title: Commencer avec les processus et les datas Management
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
source-git-commit: a9fbf0479019dfbe2964c517a0370f015d0f380a
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 30%

---


# Commencer avec les processus et les datas Management {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">activités de processus</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Cas pratiques</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrage des données</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importer/exporter des données</a></p></td></tr>
</table>

L&#39;Adobe Campaign offre un environnement graphique complet qui vous permet de concevoir des processus complexes tels que la segmentation, l&#39;exécution des campagnes, le traitement des fichiers, etc. Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d&#39;importer ses enregistrements dans la base de données Adobe Campaign.

Un workflow peut également faire intervenir des utilisateurs, pour leur affecter une tâche ou demander la validation d&#39;une tâche accomplie. Ainsi, il est possible d&#39;assigner une tâche à un ou plusieurs utilisateurs qui seront chargés de saisir son contenu ou spécifier sa cible, puis de faire valider un BAT avant d&#39;envoyer un message.

Les workflows peuvent intervenir dans différents contextes, par exemple :

* Ciblage afin de gérer des audiences ou envoyer des messages.
* Data management (ETL) pour manipuler des données.
* Import de données dans la base de Campaign.
* Processus techniques tels que les tâches de nettoyage de la base (cleanup), la récupération des informations de tracking, etc.

## activités de processus {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Différentes activités sont à votre disposition pour vous aider à concevoir vos workflows.

[Les activités](../../automating/using/about-targeting-activities.md) de ciblage vous permettent de créer une ou plusieurs cibles en définissant des ensembles et en les fractionnant ou en les combinant à l’aide d’opérations d’intersection, d’union ou d’exclusion.

Avec les activités [](../../automating/using/about-execution-activities.md)d’exécution, coordonnez votre flux de travail et ses activités, tandis que les activités [](../../automating/using/about-channel-activities.md) Canaux vous permettent de combiner des canaux de communication Campaign Standards pour créer des workflows entre canaux.

Enfin, les activités [de](../../automating/using/about-data-management-activities.md) Data Management vous permettent de manipuler les données de votre base de données.

En savoir plus:

* [Construire un workflow](../../automating/using/building-a-workflow.md)
* [Exécuter un workflow](../../automating/using/about-workflow-execution.md)
* [Bonnes pratiques relatives aux workflows](../../automating/using/best-practices-workflows.md)

## Filtrage des données {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Tirez parti de l’éditeur **de** requêtes pour filtrer les données de votre base de données et créer une population afin de mieux cible vos destinataires. L’éditeur de requêtes permet d’effectuer plusieurs actions dans le Campaign Standard : créer des audiences de type Requête, définir des cibles de diffusion ou des populations dans les activités de processus.

L’éditeur de requêtes est fourni avec **des filtres prédéfinis et des règles** pour un filtrage rapide et facile. Cependant, vous pouvez également utiliser des fonctions **avancées de modification** des expressions. Vous pouvez ainsi saisir manuellement des conditions et utiliser des fonctions afin de créer vos propres règles.

En savoir plus:

* [Edition de requêtes](../../automating/using/editing-queries.md)
* [Edition avancée d’expressions](../../automating/using/advanced-expression-editing.md)
* [Liste des fonctions](../../automating/using/list-of-functions.md)

## Importer/exporter des données {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard est fourni avec plusieurs fonctionnalités **de** data Management pour importer et exporter des données.

[Les activités](../../automating/using/about-data-management-activities.md) de data Management de Workflows vous permettent d&#39;importer des données, d&#39;effectuer des mises à jour massives sur les champs, de recevoir ou d&#39;envoyer des fichiers ou de lier des données non identifiées à des ressources existantes.

Avec [les Modèles d&#39;import](../../automating/using/importing-data-with-import-templates.md), gérez certains types d&#39;importation définis par les administrateurs grâce à des fonctions d&#39;importation simplifiées.

[L’exportation de journaux](../../automating/using/exporting-logs.md) vous permet d’exporter des données de journaux par le biais d’un processus simple, ce qui vous permet d’analyser les résultats de vos campagnes marketing dans vos propres outils de rapports ou de BI.

Tirez parti des [packages](../../automating/using/managing-packages.md) pour échanger des ressources entre différentes instances de campagne, par exemple pour répliquer la configuration d’une instance ou pour transférer des données d’un serveur à un autre, y compris des ressources personnalisées.

Enfin, l&#39; [exportation de listes](../../automating/using/exporting-lists.md) vous permet d&#39;exporter toute liste à partir d&#39;un Campaign Standard, comme, par exemple, la liste des profils de test, la liste des adresses électroniques de quarantaines, etc.

En savoir plus:

* [Import et export de données](../../automating/using/about-data-import-and-export.md)
* [Cas pratique : export/import de ressources personnalisées](../../automating/using/exporting-importing-custom-resources.md)

## Autres ressources

* [Vidéos sur les processus et les datas Management](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Workflows techniques](../../administration/using/technical-workflows.md)
* [Commencer avec le modèle de données Campaign Standard](../../developing/using/get-started-data-model.md)
