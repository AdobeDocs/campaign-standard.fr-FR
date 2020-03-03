---
title: Meilleures pratiques relatives aux modèles de données dans Adobe Campaign Standard
description: Découvrez les meilleures pratiques lors de la conception de votre modèle de données Adobe Campaign Standard.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0aa1089ee744a86a95d344235feba7adb9150a4

---


# Meilleures pratiques du modèle de données{#data-model-best-practices}

Ce document présente les principales recommandations lors de la conception de votre modèle de données Adobe Campaign.


>[!NOTE]
>
>Pour créer et modifier des ressources afin d’étendre le modèle de données prédéfinies d’Adobe Campaign, reportez-vous à [cette section](../../developing/using/key-steps-to-add-a-resource.md).
>
>You can find a data model representation of the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).

## Présentation {#overview}

Le système Adobe Campaign est extrêmement flexible et peut être étendu au-delà de l’implémentation initiale. Cependant, même si les possibilités sont infinies, il est essentiel de prendre des décisions judicieuses et de construire des bases solides pour commencer à concevoir votre modèle de données.

Ce document présente les cas d’utilisation courants et les bonnes pratiques pour apprendre à concevoir correctement votre outil Adobe Campaign.

## Architecture du modèle de données {#data-model-architecture}

Adobe Campaign Standard est un puissant système de gestion de campagne cross-canal qui peut vous aider à aligner vos stratégies en ligne et hors ligne pour créer des expériences client personnalisées.

### Approche axée sur le client {#customer-centric-approach}

Bien que la plupart des fournisseurs de services de messagerie communiquent avec les clients par le biais d’une approche centrée sur la liste, Adobe Campaign s’appuie sur une base de données relationnelle afin de tirer parti d’une vision plus large des clients et de leurs attributs.

Cette approche axée sur le client est présentée dans le graphique ci-dessous. La ressource **Profile** en gris représente la table client principale autour de laquelle tout est construit :

![](assets/customer-centric-data-model.png)

Le modèle de données par défaut d’Adobe Campaign est présenté dans cette [section](../../developing/using/datamodel-introduction.md).

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the master record. This master record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a master customer record which will be sent to Adobe Campaign.-->

### Données pour Adobe Campaign {#data-for-campaign}

Quelles données doivent être envoyées à Adobe Campaign ? Il est essentiel de déterminer les données requises pour vos activités marketing.

>[!NOTE]
>
>Adobe Campaign n’est pas un entrepôt de données. Par conséquent, n’essayez pas d’importer tous les clients possibles et leurs informations associées dans Adobe Campaign.

Pour décider si un attribut est nécessaire ou non dans Adobe Campaign, déterminez s’il tomberait dans l’une des catégories suivantes :
* Attribut utilisé pour la **segmentation**
* Attribut utilisé pour les processus **de gestion des** données (calcul agrégé, par exemple)
* Attribut utilisé pour la **personnalisation**
* Attribut utilisé pour la **création de rapports** (les rapports peuvent être créés à partir de données de profil personnalisées)

Si vous ne tombez dans aucune de ces catégories, il est probable que vous n’ayez pas besoin de cet attribut dans Adobe Campaign.

### Types de données {#data-types}

Pour garantir une architecture et des performances optimales de votre système, suivez les bonnes pratiques ci-dessous pour configurer les données dans Adobe Campaign :
* La longueur d’un champ de chaîne doit toujours être définie avec la colonne. Par défaut, la longueur maximale dans Adobe Campaign est de 255 caractères, mais Adobe conseille de raccourcir le champ si vous savez déjà que la taille ne dépassera pas une longueur plus courte.
* Dans Adobe Campaign, un champ plus court est acceptable que dans le système source si vous êtes certain que la taille du système source a été surestimée et n’aurait pas été atteinte. Cela peut signifier une chaîne plus courte ou un entier plus petit dans Adobe Campaign.

## Configuration de la structure des données {#configuring-data-structure}

Cette section décrit les meilleures pratiques lors de la [configuration de la structure](../../developing/using/configuring-the-resource-s-data-structure.md)de données d’une ressource.

### Identificateurs {#identifiers}

Les ressources Adobe Campaign comportent trois identifiants et il est possible d’ajouter un identifiant supplémentaire.

Le tableau suivant décrit ces identifiants et leur objectif.

