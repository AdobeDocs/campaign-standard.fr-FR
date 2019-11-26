---
title: Concevoir une landing page
description: Découvrez comment concevoir le contenu d’une page d’entrée.
page-status-flag: never-activated
uuid: de6fe190-835c-40fd-8101-a809b430b423
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: bd77d6f0-3143-4030-a91b-988a2bebc534
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Concevoir une landing page{#designing-a-landing-page}

## A propos de la conception du contenu d'une landing page {#about-content-design}

Les landing pages sont créées de la même façon que toute autre [activité marketing](../../start/using/marketing-activities.md#about-marketing-activities).

Lors de la conception d'une landing page, vous devez définir le contenu de la page, de la page de confirmation et de la page d'erreur. Utilisez le sélecteur situé sous la barre d'actions pour afficher et configurer chacune de ces pages.

Le contenu des landing pages est conçu dans l'éditeur de contenu de Campaign.

>[!NOTE]
>
>Si votre instance a été installée avant la version 19.0 d'Adobe Campaign Standard, vous avez toujours accès à l'ancien éditeur de contenu d'email. L'interface, les principes d'utilisation et la configuration sont pratiquement les mêmes que ceux décrits ci-dessous pour les landing pages. Cependant, toutes les fonctionnalités peuvent ne pas être disponibles ou gérées dans l'ancien éditeur de contenu d'email qui est obsolète à compter de la version 19.0. Pour éditer rapidement le contenu de votre email par le biais de l'interface de type glisser-déposer avec des fonctionnalités étendues, utilisez le [Concepteur d'email](../../designing/using/overview.md).

Cette page décrit les spécificités de l'éditeur de contenu de landing page. Pour plus d'informations sur les actions communes à une ou plusieurs activités marketing, reportez-vous aux sections suivantes du guide **Concevoir un contenu d'email** :

* [Insertion d'un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block).
* [Insérer un lien](../../designing/using/links.md#inserting-a-link).
* [Insérer des images](../../designing/using/images.md).
* [Bonnes pratiques générales pour la conception de contenu](../../designing/using/overview.md#content-design-best-practices).

>[!NOTE]
>Si vous disposez d'une landing page déjà prédéfinie au format HTML, vous pouvez l'importer directement via le bouton **[!UICONTROL Changer de contenu]**.
>
>Avant d'importer une page HTML dans Adobe Campaign, assurez-vous qu'elle s'ouvre et s'affiche correctement dans les différents navigateurs. Si la page HTML contient des scripts en langage JavaScript, ils doivent s'exécuter sans erreur hors de l'éditeur. Evitez en général d'utiliser des scripts dans le contenu des messages pour qu'il soit correctement traité par les clients de messagerie.

## Interface de l'éditeur de contenu de landing page{#landing-page-content-editor-interface}

L'éditeur de contenu de landing page permet de définir, modifier et personnaliser facilement du contenu dans Adobe Campaign. Pour y accéder, cliquez sur le bloc **[!UICONTROL Contenu]** dans le tableau de bord des landing pages.

L'éditeur de contenu est organisé en trois sections distinctes. Elles permettent de visualiser le contenu et de le modifier.

![](assets/des_lp_content_8.png)

1. La **palette** située à gauche de l'écran permet de modifier les paramètres du bloc sélectionné. Les options pouvant être modifiées sont les suivantes : couleur de fond, bordure, alignement du texte, condition de visibilité, etc. Voir [Insertion d'un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field).
1. La **barre d'actions** regroupe les options générales de la page. Vous pouvez sélectionner un modèle et changer le mode d'affichage.
1. La **zone d'édition** principale permet d'interagir directement avec le contenu, grâce à la barre d'outils contextuelle : insérer un lien sur une image, modifier la police de caractères, supprimer un champ, etc.

La **barre d'actions** contient différents boutons permettant d'agir sur le contenu en cours de création.

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> Icône<br /> </th> 
   <th> Nom du bouton<br /> </th> 
   <th> Canal<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Charger du contenu</span> <br /> </td> 
   <td> Landing page et email<br /> </td> 
   <td> Permet de sélectionner un contenu d'usine ou d'importer votre propre contenu HTML. Reportez-vous à <a href="../../designing/using/using-existing-content.md">Charger un contenu existant</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Annuler</span> <br /> </td> 
   <td> Tous<br /> </td> 
   <td> Annule la dernière action effectuée.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Rétablir</span> <br /> </td> 
   <td> Tous<br /> </td> 
   <td> Rétablit la dernière action que vous avez annulée.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Afficher les blocs</span> <br /> </td> 
   <td> Landing page et email<br /> </td> 
   <td> Permet d'afficher des cadres autour des blocs de contenu (correspond à la balise HTML <strong>&lt;div&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Voir la source</span> <br /> </td> 
   <td> Landing page et email<br /> </td> 
   <td> Permet d'afficher le code source HTML de la page.<br /> </td> 
  </tr> 
 </tbody> 
</table>

La **barre d'outils** est un élément contextuel de l'interface de l'éditeur qui présente des fonctionnalités différentes selon la zone sélectionnée. Elle regroupe des boutons d'action et des boutons permettant de modifier le style du texte. Les modifications effectuées s'appliquent toujours sur la zone sélectionnée. Lorsque vous sélectionnez un bloc, vous pouvez par exemple le supprimer ou le dupliquer. Lorsque vous sélectionnez du texte à l'intérieur d'un bloc, vous pouvez le transformer en lien ou le mettre en gras.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Certaines fonctionnalités de la barre d'outils permettent de mettre en forme le contenu HTML. Cependant, si la page contient une feuille de style CSS, les **instructions** provenant de la feuille de style peuvent s'avérer **prioritaires** par rapport aux instructions spécifiées avec la barre d'outils.

<table> 
 <thead> 
  <tr> 
   <th> Icône<br /> </th> 
   <th> Nom du bouton<br /> </th> 
   <th> Contexte<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/link_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien vers une URL externe</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d'ajouter un lien vers une URL. Le paramétrage d'un lien est présenté dans la section <a href="../../designing/using/links.md#inserting-a-link">Insérer un lien</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien vers une landing page</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d'accéder à une landing page Adobe Campaign. Le paramétrage d'un lien est présenté dans la section <a href="../../designing/using/links.md#inserting-a-link">Insérer un lien</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien d'abonnement</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d'insérer un lien d'abonnement à un service. Le paramétrage d'un lien est présenté dans la section <a href="../../designing/using/links.md#inserting-a-link">Insérer un lien</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien de désabonnement</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d'insérer un lien de désabonnement à un service. Le paramétrage d'un lien est présenté dans la section <a href="../../designing/using/links.md#inserting-a-link">Insérer un lien</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Supprimer le lien</span> <br /> </td> 
   <td> Lien (link)<br /> </td> 
   <td> Permet de supprimer, après confirmation, le lien ainsi que tous les paramétrages liés.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insérer un champ de personnalisation</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet d'ajouter un champ de la base de données dans le contenu. Voir <a href="../../designing/using/personalization.md#inserting-a-personalization-field">Insertion d'un champ de personnalisation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insérer un bloc de contenu</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet d'insérer un bloc de personnalisation dans le contenu. Voir <a href="../../designing/using/personalization.md#adding-a-content-block">Ajouter un bloc de contenu</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Activer le contenu dynamique</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet d'insérer un contenu dynamique dans le contenu. Voir <a href="../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page">Définir le contenu dynamique</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Désactiver le contenu dynamique</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet de supprimer un contenu dynamique.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Agrandir la police</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Augmente la taille du texte sélectionné (ajoute <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Diminuer la police</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Réduit la taille du texte sélectionné (ajoute <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Gras</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Ajoute le style gras au texte sélectionné (entoure le texte de la balise <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Italique</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Ajoute le style italique au texte sélectionné (entoure le texte de la balise <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Souligner</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Ajoute le style souligné au texte sélectionné (entoure le texte de la balise <strong>&lt;span style="text-decoration: underline;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Changer la couleur de fond</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet de changer la couleur de fond du bloc sélectionné (ajoute style="background-color: rgba(170, 86, 255, 0.87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Changer la couleur du texte</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet de changer la couleur de tout le texte dans le bloc ou seulement celle du texte sélectionné (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Image</span> <br /> </td> 
   <td> Bloc contenant une image<br /> </td> 
   <td> Permet d'insérer une image à partir d'un fichier enregistré en local.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Effacer</span> <br /> </td> 
   <td> Tout bloc<br /> </td> 
   <td> Supprime le bloc et tout son contenu.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Doublon</span> <br /> </td> 
   <td> Tout bloc<br /> </td> 
   <td> Duplique le bloc et également tous les styles associés au bloc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Gérer la structure et le style d'une landing page{#managing-landing-page-structure-and-style}

### Gérer les blocs dans l'éditeur de contenu {#managing-blocks-in-the-content-editor}

Les différents éléments du contenu HTML sont affichés dans la landing page sous forme de blocs, correspondant à la balise **&lt;div&gt;** **&lt;/div&gt;**. Pour agir sur un bloc, sélectionnez-le. Celui-ci est alors entouré d'un cadre de couleur bleue.

![](assets/des_lp_content_1.png)

Quand un bloc est sélectionné, les objets parents de l'élément HTML correspondant s'affichent dans un fil d'Ariane situé au bas de la zone d'édition.

Au survol de la souris sur un élément de ce fil d'Ariane, l'élément est mis en surbrillance. Vous pouvez ainsi facilement naviguer entre les divers blocs et sélectionner précisément l'élément HTML que vous souhaitez modifier.

![](assets/des_lp_content_2.png)

Utilisez les options disponibles dans la palette et la barre d'outils contextuelle pour modifier le bloc, le supprimer ou le dupliquer.

Pour les blocs contenant du texte, cliquez une seconde fois dans le bloc pour activer le mode d'édition du texte. Le contour du bloc devient vert. Vous pouvez alors sélectionner ou saisir du texte. Utilisez les options disponibles dans la palette et la barre d'outils contextuelle pour ajouter un lien ou modifier le formatage du texte.

![](assets/des_lp_content_3.png)

Les paramètres définis pour un élément d'un bloc (liens, champs de personnalisation, blocs de contenu, etc.) peuvent être modifiés à tout moment à partir de la palette.

![](assets/des_lp_content_4.png)

### Ajouter une bordure et un arrière-plan dans l'éditeur de contenu {#adding-a-border-and-a-background-in-the-content-editor}

Vous pouvez définir une **couleur de fond** en sélectionnant une couleur dans le nuancier. Cette couleur sera appliquée au bloc sélectionné.

![](assets/des_lp_content_5.png)

Vous pouvez ajouter une **bordure** au bloc sélectionné.

![](assets/des_lp_content_6.png)

### Changer le style du texte dans l'éditeur de contenu {#changing-the-text-style-in-the-content-editor}

Pour modifier le style du texte, vous devez vous placer à l'intérieur d'un bloc de texte.

Pour modifier l'alignement du texte, sélectionnez l'une des trois icônes suivantes dans la palette de gauche :

![](assets/des_lp_content_7.png)

* **Aligner à gauche** : aligne le texte à gauche du bloc sélectionné (ajoute style="text-align: left;").
* **Centrer** : centre le texte du bloc sélectionné (ajoute style="text-align: center;").
* **Aligner à droite** : aligne le texte à droite du bloc sélectionné (ajoute style="text-align: right;").

Vous pouvez également utiliser la barre d'outils pour modifier les attributs de la police : changer la taille de la police, mettre le texte en gras ou en italique, le souligner ou changer la couleur du texte. Consultez [cette section](../../channels/using/designing-a-landing-page.md#landing-page-content-editor-interface).

### Insérer des images dans une landing page {#inserting-images-in-a-landing-page}

1. Dans le contenu d'une landing page, sélectionnez un bloc contenant une image.
1. Sélectionnez le bouton **[!UICONTROL Insérer]**.

   ![](assets/des_insert_images_lp_1.png)

1. Sélectionnez **[!UICONTROL Image locale]** dans la barre d'outils contextuelle.

   ![](assets/des_insert_images_lp_2.png)

1. Sélectionnez un fichier.

   ![](assets/des_insert_images_lp_3.png)

1. Ajustez les propriétés de l'image selon les besoins.

   ![](assets/des_insert_images_lp_4.png)

## Définir le contenu dynamique dans une landing page{#defining-dynamic-content-in-a-landing-page}

Pour définir du contenu dynamique dans une landing page, sélectionnez un bloc à l'aide du fil d'Ariane ou en cliquant directement sur un élément.

![](assets/dynamic_content_lp_1.png)

Certains blocs, comme les images, ne peuvent pas être sélectionnés directement. Dans ce cas, sélectionnez le bloc parent à l'aide du fil d'Ariane. Vous pourrez alors modifier tous les éléments compris dans cet élément parent, y compris les images. La condition s'appliquera à tous les éléments enfants du bloc parent.

Le fil d'Ariane est présenté dans la section [Gestion des blocs](../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style).

Les étapes suivantes pour définir le contenu dynamique dans une landing page sont similaires à celles que vous devez suivre pour un email. Reportez-vous à [cette section](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Les éléments de variante encadrés en rouge sont ceux pour lesquels une expression n'a pas encore été définie.

Vous pouvez naviguer parmi les différents contenus dynamiques d'un bloc. Pour cela :

1. Sélectionnez le bloc.

   Des flèches apparaissent sur les bords gauche et droit de l'image.

1. Cliquez sur la flèche de droite pour naviguer.

   ![](assets/dynamic_content_lp_2.png)

   Le rendu des flèches est estompé lorsque vous avez navigué jusqu'au dernier contenu dynamique (ou jusqu'au premier pour la flèche de gauche).

   ![](assets/dynamic_content_lp_3.png)

1. Pour supprimer toutes les conditions appliquées à un bloc, sélectionnez celui-ci et cliquez de nouveau sur l'icône **[!UICONTROL Désactiver le contenu dynamique]**.
1. Sélectionnez le contenu dynamique que vous souhaitez conserver.

   ![](assets/dynamic_content_lp_5.png)

Dans la palette :

* Les contenus pour lesquels une expression a été renseignée ne sont plus encadrés en rouge ; ils s'affichent en gris.
* Le contenu actuellement sélectionné s'affiche en bleu.

![](assets/dynamic_content_lp_4.png)
