---
title: Prise en main des processus et de la gestion des données
description: Automatisez les processus avec des workflows, gérez les données et les audiences, envoyez des messages, et bien plus encore.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 100%

---

# Prise en main des processus et de la gestion des données {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Activités de workflow</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Cas pratiques</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrage des données</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Import/export des données</a></p></td></tr>
</table>

Adobe Campaign propose un environnement graphique qui permet de construire des processus complexes englobant segmentation, exécution de campagnes, manipulation de fichiers, validations, etc. Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d&#39;importer ses enregistrements dans la base de données Adobe Campaign.

Les workflows peuvent intervenir dans différents contextes, par exemple :

* Ciblage afin de gérer des audiences ou envoyer des messages.
* Data management (ETL) pour manipuler des données.
* Import de données dans la base de Campaign.
* Processus techniques tels que les tâches de nettoyage de la base (cleanup), la récupération des informations de tracking, etc.

>[!IMPORTANT]
>
> Adobe recommande à ses clients de ne pas exécuter plus de 20 workflows actifs simultanément ainsi que de hiérarchiser et d&#39;étaler l&#39;exécution des workflows dans le temps. Pour en savoir plus, consultez les bonnes pratiques disponibles sur [cette page](../../automating/using/best-practices-workflows.md).

## Activités de workflow {#workflow-activities}

Différentes activités sont à votre disposition pour vous aider à concevoir vos workflows.

Les [activités de ciblage](../../automating/using/about-targeting-activities.md) permettent de construire une ou plusieurs cibles en définissant des ensembles, puis en partitionnant ou en combinant ces ensembles à l’aide des opérations d’intersection, d’union ou d’exclusion.

Avec les [activités d’exécution](../../automating/using/about-execution-activities.md), vous pouvez coordonner un workflow et ses activités, tandis que les [activités de canal](../../automating/using/about-channel-activities.md) permettent de combiner des canaux de communication de Campaign Standard pour créer des workflows cross-canal.

Enfin, les [activités de data Management](../../automating/using/about-data-management-activities.md) permettent de manipuler les données contenues dans votre base de données.

En savoir plus :

* [Construire un workflow](../../automating/using/building-a-workflow.md)
* [Exécuter un workflow](../../automating/using/about-workflow-execution.md)
* [Bonnes pratiques relatives aux workflows](../../automating/using/best-practices-workflows.md)

## Filtrage des données {#filter-data}

Utilisez le **requêteur** pour filtrer les données de votre base de données et créer une population afin de cibler plus efficacement vos destinataires. Le requêteur permet de mettre en œuvre différentes actions dans Campaign Standard : créer des audiences de type Requête, définir des cibles de diffusion ou des populations dans les activités de workflow.

Le requêteur contient des **règles et des filtres prédéfinis** pour accélérer et faciliter le filtrage. Cependant, vous pouvez également utiliser des fonctionnalités **avancées d’édition d’expressions**. Vous pouvez ainsi saisir manuellement des conditions et utiliser des fonctions pour créer vos propres règles.

En savoir plus :

* [Édition de requêtes](../../automating/using/editing-queries.md)
* [Édition avancée d&#39;expressions](../../automating/using/advanced-expression-editing.md)
* [Liste des fonctions](../../automating/using/list-of-functions.md)

## Import/export des données {#import-export-data}

Campaign Standard propose plusieurs **fonctionnalités de data Management** pour importer et exporter des données.

[Les activités de data Management des workflows](../../automating/using/about-data-management-activities.md) permettent d’importer des données, d’effectuer des mises à jour en masse des champs, de recevoir ou d’envoyer des fichiers ou de lier des données non identifiées à des ressources existantes.

Avec les [modèles d’import](../../automating/using/importing-data-with-import-templates.md), vous pouvez gérer certains types d’imports définis par les administrateurs à l’aide de fonctions d’import simplifiées.

L’[export de logs](../../automating/using/exporting-logs.md) permet d’exporter les données contenues dans les logs à l’aide d’un workflow simple. Vous pouvez ainsi analyser les résultats de vos campagnes marketing dans vos propres outils de reporting ou de BI.

Utilisez les [packages](../../automating/using/managing-packages.md) pour échanger des ressources entre différentes instances de Campaign, par exemple pour répliquer la configuration d&#39;une instance ou pour transférer des données d&#39;un serveur à un autre, y compris des ressources personnalisées.

Enfin, l’[export de listes](../../automating/using/exporting-lists.md) permet d’exporter des listes issues de Campaign Standard, par exemple la liste des profils de test, la liste des adresses email mises en quarantaine, etc.

En savoir plus :

* [Import et export de données](../../automating/using/about-data-import-and-export.md)
* [Cas pratique : export/import de ressources personnalisées](../../automating/using/exporting-importing-custom-resources.md)

## Autres ressources

* [Vidéos contenant des tutoriels relatifs aux processus et à la gestion des données](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=fr)
* [Workflows techniques](../../administration/using/technical-workflows.md)
* [Prise en main du modèle de données de Campaign Standard](../../developing/using/get-started-data-model.md)
