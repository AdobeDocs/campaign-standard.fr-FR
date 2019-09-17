---
title: Appel d'une ressource à l'aide d'une clé d'identification composite
seo-title: Appel d'une ressource à l'aide d'une clé d'identification composite
description: Appel d'une ressource à l'aide d'une clé d'identification composite
seo-description: Découvrez comment appeler une ressource à l'aide d'une clé d'identification composite.
translation-type: tm+mt
source-git-commit: 339dfbcc9b6443211079d116eb3e007db69c8b1a

---


# Appel d'une ressource à l'aide d'une clé d'identification composite{#calling-a-resource-using-a-composite-identification-key}

Dans certains cas, il est possible que vous deviez définir pour une ressource une clé d'identification constituée de deux champs. Une fois la clé d'identification configurée, vous devez configurer une définition de filtre afin de pouvoir appeler la ressource avec cette clé d'identification à partir de l'interface de Campaign Standard ou des API.

Dans ce cas pratique, la ressource **Profil** a été étendue avec les champs personnalisés **"Identifiant CRM"** et **"catégorie"**. Nous allons créer une clé d'identification pour la ressource Profil qui sera composée de ces deux champs. Nous configurerons ensuite une définition de filtre afin de pouvoir accéder à la ressource Profil à l'aide de la clé d'identification.

Les principales étapes de ce cas d'utilisation sont les suivantes:

1. Configurer la clé d'identification pour la ressource Profil en fonction des deux champs
1. Configurer la définition de filtre pour pouvoir appeler la ressource Profil à l'aide de sa clé d'identification
1. Appeler la ressource Profil depuis l'interface ou les API

Rubriques connexes :

* [Création ou extension de la ressource](../../developing/using/creating-or-extending-the-resource.md)
* [Définir les clés d'identification ](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [API REST standard de campagne](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## Etape 1 : configurer la clé d'identification{#step-1-configure-the-identification-key}

>[!NOTE]
> Les concepts globaux lors de la configuration des clés d'identification sont présentés dans [cette section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Avant de configurer la clé d'identification, vérifiez que la ressource a été étendue avec les champs souhaités et qu'elle a été publiée. Voir à ce propos [cette section](../../developing/using/creating-or-extending-the-resource.md).

1. Accédez au menu **[!UICONTROL Administration]** / **[!UICONTROL Développement]** / **[!UICONTROL Ressources personnalisées]**, puis ouvrez la ressource **[!UICONTROL Profil]**.

   ![](assets/uc_idkey1.png)

1. Dans la section **[!UICONTROL Clés d'identification]**, cliquez sur le bouton **[!UICONTROL Créer un élément]**.

   ![](assets/uc_idkey2.png)

1. Ajoutez les deux champs personnalisés "Identifiant CRM" et "Catégorie", puis cliquez sur **[!UICONTROL Confirmer]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Si vous souhaitez afficher les deux champs personnalisés dans l'interface du profil, configurez l'onglet **[!UICONTROL Définition des écrans]**. Voir à ce propos [cette section](../../developing/using/configuring-the-screen-definition.md).

1. Vous pouvez maintenant configurer la définition de filtre pour pouvoir appeler la ressource à l'aide de sa clé d'identification.

## Etape 2 : configurer la définition de filtre{#step-2-configure-the-filter-definition}

>[!NOTE]
> Les concepts globaux lors de la configuration des définitions de filtre sont présentés dans [cette section](../../developing/using/configuring-filter-definition.md).

1. Dans l'onglet **[!UICONTROL Définition des filtres]**, cliquez sur **[!UICONTROL Ajouter un élément]**, puis saisissez le libellé et l'identifiant de la définition de filtre.

1. Editez les propriétés de la définition de filtre pour configurer ses règles.

   ![](assets/uc_idkey4.png)

1. Placez dans l'espace de travail le tableau contenant les champs utilisés dans la clé d'identification.

   ![](assets/uc_idkey5.png)

1. Sélectionnez le premier champ utilisé dans la clé d'identification ("Identifiant CRM"), puis activez l'option **[!UICONTROL Définir des paramètres]**.

   ![](assets/uc_idkey6.png)

1. Dans la section **[!UICONTROL Conditions de filtrage]**, conservez l'opérateur **[!UICONTROL Egal]** , puis définissez le nom du paramètre et cliquez sur le signe plus pour le créer.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Une fois que vous avez cliqué sur le bouton plus, le nom du paramètre est généré automatiquement. Notez ces informations, car vous devrez les utiliser pour utiliser le filtre des API.

1. Répétez les étapes ci-dessus avec tous les champs qui composent la clé d'identification ("catégorie"), puis enregistrez vos modifications.

   ![](assets/uc_idkey8.png)

1. La définition de filtre est maintenant configurée. Vous pouvez publier la ressource afin que le filtre soit disponible.

## Etape 3 : appeler la ressource en fonction de sa clé d'identification{#step-3-call-the-resource-based-on-its-identification-key}

Une fois la clé d'identification et sa définition de filtre configurées, vous pouvez les utiliser pour appeler la ressource à partir de l'interface de Campaign standard ou des API REST.

Pour utiliser la définition de filtre depuis l'interface, employez une activité **[!UICONTROL Requête]** dans un workflow (voir [cette section](../../automating/using/query.md)). Le filtre devient ensuite disponible dans le volet gauche.

![](assets/uc_idkey9.png)

Pour utiliser la définition de filtre depuis les API REST de Campaign Standard, utilisez la syntaxe suivante :

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Pour appeler un filtre client, utilisez le préfixe "par" suivi du nom de filtre défini lors de la configuration de la définition du filtre à l' [étape 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

Dans notre cas, la syntaxe pour récupérer un profil de la catégorie "ressort" avec l'ID CRM "123456" serait la suivante:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

For more details, refer to [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).