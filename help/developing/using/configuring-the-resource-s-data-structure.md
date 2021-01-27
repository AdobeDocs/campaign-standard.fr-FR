---
solution: Campaign Standard
product: campaign
title: Configuration de la structure de données de la ressource
description: Découvrez comment configurer la structure de données.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: cusResource,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1840'
ht-degree: 100%

---


# Configuration de la structure de données de la ressource{#configuring-the-resource-s-data-structure}

Suite à la création d&#39;une ressource personnalisée, vous devez paramétrer la structure de données.

Lors de l&#39;édition de la ressource, dans l&#39;onglet **[!UICONTROL Structure de données]**, il est possible d&#39;ajouter :

* [des champs ;](#adding-fields-to-a-resource)
* [Clés d’identification](#defining-identification-keys)
* [des index ;](#defining-indexes)
* [des liens ;](#defining-links-with-other-resources)
* [des logs d&#39;envoi.](#defining-sending-logs-extension)

## Ajouter des champs à une ressource      {#adding-fields-to-a-resource}

Vous pouvez ajouter de nouveaux champs à une ressource pour stocker les données qui ne font pas partie du modèle de données d&#39;usine.

1. Utilisez le bouton **[!UICONTROL Créer un élément]** pour créer un champ.
1. Indiquez un libellé, un identifiant, un type de champ et définissez la longueur maximale autorisée pour ce champ.

   Le champ **[!UICONTROL Identifiant]** est obligatoire et doit être unique pour chaque champ ajouté.

   >[!NOTE]
   >
   >Utilisez 30 caractères au maximum.

   ![](assets/schema_extension_4.png)

1. Pour modifier l&#39;un des champs, cliquez sur le bouton **[!UICONTROL Editer les propriétés]**.

   ![](assets/schema_extension_24.png)

1. Dans l&#39;écran **[!UICONTROL Définition du champ]**, vous pouvez définir une catégorie qui servira pour l&#39;audience et le ciblage ou encore ajouter une description.

   ![](assets/schema_extension_5.png)

1. Cochez la case **[!UICONTROL Définir une liste de valeurs autorisées]** si vous devez spécifier les valeurs qui seront proposées à l&#39;utilisateur (valeurs d&#39;énumération).

   Cliquez ensuite sur **[!UICONTROL Créer un élément]** et indiquez un **[!UICONTROL Libellé]** et une **[!UICONTROL Valeur]**. Ajoutez autant de valeurs que nécessaire.

1. Cochez la case **[!UICONTROL Ajouter les champs d&#39;audit]** si vous souhaitez inclure les champs relatifs à la date de création, à l&#39;utilisateur qui a créé la ressource, à la date et à l&#39;auteur de la dernière modification.
1. Cochez la case **[!UICONTROL Ajouter les champs de gestion des autorisations d&#39;accès]** si vous souhaitez inclure les champs indiquant qui a le droit d&#39;accéder à cette ressource.

   Ces champs figurent dans les données et les métadonnées que l&#39;on peut afficher une fois la mise à jour de la base de données effectuée. Voir à ce sujet la section [Mettre à jour la structure de la base de données](../../developing/using/updating-the-database-structure.md).

1. Cochez l&#39;option **[!UICONTROL Ajouter un champ d&#39;identifiant automatique]** pour générer automatiquement un identifiant. Les entités existantes resteront vides. Pour plus d’informations, reportez-vous à la section [Générer un identifiant unique pour les profils et les ressources personnalisées](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
1. Pour modifier la façon dont le nom des éléments de ressource s’affichera dans les listes et les étapes de création, cochez la case **[!UICONTROL Personnaliser le titre des éléments de ressource]**. Sélectionnez un champ parmi ceux que vous avez créés pour cette ressource.

   ![](assets/schema_extension_18.png)

   >[!NOTE]
   >
   >Si vous ne cochez pas cette option, la clé primaire automatique (qui est automatiquement créée chaque fois qu’une entité est ajoutée à la table) sera utilisée lorsque vous dresserez la liste de toutes les entités de cette table.

Les champs de votre ressource sont maintenant définis.

## Définir les clés d&#39;identification       {#defining-identification-keys}

Chaque ressource doit posséder au moins une clé permettant de l&#39;identifier de manière unique. Vous pouvez par exemple définir une clé pour que deux produits ne puissent pas avoir le même ID dans une table d&#39;achats.

1. Si vous souhaitez obtenir une clé technique, qui sera automatiquement générée de manière incrémentale, définissez sa taille de stockage dans la section **[!UICONTROL Clé primaire automatique]**.

   ![](assets/schema_extension_6.png)

1. Utilisez le bouton **[!UICONTROL Créer un élément]** pour créer une clé.

   Les champs **[!UICONTROL Libellé]** et **[!UICONTROL Identifiant]** sont renseignés par défaut, mais vous pouvez les éditer.

   >[!NOTE]
   >
   >Utilisez 30 caractères au maximum.

1. Pour définir les éléments composant cette clé, cliquez sur **[!UICONTROL Créer un élément]** et sélectionnez les champs que vous avez créés pour cette ressource.

   ![](assets/schema_extension_7.png)

   Les clés créées s&#39;affichent dans la section **[!UICONTROL Clés personnalisées]**.

Les clés d&#39;identification de la ressource sont maintenant créées.

>[!NOTE]
>
>Pour en savoir plus sur les bonnes pratiques lors de la création de clés d’identification, consultez cette [section](../../developing/using/data-model-best-practices.md#keys).

## Définir les index       {#defining-indexes}

Un index peut référencer un ou plusieurs champs de la ressource. Les index permettent à la base de données de trier les enregistrements afin de les retrouver plus facilement. Ils optimisent les performances des requêtes SQL.

La définition des index est recommandée mais elle n&#39;est pas obligatoire.

1. Utilisez le bouton **[!UICONTROL Créer un élément]** pour créer un index.

   ![](assets/schema_extension_26.png)

1. Les champs **[!UICONTROL Libellé]** et **[!UICONTROL Identifiant]** sont renseignés par défaut, mais vous pouvez les modifier.

   >[!NOTE]
   >
   >Utilisez 30 caractères au maximum.

1. Pour définir les éléments composant cet index, sélectionnez les champs parmi ceux que vous avez créés pour cette ressource.

   ![](assets/schema_extension_27.png)

1. Cliquez sur **[!UICONTROL Confirmer]**.

Les index créés s&#39;affichent dans la liste de la section **[!UICONTROL Index]**.

>[!NOTE]
>
>Pour en savoir plus sur les bonnes pratiques lors de la création d’index, consultez cette [section](../../developing/using/data-model-best-practices.md#indexes).

## Définir les liens avec d&#39;autres ressources {#defining-links-with-other-resources}

Un lien décrit l&#39;association d&#39;une table avec d&#39;autres tables.

1. Utilisez le bouton **[!UICONTROL Créer un élément]** pour créer un lien vers une ressource cible.
1. Cliquez sur **[!UICONTROL Sélectionner une ressource cible]**.

   ![](assets/schema_extension_28.png)

1. Les ressources s’affichent par ordre alphabétique et peuvent être filtrées par nom. Leur nom technique est indiqué entre parenthèses.

   Choisissez un élément de la liste et cliquez sur **[!UICONTROL Confirmer]**.

   ![](assets/schema_extension_9.png)

1. Sélectionnez le **[!UICONTROL type de lien]** en fonction de la cardinalité. Selon le type de cardinalité choisi, le comportement en cas de suppression ou de duplication des enregistrements peut varier.

   Les différents types de liens sont les suivants :

   * **[!UICONTROL Lien simple de cardinalité 1]** : une occurrence de la table source peut avoir au plus une occurrence correspondante de la table cible.
   * **[!UICONTROL Lien de collection de cardinalité N]** : une occurrence de la table source peut avoir plusieurs occurrences correspondantes de la table cible, mais une occurrence de la table cible peut avoir au plus une occurrence correspondante de la table source.
   * **[!UICONTROL Lien simple de cardinalité 0 ou 1]** : une occurrence de la table source peut avoir au plus une occurrence correspondante de la table cible ou aucune. Ce **[!UICONTROL Type de lien]** peut entraîner des problèmes de performances.

   ![](assets/schema_extension_29.png)

1. Dans l&#39;écran **[!UICONTROL Nouveau lien]**, les champs **[!UICONTROL Libellé]** et **[!UICONTROL Identifiant]** sont renseignés par défaut, mais vous pouvez les modifier.

   >[!NOTE]
   >
   >Utilisez 30 caractères au maximum.
   >
   >Il n&#39;est pas possible de renommer un lien après sa création. Pour renommer un lien, vous devez le supprimer et le recréer.

1. La liste **[!UICONTROL Catégorie pour l&#39;audience et le ciblage]** permet d&#39;affecter ce lien à une catégorie, ce qui le rend plus visible dans l&#39;outil d&#39;édition de requête.
1. Si nécessaire, la section **[!UICONTROL Définition du lien inverse]** permet d&#39;afficher le libellé et l&#39;identifiant de la ressource dans la ressource ciblée.
1. Définissez le comportement des enregistrements référencés par le lien dans la section **[!UICONTROL Comportement en cas de suppression/duplication]**.

   Par défaut, la suppression de l&#39;enregistrement cible est possible s&#39;il n&#39;est plus référencé par le lien.

   ![](assets/schema_extension_16.png)

1. Dans la section **[!UICONTROL Définition de la jointure]**, l&#39;option par défaut **[!UICONTROL Utiliser les clés primaires pour faire la jointure]** est sélectionnée, mais vous pouvez effectuer une sélection parmi deux options :

   * **[!UICONTROL Utiliser les clés primaires pour faire la jointure]** : cette définition de jointure vous permet d&#39;utiliser la clé primaire des profils pour effectuer une réconciliation avec la clé primaire des achats.
   * **[!UICONTROL Définir des conditions de jointure spécifiques]** : cette définition de jointure vous permet de sélectionner manuellement les champs qui effectuent une jointure entre les deux ressources. Si les données ne sont pas correctement configurées, l&#39;enregistrement **Achat** ne sera pas visible.

   ![](assets/schema_extension_17.png)

Les liens créés s&#39;affichent dans la liste de la section **[!UICONTROL Liens]**.

>[!NOTE]
>
>Pour en savoir plus sur les bonnes pratiques lors de la création d’index, consultez cette [section](../../developing/using/data-model-best-practices.md#links).

**Exemple : lier une ressource créée à la ressource &#39;Profils&#39;**

Dans cet exemple, nous souhaitons lier la nouvelle ressource **Achat** à la ressource personnalisée **Profils** :

1. Créez la ressource **Achat**.
1. Pour la lier à la ressource personnalisée **Profils**, développez la section **[!UICONTROL Liens]** dans l&#39;onglet **[!UICONTROL Structure de données]** et cliquez sur **[!UICONTROL Créer un élément]**.
1. Sélectionnez la ressource cible, **[!UICONTROL Profils (profile)]**, dans le cas présent.
1. Dans cet exemple, conservez le type de lien sélectionné par défaut **[!UICONTROL Lien simple de cardinalité 1]**.

   ![](assets/custom_resource_link_to_profile_2.png)

1. Sélectionnez une définition de jointure. Dans le cas présent, conservez la définition sélectionnée par défaut **[!UICONTROL Utiliser les clés primaires pour faire la jointure]**.

   ![](assets/custom_resource_link_to_profile_3.png)

1. Au besoin, vous pouvez définir un écran de détail pour pouvoir éditer la ressource **Achat** et la lier à un profil.

   Développez la section **[!UICONTROL Configuration de l&#39;écran de détail]** et cochez la case **[!UICONTROL Définir un écran de détail]** pour configurer l&#39;écran correspondant à chaque élément de la ressource. Si vous ne cochez pas cette case, le détail des éléments de cette ressource ne sera pas accessible.

1. Cliquez sur **[!UICONTROL Créer un élément]**.
1. Sélectionnez la ressource liée et cliquez sur **[!UICONTROL Ajouter]**.

   La nouvelle ressource sera ensuite disponible dans le menu avancé en sélectionnant **[!UICONTROL Données client]** > **[!UICONTROL Achat]**.

   ![](assets/custom_resource_link_to_profile_4.png)

1. Une fois la configuration effectuée, cliquez sur **[!UICONTROL Confirmer]**.

   Vous pouvez maintenant publier la nouvelle ressource.

En ajoutant ce lien, un onglet **Achat** est ajouté à l&#39;écran de détail des profils depuis le menu **[!UICONTROL Profils &amp; audiences]** > **[!UICONTROL Profils]**. Cela est propre à la ressource **[!UICONTROL Profil]**.

![](assets/custom_resource_link_to_profile.png)

## Définition de l&#39;extension des envois {#defining-sending-logs-extension}

L&#39;extension des envois vous permet :

* d&#39;étendre les capacités des rapports dynamiques en **ajoutant des champs de profil personnalisés** ;
* d&#39;étendre les données des envois avec le **code segment et les données de profil.**

**Étendre avec le code segment**

L&#39;utilisateur peut étendre les logs avec le code segment provenant du moteur du workflow.

Le code segment doit être défini dans le workflow.

Pour activer cette extension, cochez l&#39;option **[!UICONTROL Ajouter un code segment]**.

![](assets/sendinglogsextension_1.png)

Pour plus d&#39;informations sur le code segment, voir la section [Segmentation](../../automating/using/segmentation.md).

**Étendre avec un champ de profil**

>[!NOTE]
>
>L&#39;administrateur doit avoir étendu la ressource Profil avec un champ personnalisé.

![](assets/sendinglogsextension_2.png)

Cliquez sur **[!UICONTROL Ajouter un champ]** et sélectionnez un champ personnalisé dans la ressource de profil.

Afin de générer une nouvelle sous-dimension liée à la dimension Profil, cochez l&#39;option **[!UICONTROL Ajouter ce champ en tant que nouvelle dimension dans les rapports dynamiques]**.

![](assets/sendinglogsextension_3.png)

Dans Rapports dynamiques, vous pouvez glisser et déposer la dimension de champ personnalisé dans un tableau à structure libre.

Pour plus d&#39;informations sur les rapports dynamiques, voir la [Liste des composants](../../reporting/using/list-of-components-.md).

>[!IMPORTANT]
>
>Le nombre de champs envoyés aux rapports dynamiques est limité à 20.

## Editer les propriétés d&#39;une ressource       {#editing-resource-properties}

Dans l&#39;écran de la ressource personnalisée, le volet **[!UICONTROL Résumé]** indique le statut de la ressource nouvellement créée. Vous pouvez gérer son accès et ses propriétés générales.

![](assets/schema_extension_3.png)

1. Cliquez sur le bouton **[!UICONTROL Editer les propriétés]** pour ajouter une description.

   ![](assets/schema_extension_30.png)

1. Si besoin, modifiez le libellé et l&#39;identifiant de la ressource.

   >[!NOTE]
   >
   >Utilisez 30 caractères au maximum.

1. Si vous devez restreindre l&#39;accès de cette ressource à certaines entités organisationnelles, indiquez-les ici. Seuls les utilisateurs des entités autorisées pourront utiliser cette ressource dans l&#39;application.
1. Enregistrez les modifications.

Vos modifications sont enregistrées. Pour les appliquer, vous devez republier la ressource.

## Générer un identifiant unique pour les profils et les ressources personnalisées {#generating-a-unique-id-for-profiles-and-custom-resources}

Par défaut, les profils et les ressources personnalisées ne sont pas associés à un identifiant d&#39;entreprise lors de leur création. Vous pouvez activer une option qui génère automatiquement un identifiant unique lors de la création des éléments. Cet identifiant peut être utilisé pour :

* Identifier facilement les enregistrements exportés dans un outil externe.
* Réconcilier les enregistrements lors de l&#39;import de données mises à jour traitées dans une autre application.

Il peut être activé uniquement pour les profils et les ressources personnalisées.

1. Créez une nouvelle ressource ou une extension à la ressource Profiles.
1. Dans la définition de la structure des données, cochez l&#39;option **[!UICONTROL Ajouter un champ d&#39;identifiant automatique]** dans la section **[!UICONTROL Champs]**.

   ![](assets/option_id_field.png)

   >[!NOTE]
   >
   >Seuls les nouveaux enregistrements disposeront d&#39;un identifiant ACS. Le champ **[!UICONTROL Identifiant ACS]** reste vide pour les profils ou les éléments créés avant l’activation de cette option.

1. Enregistrez et publiez la modification apportée à la ressource. Si vous souhaitez que ce mécanisme s&#39;applique aux éléments créés via l&#39;API, cochez l&#39;option permettant d&#39;étendre l&#39;API.

Le champ **[!UICONTROL Identifiant ACS]** est maintenant disponible et automatiquement renseigné lorsque de nouveaux éléments sont créés manuellement, depuis l&#39;API, ou insérés à partir d&#39;un workflow d&#39;import. Le champ d&#39;identifiant ACS est un champ UUID et il est indexé.

Lors de l&#39;export des profils ou des ressources personnalisées, vous pouvez désormais ajouter la colonne **[!UICONTROL Identifiant ACS]** si cet identifiant a été activé pour cette ressource. Vous pouvez réutiliser cet identifiant dans vos outils externes pour identifier les enregistrements.

![](assets/export_id_field.png)

Lors du nouvel import des données traitées/mises à jour dans une autre application (un système CRM, par exemple), vous pouvez facilement les réconcilier avec cet identifiant unique.

>[!NOTE]
>
>Le champ **[!UICONTROL Identifiant ACS]** n’est pas mis à jour pour les profils ou les éléments créés avant l’activation de l’option. Seuls les nouveaux enregistrements disposeront d&#39;un identifiant ACS.
>
>Ce champ est en mode Lecture seule. Vous ne pouvez pas le modifier.
