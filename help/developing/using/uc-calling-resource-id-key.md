---
title: Appel d'une ressource à l'aide d'une clé d'identification composite
seo-title: Appel d'une ressource à l'aide d'une clé d'identification composite
description: Appel d'une ressource à l'aide d'une clé d'identification composite
seo-description: Apprenez comment appeler une ressource en utilisant une clé d'identification composite
translation-type: tm+mt
source-git-commit: ff9861a2b8a59843cc668cec9f89b9ea76822d66

---


# Appel d'une ressource à l'aide d'une clé d'identification composite

Dans certains cas, vous devrez peut-être définir pour une ressource une clé d'identification composée de deux champs. Une fois la clé d'identification configurée, vous devez configurer une définition de filtre afin de pouvoir appeler la ressource avec cette clé d'identification, soit à partir de l'interface standard de campagne ou des API.

Dans ce cas d'utilisation, la ressource **Profil** a été étendue avec le champ " **CRM ID"** **et** "catégorie". Nous créerons une clé d'identification pour la ressource Profil, qui sera composée de ces deux champs. Nous configurerons ensuite une définition de filtre, afin que nous puissions accéder à la ressource Profil en utilisant la clé d'identification.

Les principales étapes de cette affaire sont les suivantes :

1. Configurez la clé d'identification de la ressource Profil, basée sur les deux champs.
1. Configurez la définition du filtre, pour pouvoir appeler la ressource Profil en utilisant sa clé d'identification.
1. Appelez la ressource Profil de l'interface ou des API.

Rubriques connexes :

* [Création ou extension de la ressource](../../developing/using/creating-or-extending-the-resource.md)
* [Définir les clés d'identification ](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campagne de la campagne APIS REST](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## Étape 1 : Configurer la clé d'identification

>[!NOTE]
> Les concepts globaux lors de la configuration des clés d'identification sont détaillés dans [cette section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Avant de configurer la clé d'identification, assurez-vous que la ressource a été étendue avec les champs désirés et qu'elle a été publiée. Voir à ce propos [cette section](../../developing/using/creating-or-extending-the-resource.md).

1. Allez au menu **[!UICONTROL Gestion]** / **[!UICONTROL Développement]** / **[!UICONTROL Personnalisation,]** puis ouvrez la ressource **[!UICONTROL Profil]** .

   ![](assets/uc_idkey1.png)

1. In the **[!UICONTROL Identification keys]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/uc_idkey2.png)

1. Ajoutez les deux champs personnalisés « CRM ID » et « Catégorie », puis cliquez **[!UICONTROL sur Confirmer]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Si vous souhaitez afficher les deux champs personnalisés dans l'interface du profil, configurez l'onglet **[!UICONTROL Définition]** de l'écran. Voir à ce propos [cette section](../../developing/using/configuring-the-screen-definition.md).

1. Vous pouvez maintenant configurer la définition du filtre pour pouvoir appeler la ressource en utilisant sa clé d'identification.

## Étape 2 : Configurer la définition du filtre

>[!NOTE]
> Les concepts globaux lors de la configuration des définitions de filtres sont détaillés dans [cette section](../../developing/using/configuring-filter-definition.md).

1. Dans **[!UICONTROL l'onglet Définition]** du filtre, cliquez **[!UICONTROL sur Ajouter un élément]**, puis entrez l'étiquette et l'ID de la définition du filtre.

1. Modifiez les propriétés de la définition du filtre pour configurer ses règles.

   ![](assets/uc_idkey4.png)

1. Glisser-glisser dans l'espace de travail qui contient les champs utilisés dans la clé d'identification.

   ![](assets/uc_idkey5.png)

1. Sélectionnez le premier champ utilisé dans la clé d'identification (« ID CRM »), puis activez l'option **[!UICONTROL Switch to Paramètres]** .

   ![](assets/uc_idkey6.png)

1. Dans la **[!UICONTROL section Conditions]** des filtres, gardez l'opérateur **[!UICONTROL Equal]** , puis définissez le nom du paramètre et cliquez sur le signe plus pour la créer.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Une fois que vous avez cliqué sur le bouton plus, le nom du paramètre est automatiquement généré. Notez cette information, car vous en aurez besoin pour utiliser le filtre des API.

1. Répétez les étapes ci-dessus avec tous les champs qui composent la clé d'identification (« catégorie »), puis sauvegardez vos changements.

   ![](assets/uc_idkey8.png)

1. La définition du filtre est maintenant configurée. Vous pouvez publier la ressource pour que le filtre soit disponible.

## Étape 3 : Appelez la ressource basée sur sa clé d'identification

Une fois la clé d'identification et sa définition de filtre configurée, vous pouvez les utiliser pour appeler la ressource, soit à partir de l'interface standard de campagne ou des API REST.

Pour utiliser la définition du filtre à partir de l'interface, utilisez une activité **[!UICONTROL de requête]** dans un flux de travail (voir [cette section](../../automating/using/query.md)). Le filtre est ensuite disponible dans le volet gauche.

![](assets/uc_idkey9.png)

Pour utiliser la définition du filtre à partir des API standard de campagne, utilisez la syntaxe ci-dessous :

```
GET /profileAndServicesExt/<resourceName><filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

Dans notre cas, la syntaxe pour récupérer un profil de la catégorie « printemps » et avec l'ID CRM « 123456 » serait :

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

Pour plus de détails, reportez-vous à la documentation de [la campagne des API REST](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).