>[!NOTE]
>
>Le nom d’affichage est le nom du champ affiché pour l’utilisateur via l’interface utilisateur d’Adobe Campaign. Le nom technique est le nom réel du champ dans la définition de la ressource (et le nom de la colonne de la table).

| Nom d’affichage | Nom technique | Description | Bonnes pratiques |
|--- |--- |--- |--- |
|  | PKey | <ul><li>La clé PKey est la clé primaire physique d’une table Adobe Campaign.</li><li>Cet identifiant est généralement propre à une instance Adobe Campaign spécifique.</li><li>Dans Adobe Campaign Standard, cette valeur n’est pas visible pour l’utilisateur final.</li></ul> | <ul><li>Par le biais du système [](../../api/using/about-campaign-standard-apis.md)API, il est possible de récupérer une valeur PKey (qui est une valeur générée/hachée et non la clé physique).</li><li>Il n’est pas recommandé de l’utiliser à d’autres fins que la récupération, la mise à jour ou la suppression d’enregistrements via l’API.</li></ul> |
| ID | name ou internalName | <ul><li>Ces informations sont un identifiant unique d’un enregistrement dans un tableau. Cette valeur peut être mise à jour manuellement.</li><li>Cet identifiant conserve sa valeur lorsqu’il est déployé dans une autre instance d’Adobe Campaign. Il doit avoir un nom différent de la valeur générée pour pouvoir être exporté via un package.</li><li>Il ne s’agit pas de la clé primaire réelle de la table.</li></ul> | <ul><li>N’utilisez pas de caractères spéciaux tels que l’espace &quot;&quot;, la demi-colonne &quot;:&quot; ou le tiret &quot;-&quot;.</li><li>Tous ces caractères seraient remplacés par un trait de soulignement &quot;_&quot; (caractère autorisé). Par exemple, &quot;abc-def&quot; et &quot;abc:def&quot; sont stockés en tant que &quot;abc_def&quot; et remplacent les uns des autres.</li></ul> |
| Libellé | label | <ul><li>Le libellé est l’identifiant de l’entreprise d’un objet ou d’un enregistrement dans Adobe Campaign.</li><li>Cet objet autorise des espaces et des caractères spéciaux.</li><li>Il ne garantit pas le caractère unique d&#39;un enregistrement.</li></ul> | <ul><li>Il est recommandé de déterminer une structure pour les libellés de vos objets.</li><li>Il s’agit de la solution la plus conviviale pour identifier un enregistrement ou un objet pour un utilisateur d’Adobe Campaign.</li></ul> |
| Identifiant ACS | acsId | <ul><li>Un identifiant supplémentaire peut être généré : l&#39;ID [ACS](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>Comme PKey ne peut pas être utilisé dans l’interface utilisateur d’Adobe Campaign, il s’agit d’une solution permettant d’obtenir une valeur unique générée lors de l’insertion d’un enregistrement de profil.</li><li>La valeur ne peut être générée automatiquement que si l’option est activée dans la ressource avant qu’un enregistrement ne soit inséré dans Adobe Campaign.</li></ul> | <ul><li>Cet UUID peut être utilisé comme clé de réconciliation.</li><li>Un ID ACS généré automatiquement ne peut pas être utilisé comme référence dans un processus ou dans une définition de package.</li><li>Cette valeur est spécifique à une instance Adobe Campaign.</li></ul> |

### des clés d&#39;identification ;{#keys}

Chaque ressource créée dans Adobe Campaign doit comporter au moins une clé [d’](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)identification unique.

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Lorsque vous créez une ressource personnalisée, vous disposez de deux options :

* Combinaison de clé générée automatiquement et de clé personnalisée interne. Cette option est intéressante si votre clé système est une clé composite ou non un entier. Les entiers offriront des performances plus élevées dans les grandes tables et se joindront aux autres tables.
* Utilisation de la clé primaire comme clé primaire du système externe. Cette solution est généralement préférable, car elle simplifie l’approche d’importation et d’exportation des données, avec une clé cohérente entre les différents systèmes.

Les clés d’identification ne doivent pas être utilisées comme référence dans les processus.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### des index ;{#indexes}

Adobe Campaign ajoute automatiquement un [index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) à toutes les clés principales et internes définies dans une ressource.

