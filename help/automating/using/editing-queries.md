---
solution: Campaign Standard
product: campaign
title: Edition de requêtes
description: Créez une population grâce aux règles et aux filtres prédéfinis.
audience: automating
content-type: reference
topic-tags: filtering-data
context-tags: queryFilter,overview;audience,main
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '787'
ht-degree: 100%

---


# Edition de requêtes{#editing-queries}

## A propos de l&#39;éditeur de requêtes {#about-query-editor}

L&#39;outil d&#39;édition de requêtes est un assistant permettant de filtrer des données contenues dans la base de données Adobe Campaign.

Cette fonctionnalité vous permet de créer une population afin de mieux cibler les destinataires grâce aux règles et aux filtres prédéfinis.

Cet outil est partagé par plusieurs fonctionnalités de l&#39;application :

* création d&#39;une **audience** de type **Requête**
* définition de la cible d&#39;un **email**
* définition d&#39;une population dans des activités de **workflows**.

## Interface de l&#39;éditeur de requêtes   {#query-editor-interface}

L&#39;éditeur de requêtes se compose d&#39;une **Palette** et d&#39;un **Espace de travail**.

![](assets/query_editor_overview.png)

### Palette   {#palette}

La palette, située sur la gauche de l&#39;éditeur, est divisée en deux onglets, composés d&#39;éléments répartis dans des blocs thématiques. Ces onglets sont :

* les **raccourcis**, disponibles par défaut, ou créés par l&#39;administrateur de l&#39;instance. Vous y retrouvez des champs, des noeuds, des groupements, des liens 1-1, des liens 1-N et des filtres prédéfinis.
* l&#39;**explorateur**, qui permet d&#39;accéder à l&#39;ensemble des champs disponibles dans la ressource cible : noeuds, élements de groupement, liens (1-1 et 1-N).

Les éléments contenus dans les onglets doivent être déplacés dans l&#39;espace de travail afin d&#39;être paramétrés et pris en compte pour la requête. En fonction de la dimension de ciblage sélectionnée (voir [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources)), vous pouvez :

* sélectionner unitairement des audiences ou des profils
* utiliser des filtres prédéfinis
* définir des règles simples sur les champs de votre choix
* définir des règles avancées permettant d&#39;appliquer des fonctions sur certains champs.

### Espace de travail {#workspace}

L&#39;espace de travail est la zone centrale, dans laquelle vous pouvez paramétrer et combiner les règles, audiences et filtres prédéfinis ajoutés depuis la palette.

Lorsque vous déplacez un élément de la palette dans l&#39;espace de travail, une nouvelle fenêtre s&#39;ouvre et vous permet de [Créer une requête](#creating-queries).

## Créer une requête {#creating-queries}

L&#39;éditeur de requêtes peut être utilisé pour définir une audience ou un profil de test dans un message, une population dans un workflow et pour créer une audience de type Requête.

Les requêtes peuvent être définies dans la fenêtre **[!UICONTROL Audience]** lors de la création d&#39;une diffusion ou dans une activité de type **Requête** lors de la création d&#39;un workflow.

1. Déplacez un élément depuis la palette vers l&#39;espace de travail. La fenêtre d&#39;édition de la règle s&#39;ouvre.

   * pour un **champ** de type chaîne ou numérique, spécifiez l&#39;opérateur de comparaison et la valeur.

      ![](assets/query_editor_audience_definition2.png)

   * pour un **champ** de type date ou date et heure, vous pouvez choisir de définir une date précise, une intervalle entre deux dates précises ou une date ou période relative à la date d&#39;exécution de la requête.

      ![](assets/query_editor_date_field.png)

   * pour un **champ** de type booléen, cochez les cases associées aux valeurs possibles pour le champ.
   * pour un **groupement**, sélectionnez le champ du groupement sur lequel vous souhaitez créer la règle, puis définissez la condition de la même manière que pour les autres champs.

      ![](assets/query_editor_audience_definition4.png)

   * pour un lien de type **1-1** avec une autre ressource de la base, sélectionnez directement une valeur de la table ciblée.

      ![](assets/query_editor_audience_definition5.png)

   * pour un lien de type **1-N** avec une autre ressource de la base, vous pouvez définir une sous-requête sur les champs de cette seconde ressource.

      Spécifier une sous-condition n&#39;est pas obligatoire.

      Vous pouvez par exemple seulement sélectionner l&#39;opérateur **[!UICONTROL Existe]** sur le tracking des profils et valider la règle. La règle renverra tous les profils pour lesquels le tracking existe.

      ![](assets/query_editor_audience_definition6.png)

   * pour un **filtre prédéfini**, saisissez ou sélectionnez les éléments de votre choix en fonction des critères proposés.

      Pour faciliter l&#39;élaboration de requêtes complexes et répétitives, les administrateurs peuvent créer des filtres. Ceux-ci apparaissent dans l&#39;éditeur de requêtes sous la forme de règles pré-paramétrées et permettent de limiter le nombre d&#39;étapes à réaliser pour l&#39;utilisateur.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Donnez éventuellement un nom à votre règle. Ce nom est affiché au niveau de la règle dans l&#39;espace de travail. Si aucun nom n&#39;est défini, un texte automatique décrivant les conditions est affiché.
1. Pour combiner les éléments de l&#39;espace de travail, imbriquez-les afin de créer différents groupes et/ou niveaux de groupes. Vous pouvez alors sélectionner un opérateur logique afin de combiner les éléments de même niveau :

   * **[!UICONTROL ET]** : intersection de deux critères. Seuls les éléments répondant à chacun des critères sont comptabilisés.
   * **[!UICONTROL OU]** : union de deux critères. Les éléments répondant à au moins l’un des deux critères sont pris en compte.
   * **[!UICONTROL SAUF]** : critère d&#39;exclusion. Les éléments répondant au premier critère sont comptabilisés sauf s&#39;ils répondent également au second critère.

1. Vous pouvez à tout moment compter et prévisualiser les éléments ciblés par votre requête à l&#39;aide des boutons ![](assets/count.png) et ![](assets/preview.png) de la barre d&#39;actions.

   ![](assets/query_editor_combining_rules.png)

Si vous souhaitez modifier un élément de la requête, cliquez sur l&#39;icône d&#39;édition. La règle s&#39;ouvre telle qu&#39;elle a été paramétrée auparavant et vous pouvez alors effectuer les ajustements nécessaires.

Vos requêtes sont à présent créées et définies. Vous pouvez créer une population pour mieux personnaliser vos diffusions.

**Rubriques connexes :**

* [Fonctions avancées](../../automating/using/advanced-expression-editing.md)
* [Définir des filtres](../../developing/using/configuring-filter-definition.md)
* [Cas pratique : création d’une diffusion email hebdomadaire](../../automating/using/workflow-weekly-offer.md)
* [Cas pratique : création d’une diffusion segmentée sur la localisation](../../automating/using/workflow-segmentation-location.md)
* [Cas pratique : création de diffusions avec un complément](../../automating/using/workflow-created-query-with-complement.md)
* [Cas pratique : workflow de reciblage envoyant une nouvelle diffusion aux personnes n&#39;ayant pas ouvert l&#39;email](../../automating/using/workflow-cross-channel-retargeting.md)
