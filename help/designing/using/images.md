---
title: Utilisation d’images
description: Découvrez comment gérer des images dans les emails avec le Concepteur d'email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 100%

---


# Utilisation d’images {#images}

## Insérer des images{#inserting-images}

Vous pouvez insérer des images dans vos emails et landing pages.

Selon votre configuration, les types d&#39;images suivants sont disponibles :

* images locales,
* images partagées depuis Adobe Experience Cloud (voir [Utilisation de Campaign et Assets Core Service](../../integrating/using/working-with-campaign-and-assets-core-service.md)/Assets On Demand),
* images dynamiques d&#39;Adobe Target (voir [Utilisation de Campaign et Target](../../integrating/using/about-campaign-target-integration.md)).

>[!CAUTION]
>
>Si vous choisissez d&#39;ajouter une image directement en éditant la version HTML de l&#39;email, vous ne devez pas appeler les **fichiers externes dans une balise &lt;script>** de la page HTML. Ces fichiers ne seront pas importés sur le serveur Adobe Campaign.

### Insérer des images dans un email   {#inserting-images-in-an-email}

1. Ajoutez un composant de structure. Voir à ce propos la section [Éditer la structure de l’email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Dans le composant de structure, ajoutez un composant de contenu **[!UICONTROL Image]**.

   ![](assets/des_insert_images_1.png)

1. Cliquez sur **[!UICONTROL Parcourir]**. Placez une image à l&#39;aide d&#39;une opération glisser-déposer ou cliquez pour sélectionner un fichier sur votre ordinateur.

   ![](assets/des_insert_images_2.png)

1. Sélectionnez le composant de contenu que vous venez d&#39;ajouter.
1. Vérifiez les propriétés des images et modifiez-les au besoin.

   ![](assets/des_insert_images_3.png)

## Configurer les propriétés d&#39;une image{#setting-up-image-properties}

Lorsque vous sélectionnez un bloc contenant une image, les propriétés suivantes sont proposées dans la palette :

* **Activer la personnalisation** permet de personnaliser la source de l&#39;image. Voir [Personnaliser la source d&#39;une image](../../designing/using/personalization.md#personalizing-an-image-source).
* **Titre de l&#39;image** permet de définir un titre pour l&#39;image.
* **Texte alternatif** (email) ou **Légende** (landing page) permet de définir la légende associée à l&#39;image (correspond à l&#39;attribut HTML **alt**).
* Lors de l&#39;édition d&#39;un email, **Style** permet d&#39;indiquer la taille, l&#39;arrière-plan et la bordure de l&#39;image.
* Lors de l&#39;édition d&#39;une landing page, **Dimensions** permet de spécifier la taille de l&#39;image en pixels.

L&#39;éditeur permet de travailler avec **tous types d&#39;images** dont le format est compatible avec les navigateurs. Pour être compatible avec l&#39;éditeur, les **animations de type &quot;Flash&quot;** doivent être insérées dans une page HTML de la manière suivante :

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->