---
solution: Campaign Standard
product: campaign
title: Configuration de la définition des filtres
description: Découvrez la fonctionnalité de filtre pour gérer un jeu de données volumineux.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: cusResource,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 100%

---


# Configuration de la définition des filtres{#configuring-filter-definition}

Dans l&#39;onglet **[!UICONTROL Définition des filtres]**, vous pouvez créer des filtres avancés de sorte que les utilisateurs puissent directement y accéder lorsqu&#39;ils élaborent des requêtes complexes, telles que la définition d&#39;une audience.

Cette étape n&#39;est pas obligatoire, car vous pourrez toujours renseigner votre ressource et accéder à ses données via les workflows, les audiences et l&#39;API REST.

![](assets/custom_resource_filter-definition.png)

Ces filtres sont utilisés dans l&#39;éditeur de requêtes sous la forme de règles pré-paramétrées. Ils permettent de limiter le nombre d&#39;étapes à réaliser afin d&#39;obtenir le paramétrage souhaité, ce qui est particulièrement intéressant dans le cas de segmentations répétitives.

Par exemple, vous pouvez créer un filtre permettant de sélectionner toutes les transactions supérieures à un montant donné au cours des trois derniers mois.

Pour cela, vous devez étendre la ressource **[!UICONTROL Profiles]** et définir une liaison de filtre vers une table des transactions (que vous aurez préalablement créées). Vous devez également définir une règle indiquant que le prix de la transaction doit être supérieur ou égal à un paramètre donné et que la date de transaction doit être comprise dans une plage correspondant aux trois derniers mois.

1. Veillez à créer et publier une table des transactions. Voir [Création ou extension de la ressource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Cette procédure utilise comme exemple une table personnalisée des transactions. Adaptez-la aux besoins de votre entreprise.

1. Avant de définir un filtre associé à la table des transactions dans la ressource **[!UICONTROL Profiles]**, assurez-vous de définir le lien vers cette table et de publier vos modifications. Voir [Définir les liens avec d&#39;autres ressources](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) et [Mettre à jour la structure de la base de données](../../developing/using/updating-the-database-structure.md).
1. Dans l&#39;onglet **[!UICONTROL Définition]** de l&#39;écran de définition de votre nouveau filtre, sélectionnez la table des transactions.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. Dans la fenêtre **[!UICONTROL Ajouter une règle - Profils/Transactions]**, placez la table des transactions dans l&#39;espace de travail. Dans la fenêtre suivante qui s&#39;affiche, sélectionnez le champ que vous souhaitez utiliser.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. Dans les **[!UICONTROL Configurations optionnelles du paramètre]** de la fenêtre **[!UICONTROL Ajouter une règle - Transactions]**, cochez la case **[!UICONTROL Définir des paramètres]**.

   Dans les **[!UICONTROL Conditions de filtrage]**, sélectionnez l&#39;opérateur **[!UICONTROL Supérieur ou égal à]**. Dans le champ **[!UICONTROL Paramètres]**, saisissez un nom et cliquez sur le signe + pour créer le nouveau paramètre.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Validez vos modifications. Il s&#39;agit du champ paramétrable que l&#39;utilisateur devra renseigner pour effectuer sa requête.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combinez cette règle à une autre règle précisant que la date doit être comprise dans une plage correspondant aux trois derniers mois.

   ![](assets/custom_resource_filter-definition_example.png)

1. Choisissez la catégorie dans laquelle figurera votre filtre.

   ![](assets/custom_resource_filter-definition_category.png)

1. Dans l&#39;onglet **[!UICONTROL Paramètres]** de l&#39;écran de définition du filtre, modifiez la description et le libellé pour indiquer clairement aux utilisateurs l&#39;objet de votre filtre. Ces informations apparaîtront dans l&#39;éditeur de requêtes.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Si vous définissez plusieurs champs paramétrables, vous pouvez modifier leur ordre d&#39;apparition dans l&#39;interface.

1. Enregistrez vos modifications et publiez les ressources. Voir à ce sujet la section [Mettre à jour la structure de la base de données](../../developing/using/updating-the-database-structure.md).

Une fois l&#39;extension de la ressource **[!UICONTROL Profiles]** publiée, les utilisateurs verront apparaître ce filtre dans l&#39;onglet des raccourcis de l&#39;interface de l&#39;[éditeur de requêtes](../../automating/using/editing-queries.md).

Lors de la création d&#39;un email, ils pourront ainsi facilement définir leur audience afin que le message soit envoyé à tous les clients ayant dépensé plus d&#39;un certain montant au cours des trois derniers mois.

![](assets/custom_resource_filter-definition_email-audience.png)

Il leur suffira de saisir le montant souhaité dans la boîte de dialogue qui s&#39;affiche au lieu d&#39;effectuer eux-mêmes le paramétrage.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

Une fois qu’un filtre est configuré, vous pouvez l’utiliser à partir des API de Campaign Standard en utilisant la syntaxe suivante :

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Pour plus d’informations à ce sujet, consultez la [documentation relative aux API Campaign Standard](../../api/using/filtering.md#custom-filters).
