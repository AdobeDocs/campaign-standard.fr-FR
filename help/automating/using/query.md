---
solution: Campaign Standard
product: campaign
title: Requête
description: L’activité Requête permet de filtrer et d’extraire une population d’éléments de la base de données Adobe Campaign.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 100%

---


# Requête{#query}

## Description {#description}

![](assets/query.png)

L’activité **[!UICONTROL Requête]** permet de filtrer et d’extraire une population d’éléments de la base de données Adobe Campaign. Vous pouvez définir des **[!UICONTROL Données additionnelles]** pour la population ciblée via un onglet dédié. Ces données sont stockées dans des colonnes additionnelles et sont exploitables uniquement pour le workflow en cours.

L’activité utilise l’outil d’édition de requêtes, dont le fonctionnement est détaillé dans une [section dédiée](../../automating/using/editing-queries.md#about-query-editor).

**Rubriques connexes :**

* [Exemples de requêtes ](../../automating/using/query-samples.md)
* [Cas pratique : workflow de reciblage envoyant une nouvelle diffusion aux personnes n’ayant pas ouvert l’email](../../automating/using/workflow-cross-channel-retargeting.md)

## Contexte d’utilisation {#context-of-use}

L’activité **[!UICONTROL Requête]** peut être utilisée dans plusieurs cas d’utilisation type :

* segmentation d’individus afin de définir la cible d’un message, une audience, etc.
* enrichissement de données de toute table de la base Adobe Campaign
* export des données.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Requête]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent. Par défaut, l’activité est pré-paramétrée pour rechercher des profils.
1. Si vous souhaitez effectuer la requête sur une autre ressource que celle des profils, accédez à l’onglet **[!UICONTROL Propriétés]** de l’activité et sélectionnez une **[!UICONTROL Ressource]** et une **[!UICONTROL Dimension de ciblage]**.

   La **[!UICONTROL Ressource]** permet d’affiner les filtres affichés dans la palette tandis que la **[!UICONTROL Dimension de ciblage]**, contextuelle à la ressource sélectionnée, correspond au type de population que vous souhaitez obtenir (profils identifiés, diffusions, etc.).

   Voir à ce sujet [Dimensions de ciblage et ressources](#targeting-dimensions-and-resources).

1. Depuis l’onglet **[!UICONTROL Cible]**, effectuez votre requête en définissant et combinant des règles.
1. Vous pouvez définir des **[!UICONTROL Données additionnelles]** pour la population ciblée via un onglet dédié. Ces données sont stockées dans des colonnes additionnelles et sont exploitables uniquement pour le workflow en cours. Vous pouvez notamment ajouter des données provenant des tables de la base Adobe Campaign liées à la dimension de ciblage de la requête. Consultez la section [Enrichir des données](#enriching-data).

   >[!NOTE]
   >
   >Par défaut, l’option **[!UICONTROL Supprimer les doublons (DISTINCT)]** est cochée dans les **[!UICONTROL Options avancées]** de l’onglet **[!UICONTROL Données additionnelles]** de la requête. Pour des raisons de performance, il est recommandé de décocher cette option si l’activité **[!UICONTROL Requête]** contient de nombreuses données additionnelles (à partir de 100) définies. Sachez que si cette option est décochée, vous pouvez obtenir des doublons, selon les données faisant l’objet de la requête.

1. Dans l’onglet **[!UICONTROL Transition]**, l’option **[!UICONTROL Activer une transition sortante]** permet d’ajouter une transition sortante après l’activité de requête, et ce même si elle ne récupère pas de données.

   Le code segment de la transition sortante peut être personnalisé à l&#39;aide d&#39;une expression standard et de variables d&#39;événements (voir [cette page](../../automating/using/customizing-workflow-external-parameters.md)).

1. Validez le paramétrage de l’activité et enregistrez le workflow.

## Dimensions de ciblage et ressources      {#targeting-dimensions-and-resources}

Les dimensions de ciblage et les ressources permettent de définir sur quels éléments reposera une requête pour déterminer la cible d’une diffusion.

Elles sont configurées dans les [mappings de ciblage](../../administration/using/target-mappings-in-campaign.md) et définies lors de la création d’un workflow, dans l’onglet **[!UICONTROL Propriétés]** d’une activité de requête.

>[!NOTE]
>
>La dimension de ciblage peut être également définie lors de la création d’une audience (voir [cette section](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Les dimensions de ciblage et les ressources sont liées. Les dimensions de ciblage disponibles dépendent donc de la ressource sélectionnée.

Par exemple, pour la ressource **[!UICONTROL Profils (profile)]**, les dimensions de ciblage suivantes seront disponibles :

![](assets/targeting_dimension2.png)

Tandis que pour les **[!UICONTROL Diffusions (delivery)]**, la liste proposera les dimensions de ciblage suivantes :

![](assets/targeting_dimension3.png)

Une fois la dimension de ciblage et la ressource indiquées, différents filtres sont disponibles dans la requête.

Exemple de filtres disponibles pour la ressource **[!UICONTROL Profils (profile)]** :

![](assets/targeting_dimension4.png)

Exemple de filtres disponibles pour la ressource **[!UICONTROL Diffusions (delivery)]** :

![](assets/targeting_dimension5.png)

Par défaut, la dimension de ciblage et la ressource sont définies pour cibler des profils. Il peut toutefois s’avérer utile d’utiliser une ressource différente de la dimension de ciblage si vous souhaitez rechercher un enregistrement spécifique dans une table distante.

Pour plus d’informations à ce sujet, reportez-vous à ce cas pratique : [Utiliser des ressources différentes des dimensions de ciblage](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## Enrichir des données {#enriching-data}

L’onglet **[!UICONTROL Données additionnelles]** des activités **[!UICONTROL Requête]**, **[!UICONTROL Requête incrémentale]** et **[!UICONTROL Enrichissement]** permet d’enrichir les données ciblées et de les transmettre aux activités suivantes du workflow, où elles pourront être exploitées. Il est notamment possible d’ajouter :

* des données simples.
* des agrégats.
* des collections.

Dans le cas des agrégats et des collections, un **[!UICONTROL Alias]** est automatiquement défini afin de donner un identifiant technique à une expression complexe. Cet alias, qui doit être unique, permet ainsi de retrouver simplement les agrégats et collections par la suite. Vous pouvez le modifier afin de lui donner un nom facilement reconnaissable.

>[!NOTE]
>
>Les alias doivent respecter les règles de syntaxe suivantes : seuls les caractères alphanumériques et les caractères &quot;_&quot; sont autorisés. Les alias sont sensibles à la casse. L’alias doit commencer par le caractère &quot;@&quot;. Le caractère suivant immédiatement le &quot;@&quot; ne doit pas être numérique. Par exemple : @myAlias_1 et @_1Alias sont corrects ; @myAlias#1 et @1Alias sont incorrects.

Après avoir ajouté des données additionnelles, vous pouvez appliquer un niveau de filtre supplémentaire sur les données initialement ciblées en créant des conditions basées sur les données additionnelles définies.

>[!NOTE]
>
>Par défaut, l’option **[!UICONTROL Supprimer les doublons (DISTINCT)]** est cochée dans les **[!UICONTROL Options avancées]** de l’onglet **[!UICONTROL Données additionnelles]** de la requête. Pour des raisons de performance, il est recommandé de décocher cette option si l’activité **[!UICONTROL Requête]** contient de nombreuses données additionnelles (à partir de 100) définies. Sachez que si cette option est décochée, vous pouvez obtenir des doublons, selon les données faisant l’objet de la requête.

Vous trouverez dans [cette section](../../automating/using/personalizing-email-with-additional-data.md) un cas pratique de la personnalisation d’un email contenant des données supplémentaires.

### Ajouter un champ simple      {#adding-a-simple-field}

En ajoutant un champ simple comme donnée additionnelle, celui-ci devient directement visible dans la transition sortante de l’activité. Cela permet par exemple de vérifier que les données issues de la requête sont celles souhaitées.

1. Depuis l’onglet **[!UICONTROL Données additionnelles]**, ajoutez un nouvel élément.
1. Dans la fenêtre qui s’ouvre, au niveau du champ **[!UICONTROL Expression]**, sélectionnez l’un des champs disponibles directement dans la dimension de ciblage ou dans l’une des dimensions liées. Vous pouvez éditer des expressions et utiliser des fonctions ou des calculs simples (hors agrégat) à partir des champs de la dimension.

   Un **[!UICONTROL Alias]** est automatiquement créé si vous éditez une expression qui n’est pas un simple chemin XPATH (par exemple : &quot;Year(&lt;@birthDate>)&quot;). Si vous le souhaitez, vous pouvez modifier ce dernier. Si vous sélectionnez un champ uniquement (par exemple : &quot;@age&quot;), il n’est pas nécessaire de définir un **[!UICONTROL Alias]**.

1. Sélectionnez **[!UICONTROL Ajouter]** pour valider l’ajout du champ dans les données additionnelles. Lorsque la requête sera exécutée, une colonne supplémentaire correspondant au champ ajouté sera présente dans la transition sortante de l’activité.

![](assets/enrichment_add_simple_field.png)

### Ajouter un agrégat      {#adding-an-aggregate}

Les agrégats permettent de calculer des valeurs à partir de champs de la dimension de ciblage ou de champs des dimensions liées à la dimension de ciblage. Par exemple : la moyenne des achats réalisés par un profil.
Lorsque vous utilisez l’agrégat avec une requête, sa fonction peut revenir à zéro ce qui est alors considéré comme NULL. Utilisez l’onglet **[!UICONTROL Affiner la cible]** de votre requête pour filtrer la valeur agrégée :

* si vous voulez des valeurs nulles, vous devez filtrer sur **[!UICONTROL est Null]**.
* si vous ne souhaitez pas de valeurs nulles, filtrez sur **[!UICONTROL n’est pas Null]**.

Veuillez noter que si vous devez effectuer un tri sur votre agrégat, vous devez filtrer les valeurs nulles, sinon la valeur NULL apparaîtra comme le nombre le plus élevé.

1. Depuis l’onglet **[!UICONTROL Données additionnelles]**, ajoutez un nouvel élément.
1. Dans la fenêtre qui s’ouvre, sélectionnez la collection que vous souhaitez utiliser pour créer votre agrégat au niveau du champ **[!UICONTROL Expression]**.

   Un **[!UICONTROL Alias]** est automatiquement créé. Si vous le souhaitez, vous pouvez modifier ce dernier en revenant à l’onglet **[!UICONTROL Données additionnelles]** de la requête.

   La fenêtre de définition des agrégats s’ouvre.

1. Définissez un agrégat depuis l’onglet **[!UICONTROL Données]**. En fonction du type d’agrégat sélectionné, seuls les éléments dont le type de données est compatible sont disponibles au niveau du champ **[!UICONTROL Expression]**. Par exemple, il n’est possible de calculer une somme qu’avec des données numériques.

   ![](assets/enrichment_add_aggregate.png)

   Vous pouvez ajouter plusieurs agrégats portant sur les champs de la collection sélectionnée. Veillez à définir des libellés explicites afin de pouvoir distinguer les différentes colonnes dans le détail des données transmises en sortie de l’activité.

   Vous pouvez également modifier les alias définis automatiquement pour chaque agrégat.

   ![](assets/enrichment_add_aggregate2.png)

1. Au besoin, vous pouvez ajouter un filtre afin de limiter les données prises en compte.

   Reportez-vous à la section [Filtrer les données ajoutées](#filtering-added-data).

1. Sélectionnez **[!UICONTROL Valider]** pour finaliser l’ajout des agrégats.

>[!NOTE]
>
>Vous ne pouvez pas créer d’expression contenant un agrégat directement à partir du champ **[!UICONTROL Expression]** de la fenêtre **[!UICONTROL Nouvelles données additionnelles]**.

### Ajouter une collection {#adding-a-collection}

1. Depuis l’onglet **[!UICONTROL Données additionnelles]**, ajoutez un nouvel élément.
1. Dans la fenêtre qui s’ouvre, sélectionnez la collection que vous souhaitez ajouter au niveau du champ **[!UICONTROL Expression]**. Un **[!UICONTROL Alias]** est automatiquement créé. Si vous le souhaitez, vous pouvez modifier ce dernier en revenant à l’onglet **[!UICONTROL Données additionnelles]** de la requête.
1. Sélectionnez **[!UICONTROL Ajouter]**. Une nouvelle fenêtre s’ouvre, vous permettant d’affiner les données de la collection que vous souhaitez afficher.
1. Dans l’onglet **[!UICONTROL Paramètres]**, sélectionnez **[!UICONTROL Collection]** et définissez le nombre de lignes de la collection que vous souhaitez ajouter. Par exemple, si vous souhaitez retrouver les trois achats les plus récents réalisés par chaque profil, indiquez &quot;3&quot; au niveau du champ **[!UICONTROL Nombre de lignes à retourner]**.

   >[!NOTE]
   >
   >Vous devez indiquer un nombre supérieur ou égal à 1.

1. Depuis l’onglet **[!UICONTROL Données]**, définissez les champs de la collection que vous souhaitez afficher pour chaque ligne.

   ![](assets/enrichment_add_collection.png)

1. Si vous le souhaitez, vous pouvez ajouter un filtre afin de limiter les lignes de la collection prises en compte.

   Reportez-vous à la section [Filtrer les données ajoutées](#filtering-added-data).

1. Si vous le souhaitez, vous pouvez définir un tri sur les données.

   Par exemple, si vous avez sélectionné 3 lignes à renvoyer dans l’onglet **[!UICONTROL Paramètres]**, et que vous souhaitez récupérer les trois achats les plus récents, vous pouvez définir un tri décroissant sur le champ &quot;date&quot; de la collection qui correspond aux transactions.

1. Reportez-vous à la section [Trier les données ajoutées](#sorting-additional-data).
1. Sélectionnez **[!UICONTROL Valider]** pour finaliser l’ajout de la collection.

### Filtrer les données ajoutées {#filtering-added-data}

Lorsque vous ajoutez un agrégat ou une collection, vous avez la possibilité de spécifier un filtre supplémentaire afin de limiter les données que vous souhaitez afficher.

Par exemple, si vous souhaitez ne traiter que les lignes d’une collection de transactions dont le montant est supérieur à 50 euros, vous pouvez ajouter une condition sur le champ correspondant au montant de la transaction depuis l’onglet **[!UICONTROL Filtre]**.

![](assets/enrichment_filter_data.png)

### Trier les données ajoutées {#sorting-additional-data}

Lorsque vous ajoutez un agrégat ou une collection aux données d’une requête, vous pouvez indiquer si vous souhaitez appliquer un tri - croissant ou décroissant - basé sur la valeur du champ ou de l’expression défini.

Par exemple, si vous souhaitez ne conserver que la transaction la plus récente effectuée par un profil, indiquez &quot;1&quot; au niveau du champ **[!UICONTROL Nombre de lignes à retourner]** de l’onglet **[!UICONTROL Paramètres]**, et appliquez un tri décroissant sur le champ correspondant à la date de la transaction via l’onglet **[!UICONTROL Tri]**.

![](assets/enrichment_sort_data.png)

### Filtrer les données ciblées en fonction des données additionnelles {#filtering-the-targeted-data-according-to-additional-data}

Lorsque vous avez ajouté des données additionnelles, un nouvel onglet **[!UICONTROL Affiner la cible]** apparaît dans la **[!UICONTROL Requête]**. Cet onglet vous permet d’appliquer un filtrage supplémentaire sur les données ciblées initialement dans l’onglet **[!UICONTROL Cible]**, en prenant en compte les données ajoutées.

Par exemple, si vous avez ciblé tous les profils ayant réalisé au moins une transaction et qu’un agrégat calculant la moyenne du montant des transactions effectuées pour chaque profil a été ajouté dans les **[!UICONTROL Données additionnelles]**, vous pouvez affiner la population calculée initialement à l’aide de cette moyenne.

Pour cela, dans l’onglet **[!UICONTROL Affiner la cible]**, ajoutez simplement une condition sur cette donnée additionnelle.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