* Adobe recommande de définir des index supplémentaires, car ils peuvent améliorer les performances.
* Toutefois, n’ajoutez pas trop d’index car ils utilisent de l’espace sur la base de données. De nombreux indices peuvent également avoir un impact négatif sur les performances.
* Sélectionnez soigneusement les index à définir.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Liens {#links}

La définition de liens avec d’autres ressources est présentée dans [cette section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* Bien qu’il soit possible de joindre n’importe quel tableau dans un processus, Adobe recommande de définir des liens communs entre les ressources directement dans la définition de la structure de données.
* Le lien doit être défini en fonction des données réelles contenues dans les tableaux. Une mauvaise définition peut avoir un impact sur les données récupérées via des liens, par exemple la duplication inattendue d’enregistrements.
* Nommez votre lien de manière cohérente avec le nom de la ressource : le nom du lien doit aider à comprendre ce qu&#39;est la table distante.
* Ne donnez pas le nom d’un lien avec &quot;id&quot; comme suffixe. Par exemple, nommez-le &quot;transaction&quot; plutôt que &quot;transactionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Performances {#performance}

Afin d’assurer de meilleures performances à tout moment, suivez les bonnes pratiques ci-dessous.

### Recommandations générales {#general-recommendations}

* Evitez d’utiliser des opérations telles que &quot;CONTAINS&quot; dans les requêtes. Si vous savez ce qui est attendu et souhaitez être filtré, appliquez la même condition avec un opérateur &quot;ÉGAL À&quot; ou d’autres opérateurs de filtre spécifiques.
* Evitez de vous joindre aux champs non indexés lors de la création de données dans des processus.
* Essayez de vous assurer que les processus tels que l’importation et l’exportation se produisent en dehors des heures de bureau.
* Assurez-vous qu&#39;il y ait un horaire pour toutes les activités quotidiennes et respectez le calendrier.
* Si un ou quelques processus quotidiens échouent et s’il est obligatoire de les exécuter le même jour, assurez-vous qu’il n’y a pas de processus conflictuels en cours d’exécution au démarrage du processus manuel, car cela pourrait affecter les performances du système.
* Assurez-vous qu’aucune campagne quotidienne n’est exécutée pendant le processus d’importation ou lorsqu’un processus manuel est exécuté.
* Utilisez un ou plusieurs tableaux de référence plutôt que de dupliquer un champ dans chaque ligne. Lorsque vous utilisez des paires clé/valeur, il est préférable de choisir une clé numérique.
* Une chaîne courte reste acceptable. Si des tableaux de références sont déjà en place dans un système externe, réutiliser le même type facilitera l’intégration des données avec Adobe Campaign.

### Relations de un à plusieurs {#one-to-many-relationships}

* La conception des données a un impact sur la convivialité et la fonctionnalité. Si vous concevez votre modèle de données avec de nombreuses relations de type &quot;un à plusieurs&quot;, il devient plus difficile pour les utilisateurs de construire une logique significative dans l’application. Il peut s’avérer difficile pour les spécialistes du marketing non technique de construire et de comprendre correctement la logique de filtre &quot;un à plusieurs&quot;.
* Il est bon d&#39;avoir tous les champs essentiels dans un tableau car cela facilite la création de requêtes par les utilisateurs. Il est parfois également judicieux de dupliquer certains champs d’un tableau à l’autre si cela permet d’éviter une jointure.
* Certaines fonctionnalités intégrées ne pourront pas faire référence à des relations de type &quot;un à plusieurs&quot;, par exemple la formule de pondération d’offre et les livraisons.

### Grandes tables {#large-tables}

Vous trouverez ci-dessous quelques bonnes pratiques à suivre lors de la conception de votre modèle de données à l’aide de tableaux volumineux et de jointures complexes.

* Réduisez le nombre de colonnes, notamment en identifiant celles qui ne sont pas utilisées.
* Optimisez les relations du modèle de données en évitant les jointures complexes, telles que les jointures sur plusieurs conditions et/ou plusieurs colonnes.
* Pour les clés de jointure, utilisez toujours des données numériques plutôt que des chaînes de caractères.
* Réduisez autant que possible la profondeur de rétention du journal. Si vous avez besoin d’un historique plus détaillé, vous pouvez agréger le calcul et/ou gérer des tables de journaux personnalisées pour stocker un historique plus volumineux.