---
title: Appel d'une ressource à l'aide d'une clé d'identification composite
description: Découvrez comment appeler une ressource à l'aide d'une clé d'identification composite.
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9

---


# Appel d&#39;une ressource à l&#39;aide d&#39;une clé d&#39;identification composite{#calling-a-resource-using-a-composite-identification-key}

Dans certains cas, il est possible que vous deviez définir pour une ressource une clé d&#39;identification constituée de deux champs. Une fois la clé d&#39;identification configurée, vous devez configurer une définition de filtre afin de pouvoir appeler la ressource avec cette clé d&#39;identification à partir de l&#39;interface de Campaign Standard ou des API.

Dans ce cas pratique, la ressource **Profil** a été étendue avec les champs personnalisés **&quot;Identifiant CRM&quot;** et **&quot;catégorie&quot;**. Nous allons créer une clé d&#39;identification pour la ressource Profil qui sera composée de ces deux champs. Nous configurerons ensuite une définition de filtre afin de pouvoir accéder à la ressource Profil à l&#39;aide de la clé d&#39;identification.

Les étapes principales de ce cas pratique sont les suivantes :

1. Configurer la clé d&#39;identification pour la ressource Profil en fonction des deux champs
1. Configurer la définition de filtre pour pouvoir appeler la ressource Profil à l&#39;aide de sa clé d&#39;identification
1. Appeler la ressource Profil depuis l&#39;interface ou les API

Rubriques connexes :

* [Création ou extension de la ressource](../../developing/using/creating-or-extending-the-resource.md)
* [Définir les clés d&#39;identification ](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [API REST Campaign Standard](../../api/using/get-started-apis.md)

## Etape 1 : configurer la clé d&#39;identification{#step-1-configure-the-identification-key}

>[!NOTE]
> Les concepts globaux lors de la configuration des clés d&#39;identification sont présentés dans [cette section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Avant de configurer la clé d&#39;identification, vérifiez que la ressource a été étendue avec les champs souhaités et qu&#39;elle a été publiée. Voir à ce propos [cette section](../../developing/using/creating-or-extending-the-resource.md).

1. Accédez au menu **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** , puis ouvrez la **[!UICONTROL Profile]** ressource.

   ![](assets/uc_idkey1.png)

1. Dans la **[!UICONTROL Identification keys]** section, cliquez sur le **[!UICONTROL Create element]** bouton.

   ![](assets/uc_idkey2.png)

1. Add the two custom &quot;CRM ID&quot; and &quot;Category&quot; fields, then click **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > If you want to display the two custom fields in the profile&#39;s interface, configure the **[!UICONTROL Screen definition]** tab. Voir à ce propos [cette section](../../developing/using/configuring-the-screen-definition.md).

1. Vous pouvez maintenant configurer la définition de filtre pour pouvoir appeler la ressource à l&#39;aide de sa clé d&#39;identification.

## Etape 2 : configurer la définition de filtre{#step-2-configure-the-filter-definition}

>[!NOTE]
> Les concepts globaux lors de la configuration des définitions de filtre sont présentés dans [cette section](../../developing/using/configuring-filter-definition.md).

1. Dans l’ **[!UICONTROL Filter definition]** onglet, cliquez sur **[!UICONTROL Add an element]**, puis entrez l’étiquette et l’ID de la définition de filtre.

1. Editez les propriétés de la définition de filtre pour configurer ses règles.

   ![](assets/uc_idkey4.png)

1. Placez dans l&#39;espace de travail le tableau contenant les champs utilisés dans la clé d&#39;identification.

   ![](assets/uc_idkey5.png)

1. Select the first field used in the identification key (&quot;CRM ID&quot;), then activate the **[!UICONTROL Switch to parameters]** option.

   ![](assets/uc_idkey6.png)

1. In the **[!UICONTROL Filter conditions]** section, keep the **[!UICONTROL Equal]** operator, then define the parameter&#39;s name and click the plus sign to create it.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Une fois que vous avez cliqué sur le bouton plus, le nom du paramètre est généré automatiquement. Notez ces informations, car vous devrez les utiliser pour utiliser le filtre des API.

1. Répétez les étapes ci-dessus avec tous les champs qui composent la clé d&#39;identification (&quot;catégorie&quot;), puis enregistrez vos modifications.

   ![](assets/uc_idkey8.png)

1. La définition de filtre est maintenant configurée. Vous pouvez publier la ressource afin que le filtre soit disponible.

## Etape 3 : appeler la ressource en fonction de sa clé d&#39;identification{#step-3-call-the-resource-based-on-its-identification-key}

Une fois la clé d&#39;identification et sa définition de filtre configurées, vous pouvez les utiliser pour appeler la ressource à partir de l&#39;interface de Campaign standard ou des API REST.

To use the filter definition from the interface, use a **[!UICONTROL Query]** activity in a workflow (see [this section](../../automating/using/query.md)). Le filtre devient ensuite disponible dans le volet gauche.

![](assets/uc_idkey9.png)

Pour utiliser la définition de filtre depuis les API REST de Campaign Standard, utilisez la syntaxe suivante :

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Pour appeler un filtre client, utilisez le préfixe &quot;par&quot; suivi du nom du filtre défini lors de la configuration de la définition du filtre à l&#39;[étape 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

Dans notre cas, la syntaxe permettant de récupérer un profil de la catégorie &quot;printemps&quot; avec l&#39;identifiant CRM &quot;123456&quot; est la suivante :

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

Pour plus d&#39;informations, consultez la [documentation des API REST Campaign Standard](../../api/using/filtering.md).