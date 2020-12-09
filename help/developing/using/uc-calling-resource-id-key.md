---
solution: Campaign Standard
product: campaign
title: Appel d'une ressource à l'aide d'une clé d'identification composite
description: Découvrez comment appeler une ressource à l'aide d'une clé d'identification composite.
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '612'
ht-degree: 100%

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

1. Accédez au menu **[!UICONTROL Administration]** / **[!UICONTROL Développement]** / **[!UICONTROL Ressources personnalisées]**, puis ouvrez la ressource **[!UICONTROL Profil]**.

   ![](assets/uc_idkey1.png)

1. Dans la section **[!UICONTROL Clés d&#39;identification]**, cliquez sur le bouton **[!UICONTROL Créer un élément]**.

   ![](assets/uc_idkey2.png)

1. Ajoutez les deux champs personnalisés &quot;Identifiant CRM&quot; et &quot;Catégorie&quot;, puis cliquez sur **[!UICONTROL Confirmer]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Si vous souhaitez afficher les deux champs personnalisés dans l&#39;interface du profil, configurez l&#39;onglet **[!UICONTROL Définition des écrans]**. Voir à ce propos [cette section](../../developing/using/configuring-the-screen-definition.md).

1. Vous pouvez maintenant configurer la définition de filtre pour pouvoir appeler la ressource à l&#39;aide de sa clé d&#39;identification.

## Etape 2 : configurer la définition de filtre{#step-2-configure-the-filter-definition}

>[!NOTE]
> Les concepts globaux lors de la configuration des définitions de filtre sont présentés dans [cette section](../../developing/using/configuring-filter-definition.md).

1. Dans l&#39;onglet **[!UICONTROL Définition des filtres]**, cliquez sur **[!UICONTROL Ajouter un élément]**, puis saisissez le libellé et l&#39;identifiant de la définition de filtre.

1. Editez les propriétés de la définition de filtre pour configurer ses règles.

   ![](assets/uc_idkey4.png)

1. Placez dans l&#39;espace de travail le tableau contenant les champs utilisés dans la clé d&#39;identification.

   ![](assets/uc_idkey5.png)

1. Sélectionnez le premier champ utilisé dans la clé d&#39;identification (&quot;Identifiant CRM&quot;), puis activez l&#39;option **[!UICONTROL Définir des paramètres]**.

   ![](assets/uc_idkey6.png)

1. Dans la section **[!UICONTROL Conditions de filtrage]**, conservez l&#39;opérateur **[!UICONTROL Egal]** , puis définissez le nom du paramètre et cliquez sur le signe plus pour le créer.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Une fois que vous avez cliqué sur le bouton **+**, le nom du paramètre est généré automatiquement. Notez ces informations, car vous devrez les utiliser pour utiliser le filtre des API.

1. Répétez les étapes ci-dessus avec tous les champs qui composent la clé d&#39;identification (&quot;catégorie&quot;), puis enregistrez vos modifications.

   ![](assets/uc_idkey8.png)

1. La définition de filtre est maintenant configurée. Vous pouvez publier la ressource afin que le filtre soit disponible.

## Etape 3 : appeler la ressource en fonction de sa clé d&#39;identification{#step-3-call-the-resource-based-on-its-identification-key}

Une fois la clé d&#39;identification et sa définition de filtre configurées, vous pouvez les utiliser pour appeler la ressource à partir de l&#39;interface de Campaign standard ou des API REST.

Pour utiliser la définition de filtre depuis l&#39;interface, employez une activité **[!UICONTROL Requête]** dans un workflow (voir [cette section](../../automating/using/query.md)). Le filtre devient ensuite disponible dans le volet gauche.

![](assets/uc_idkey9.png)

Pour utiliser la définition de filtre depuis les API REST de Campaign Standard, utilisez la syntaxe suivante :

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Pour appeler un filtre personnalisé, utilisez le préfixe &quot;par&quot; suivi du nom du filtre défini lors de la configuration de la définition du filtre à l’[étape 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

Dans notre cas, la syntaxe permettant de récupérer un profil de la catégorie &quot;printemps&quot; avec l&#39;identifiant CRM &quot;123456&quot; est la suivante :

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

Pour plus d&#39;informations, consultez la [documentation des API REST Campaign Standard](../../api/using/filtering.md).