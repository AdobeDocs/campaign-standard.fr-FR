---
title: Configuration de la structure de données de la ressource
description: Découvrez comment configurer la structure de données.
page-status-flag: never-activated
uuid: 60fe80c0-9df6-4808-a432-60a1977216ea
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 4f22ee35-1d5f-4c75-95b4-3e38b85de26e
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bd83bb520a9822ffa9669076f90e6dc3397c6480

---


# Configuration de la structure de données de la ressource{#configuring-the-resource-s-data-structure}

Suite à la création d&#39;une ressource personnalisée, vous devez paramétrer la structure de données.

When editing the resource, in the **[!UICONTROL Data structure]** tab, you can add:

* [des champs ;](#adding-fields-to-a-resource)
* [des clés d&#39;identification ;](#defining-identification-keys)
* [des index ;](#defining-indexes)
* [des liens ;](#defining-links-with-other-resources)
* [des logs d&#39;envoi.](#defining-sending-logs-extension)

## Ajouter des champs à une ressource {#adding-fields-to-a-resource}

Vous pouvez ajouter de nouveaux champs à une ressource pour stocker les données qui ne font pas partie du modèle de données d&#39;usine.

1. Use the **[!UICONTROL Create element]** button to create a field.
1. Indiquez un libellé, un identifiant, un type de champ et définissez la longueur maximale autorisée pour ce champ.

   The **[!UICONTROL ID]** field is mandatory and must be unique for each field added.

   >[!NOTE]
   >
   >Utilisez 30 caractères maximum.

   ![](assets/schema_extension_4.png)

1. To modify one of the fields, check the **[!UICONTROL Edit Properties]** button.

   ![](assets/schema_extension_24.png)

1. In the **[!UICONTROL Field definition]** screen, you can define a category that will be used for the audience and targeting, or even add a description.

   ![](assets/schema_extension_5.png)

1. Sélectionnez l’ **[!UICONTROL Specify a list of authorized values]** option si vous devez définir les valeurs qui seront proposées à l’utilisateur (valeurs d’énumération).

   Cliquez ensuite sur **[!UICONTROL Create element]** et spécifiez un **[!UICONTROL Label]** et **[!UICONTROL Value]**. Ajoutez autant de valeurs que nécessaire.

1. Once you have added your fields, check the **[!UICONTROL Add audit fields]** box to include fields detailing the creation date, the user that created the resource, the date, and the author of the last modification.
1. Check the **[!UICONTROL Add access authorization management fields]** box to include the fields stating who has access rights to that particular resource.

   Ces champs figurent dans les données et les métadonnées que l&#39;on peut afficher une fois la mise à jour de la base de données effectuée. Voir à ce sujet la section [Mettre à jour la structure de la base de données](../../developing/using/updating-the-database-structure.md).

1. Cochez le **[!UICONTROL Add automatic ID]** champ pour générer automatiquement un identifiant. Les entités existantes resteront vides. Pour plus d’informations, reportez-vous à la section [Génération d’un identifiant unique pour les profils et les ressources](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)personnalisées.
1. To modify the way in which the name of the resource elements will appear in the lists and creation steps, check the **[!UICONTROL Customize the title of the resource elements]** box. Sélectionnez un champ parmi ceux que vous avez créés pour cette ressource.

   ![](assets/schema_extension_18.png)

   >[!NOTE]
   >
   >Si vous ne cochez pas cette option, la clé primaire automatique (qui est automatiquement créée chaque fois qu&#39;une entité est ajoutée à la table) sera utilisée lorsque vous répertorierez toutes les entités de cette table.

Les champs de votre ressource sont maintenant définis.

## Définir les clés d&#39;identification {#defining-identification-keys}

Chaque ressource doit posséder au moins une clé permettant de l&#39;identifier de manière unique. Vous pouvez par exemple définir une clé pour que deux produits ne puissent pas avoir le même ID dans une table d&#39;achats.

1. Specify it in the **[!UICONTROL Automatic primary key]** section the size for the storage if you would like to have a technical key automatically and incrementally generated.

   ![](assets/schema_extension_6.png)

1. Use the **[!UICONTROL Create element]** button to create a key.

   The **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default but you can edit them.

   >[!NOTE]
   >
   >Utilisez 30 caractères maximum.

1. To define the elements making up this key, click **[!UICONTROL Create element]** and select the fields that you created for this resource.

   ![](assets/schema_extension_7.png)

   Created keys are displayed in the **[!UICONTROL Custom keys]** section.

Les clés d&#39;identification de la ressource sont maintenant créées.

>[!NOTE]
>
>Pour en savoir plus sur les meilleures pratiques lors de la création de clés d’identification, consultez cette [section](../../developing/using/data-model-best-practices.md#keys).

## Définir les index {#defining-indexes}

Un index peut référencer un ou plusieurs champs de la ressource. Les index permettent à la base de données de trier les enregistrements afin de les retrouver plus facilement. Ils optimisent les performances des requêtes SQL.

La définition des index est recommandée mais elle n&#39;est pas obligatoire.

1. Use the **[!UICONTROL Create element]** button to create an index.

   ![](assets/schema_extension_26.png)

1. The **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default, but you can edit them.

   >[!NOTE]
   >
   >Utilisez 30 caractères maximum.

1. Pour définir les éléments composant cet index, sélectionnez les champs parmi ceux que vous avez créés pour cette ressource.

   ![](assets/schema_extension_27.png)

1. Clics **[!UICONTROL Confirm]**.

Les créés s&#39;affichent dans la liste de la section **[!UICONTROL Index]** Index.

>[!NOTE]
>
>Pour en savoir plus sur les meilleures pratiques lors de la création d’index, consultez cette [section](../../developing/using/data-model-best-practices.md#indexes).

## Définir les liens avec d&#39;autres ressources {#defining-links-with-other-resources}

Un lien décrit l&#39;association d&#39;une table avec d&#39;autres tables.

1. Use the **[!UICONTROL Create element]** button to create a link to a target resource.
1. Clics **[!UICONTROL Select a target resource]**.

   ![](assets/schema_extension_28.png)

1. Les ressources s&#39;affichent par ordre alphabétique et peuvent être filtrées par nom. Leur nom technique est indiqué entre parenthèses.

   Select an element from the list and click **[!UICONTROL Confirm]**.

   ![](assets/schema_extension_9.png)

1. Sélectionnez l’élément **[!UICONTROL Link type]** selon la cardinalité. Selon le type de cardinalité choisi, le comportement en cas de suppression ou de duplication des enregistrements peut varier.

   Les différents types de liens sont les suivants :

   * **[!UICONTROL 1 cardinality simple link]**: une occurrence de la table source peut comporter au plus une occurrence correspondante de la table cible.
   * **[!UICONTROL N cardinality collection link]**: une occurrence de la table source peut avoir plusieurs occurrences correspondantes de la table cible, mais une occurrence de la table cible peut avoir au plus une occurrence correspondante de la table source.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: une occurrence de la table source peut comporter au plus une occurrence correspondante de la table cible ou aucune occurrence. Note that this kind of **[!UICONTROL Link type]** can cause performance issue.
   ![](assets/schema_extension_29.png)

1. In the **[!UICONTROL New link]** screen, the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default, but you can edit them.

   >[!NOTE]
   >
   >Utilisez 30 caractères maximum.

   >[!CAUTION]
   >
   >Il n&#39;est pas possible de renommer un lien après sa création. Pour renommer un lien, vous devez le supprimer et le recréer.

1. The **[!UICONTROL Category for the audience and targeting]** list allows you to assign this link to a category making it more visible in the query editor tool.
1. If needed, the **[!UICONTROL Reverse link definition]** section allows you to display the label and ID of the resource in the targeted resource.
1. Define the behavior of the records referenced by the link in the **[!UICONTROL Behavior if deleted/duplicated]** section.

   Par défaut, la suppression de l&#39;enregistrement cible est possible s&#39;il n&#39;est plus référencé par le lien.

   ![](assets/schema_extension_16.png)

1. Dans la **[!UICONTROL Join definition]** section, l’ **[!UICONTROL Use the primary keys to make the join]** option par défaut est sélectionnée, mais vous pouvez choisir entre deux options :

   * **[!UICONTROL Use the primary key to make the join]**: Cette définition de jointure vous permet d’utiliser la clé primaire des profils pour rapprocher la clé primaire des achats.
   * **[!UICONTROL Define specific join conditions]**: Cette définition de jointure vous permet de sélectionner manuellement les champs qui rejoindront les deux ressources. Si les données ne sont pas correctement configurées, l&#39;enregistrement **Achat** ne sera pas visible.
   ![](assets/schema_extension_17.png)

The links created are displayed in the list in the **[!UICONTROL Links]** section.

>[!NOTE]
>
>Pour en savoir plus sur les meilleures pratiques lors de la création d’index, consultez cette [section](../../developing/using/data-model-best-practices.md#links).

**Exemple : lier une ressource créée à la ressource &#39;Profils&#39;**

Dans cet exemple, nous souhaitons lier la nouvelle ressource **Achat** à la ressource personnalisée **Profils** :

1. Créez la ressource **Achat**.
1. To link it with the **Profiles** custom resource, unfold the **[!UICONTROL Links]** section in the **[!UICONTROL Data structure]** tab and click **[!UICONTROL Create element]**.
1. Select the target resource, here **[!UICONTROL Profiles (profile)]**.
1. Dans cet exemple, conservez le type de **[!UICONTROL 1 cardinality simple link]** lien par défaut sélectionné.

   ![](assets/custom_resource_link_to_profile_2.png)

1. Choisissez une définition de jointure, conservez ici la valeur par défaut **[!UICONTROL Use the primary key to make the join]**.

   ![](assets/custom_resource_link_to_profile_3.png)

1. Au besoin, vous pouvez définir un écran de détail pour pouvoir éditer la ressource **Achat** et la lier à un profil.

   Dépliez la **[!UICONTROL Detail screen configuration]** section et vérifiez **[!UICONTROL Define a detail screen]** pour configurer l’écran correspondant à chaque élément de la ressource. Si vous ne cochez pas cette case, le détail des éléments de cette ressource ne sera pas accessible.

1. Clics **[!UICONTROL Create element]**.
1. Select your linked resource and click **[!UICONTROL Add]**.

   Your new resource will then be available in the advanced menu by selecting **[!UICONTROL Client data]** > **[!UICONTROL Purchase]**.

   ![](assets/custom_resource_link_to_profile_4.png)

1. Once your configuration is done, click **[!UICONTROL Confirm]**.

   Vous pouvez maintenant publier la nouvelle ressource.

By adding this link, a **Purchase** tab is added to the profiles detail screen from the **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Profiles]** menu. Please note that this is specific to the **[!UICONTROL Profile]** resource.

![](assets/custom_resource_link_to_profile.png)

## Définition de l&#39;extension des envois {#defining-sending-logs-extension}

L&#39;extension des envois vous permet :

* d&#39;étendre les capacités des rapports dynamiques en **ajoutant des champs de profil personnalisés** ;
* d&#39;étendre les données des envois avec le **code segment et les données de profil.**

**Étendre avec le code segment**

L&#39;utilisateur peut étendre les logs avec le code segment provenant du moteur du workflow.

Le code segment doit être défini dans le workflow.

Pour activer cette extension, cochez l’option **[!UICONTROL Add segment code]**.

![](assets/sendinglogsextension_1.png)

Pour plus d&#39;informations sur le code segment, voir la section [Segmentation](../../automating/using/segmentation.md).

**Étendre avec un champ de profil**

>[!NOTE]
>
>L&#39;administrateur doit avoir étendu la ressource Profil avec un champ personnalisé.

![](assets/sendinglogsextension_2.png)

Click **[!UICONTROL Add field]** and select any custom field from the profile resource.

Pour générer une nouvelle sous-dimension liée à la dimension Profil, cochez l’ **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** option.

![](assets/sendinglogsextension_3.png)

Dans Rapports dynamiques, vous pouvez glisser et déposer la dimension de champ personnalisé dans un tableau à structure libre.

Pour plus d&#39;informations sur les rapports dynamiques, voir la [Liste des composants](../../reporting/using/list-of-components-.md).

>[!CAUTION]
>
>Le nombre de champs envoyés aux rapports dynamiques est limité à 20.

## Editer les propriétés d&#39;une ressource {#editing-resource-properties}

In the custom resource screen, the **[!UICONTROL Summary]** pane indicates the status of the newly created resource. Vous pouvez gérer son accès et ses propriétés générales.

![](assets/schema_extension_3.png)

1. Click the **[!UICONTROL Edit properties]** button to add a description.

   ![](assets/schema_extension_30.png)

1. Si besoin, modifiez le libellé et l&#39;identifiant de la ressource.

   >[!NOTE]
   >
   >Utilisez 30 caractères maximum.

1. Si vous devez restreindre l&#39;accès de cette ressource à certaines entités organisationnelles, indiquez-les ici. Seuls les utilisateurs des entités autorisées pourront utiliser cette ressource dans l&#39;application.
1. Enregistrez les modifications.

Vos modifications sont enregistrées. Pour les appliquer, vous devez republier la ressource.

## Générer un identifiant unique pour les profils et les ressources personnalisées {#generating-a-unique-id-for-profiles-and-custom-resources}

Par défaut, les profils et les ressources personnalisées ne sont pas associés à un identifiant d&#39;entreprise lors de leur création. Vous pouvez activer une option qui génère automatiquement un identifiant unique lors de la création des éléments. Cet identifiant peut être utilisé pour :

* Identifier facilement les enregistrements exportés dans un outil externe.
* Réconcilier les enregistrements lors de l&#39;import de données mises à jour traitées dans une autre application.

Il peut être activé uniquement pour les profils et les ressources personnalisées.

1. Créez une nouvelle ressource ou une extension à la ressource Profiles.
1. Dans la définition de la structure de données, cochez l’ **[!UICONTROL Add automatic ID field]** option, sous la **[!UICONTROL Fields]** section.

   ![](assets/option_id_field.png)

   >[!NOTE]
   >
   >Seuls les nouveaux enregistrements disposeront d&#39;un identifiant ACS. Le **[!UICONTROL ACS ID]** champ reste vide pour les profils ou les éléments créés avant d’activer cette option.

1. Enregistrez et publiez la modification apportée à la ressource. Si vous souhaitez que ce mécanisme s&#39;applique aux éléments créés via l&#39;API, cochez l&#39;option permettant d&#39;étendre l&#39;API.

The **[!UICONTROL ACS ID]** field is now available and automatically populated when new elements are created manually, from the API, or inserted from an import workflow. Le champ d&#39;identifiant ACS est un champ UUID et il est indexé.

When exporting profiles or custom resources, you can now add the **[!UICONTROL ACS ID]** column if it has been enabled for that resource. Vous pouvez réutiliser cet identifiant dans vos outils externes pour identifier les enregistrements.

![](assets/export_id_field.png)

Lors du nouvel import des données traitées/mises à jour dans une autre application (un système CRM, par exemple), vous pouvez facilement les réconcilier avec cet identifiant unique.

>[!NOTE]
>
>The **[!UICONTROL ACS ID]** field is not updated for profiles or elements created before enabling the option. Seuls les nouveaux enregistrements disposeront d&#39;un identifiant ACS.
>
>Ce champ est en mode Lecture seule. Vous ne pouvez pas le modifier.
