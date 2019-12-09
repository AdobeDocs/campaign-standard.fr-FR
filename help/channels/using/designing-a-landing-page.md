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
>Si votre instance a été installée avant la version 19.0 d'Adobe Campaign Standard, vous avez toujours accès à l'ancien éditeur de contenu d'email. L'interface, les principes d'utilisation et la configuration sont pratiquement les mêmes que ceux décrits ci-dessous pour les landing pages. Cependant, toutes les fonctionnalités peuvent ne pas être disponibles ou gérées dans l'ancien éditeur de contenu d'email qui est obsolète à compter de la version 19.0. Pour modifier rapidement votre contenu de courrier électronique via une interface par glisser-déposer avec des fonctionnalités étendues, utilisez [Email Designer](../../designing/using/overview.md).

Cette page décrit les spécificités de l'éditeur de contenu de landing page. Pour plus d'informations sur les actions communes à une ou plusieurs activités marketing, reportez-vous aux sections suivantes du guide **Concevoir un contenu d'email** :

* [Insertion d'un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Ajout d'un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block)
* [Insertion d'un lien](../../designing/using/links.md#inserting-a-link)
* [Insertion d'images](../../designing/using/images.md)
* [Bonnes pratiques générales pour la conception de contenu](../../designing/using/overview.md#content-design-best-practices)

>[!NOTE]
>Si vous disposez d'une landing page déjà prédéfinie au format HTML, vous pouvez l'importer directement via le bouton **[!UICONTROL Changer de contenu]**.
>
>Avant d'importer une page HTML dans Adobe Campaign, assurez-vous qu'elle s'ouvre et s'affiche correctement dans les différents navigateurs. Si la page HTML contient des scripts en langage JavaScript, ils doivent s'exécuter sans erreur hors de l'éditeur. En général, évitez d’utiliser des scripts dans le contenu des messages pour vous assurer qu’ils sont correctement traités par les clients de messagerie.

## Interface de l'éditeur de contenu de landing page{#landing-page-content-editor-interface}

L'éditeur de contenu de landing page permet de définir, modifier et personnaliser facilement du contenu dans Adobe Campaign. Pour y accéder, cliquez sur le bloc **[!UICONTROL Contenu]** dans le tableau de bord des landing pages.

L’éditeur de contenu est organisé en trois sections différentes. Ces sections vous permettent d’afficher et de modifier le contenu.

![](assets/des_lp_content_8.png)

1. La **palette** située à gauche de l’écran vous permet de modifier les options générales liées à un bloc sélectionné. Les options pouvant être modifiées sont les suivantes : couleur de fond, bordure, alignement du texte, condition de visibilité, etc. See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).
1. La barre d’ **actions** contient les options générales de la page. Vous pouvez sélectionner un modèle et changer le mode d'affichage.
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
   <td> Page d’entrée et courrier électronique<br /> </td> 
   <td> Permet de sélectionner du contenu prêt à l’emploi ou d’importer votre propre contenu HTML. Reportez-vous à <a href="../../designing/using/using-existing-content.md">Chargement d’un contenu</a>existant.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Annuler</span><br /> </td> 
   <td> Tous<br /> </td> 
   <td> Annule la dernière action effectuée.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Rétablir</span><br /> </td> 
   <td> Tous<br /> </td> 
   <td> Rétablit la dernière action annulée.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Afficher les blocs</span> <br /> </td> 
   <td> Page d’entrée et courrier électronique<br /> </td> 
   <td> Permet d’afficher les zones entourant les blocs de contenu (correspond à la balise <strong>&lt;div&gt;</strong> HTML).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Afficher la source</span> <br /> </td> 
   <td> Page d’entrée et courrier électronique<br /> </td> 
   <td> Permet d’afficher le code source HTML de la page.<br /> </td> 
  </tr> 
 </tbody> 
</table>

La **barre d'outils** est un élément contextuel de l'interface de l'éditeur qui présente des fonctionnalités différentes selon la zone sélectionnée. Il contient des boutons d’action et des boutons qui vous permettent de modifier le style du texte. Les modifications effectuées s'appliquent toujours à la zone sélectionnée. Une fois que vous avez sélectionné un bloc, vous pouvez le supprimer ou le dupliquer, par exemple. Après avoir sélectionné le texte dans un bloc, vous pouvez le transformer en lien ou le mettre en gras.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Certaines fonctions de la barre d’outils vous permettent de formater le contenu HTML. Toutefois, si la page contient une feuille de style CSS, les **instructions** de la feuille de style peuvent prendre la **priorité** sur les instructions spécifiées dans la barre d’outils.

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
   <td> Permet d’ajouter un lien à une URL. Les détails de la configuration d’un lien sont présentés dans la section <a href="../../designing/using/links.md#inserting-a-link">Insertion d’un lien</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien vers une page</span> d’entrée <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d’accéder à une page d’entrée Adobe Campaign. Les détails de la configuration d’un lien sont présentés dans la section <a href="../../designing/using/links.md#inserting-a-link">Insertion d’un lien</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien d'abonnement</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d’insérer un lien d’abonnement au service. Les détails de la configuration d’un lien sont présentés dans la section <a href="../../designing/using/links.md#inserting-a-link">Insertion d’un lien</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien de désabonnement</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d’insérer un lien de désabonnement de service. Les détails de la configuration d’un lien sont présentés dans la section <a href="../../designing/using/links.md#inserting-a-link">Insertion d’un lien</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Supprimer le lien</span> <br /> </td> 
   <td> Lien (link)<br /> </td> 
   <td> Permet de supprimer le lien, ainsi que toutes les configurations qui y sont liées, après confirmation.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insérer un champ de personnalisation</span> <br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Permet d’ajouter un champ de la base de données au contenu. Reportez-vous à <a href="../../designing/using/personalization.md#inserting-a-personalization-field">Insertion d’un champ</a>de personnalisation.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insérer un bloc de contenu</span> <br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Permet d’ajouter un bloc de personnalisation au contenu. Reportez-vous à <a href="../../designing/using/personalization.md#adding-a-content-block">Ajout d’un bloc</a>de contenu.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Activer le contenu dynamique</span> <br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Permet d’insérer du contenu dynamique dans le contenu. Reportez-vous à <a href="../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page">Définition de contenu</a>dynamique.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Désactiver le contenu dynamique</span> <br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Allows you to delete dynamic content.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Agrandissement de la police</span><br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Augmente la taille du texte sélectionné (ajoute <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Réduire la police</span><br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Réduit la taille du texte sélectionné (ajoute <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Gras</span><br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Ajoute le style gras au texte sélectionné (entoure le texte de balises <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Italique</span><br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Ajoute le style italique au texte sélectionné (entoure le texte de balises <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Souligné</span><br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Souligne le texte sélectionné (entoure le texte sélectionné avec <strong>&lt;span style="text-decoration: underline;"&gt;</strong> tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Modifier la couleur</span> d’arrière-plan <br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Permet de modifier la couleur d’arrière-plan du bloc sélectionné (ajoute style="backcolor: rgba(170, 86, 255, 0.87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Changer la couleur du texte</span> <br /> </td> 
   <td> Elément Texte<br /> </td> 
   <td> Permet de modifier la couleur de tout le texte du bloc ou simplement le texte sélectionné dans le bloc (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Image</span> <br /> </td> 
   <td> Bloc contenant une image<br /> </td> 
   <td> Permet d’insérer une image à partir d’un fichier enregistré localement.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Supprimer</span><br /> </td> 
   <td> Tout bloc<br /> </td> 
   <td> Supprime le bloc et son contenu.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Dupliquer</span><br /> </td> 
   <td> Tout bloc<br /> </td> 
   <td> Duplique le bloc, y compris les styles qui y sont liés.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Gérer la structure et le style d'une landing page{#managing-landing-page-structure-and-style}

### Gérer les blocs dans l'éditeur de contenu {#managing-blocks-in-the-content-editor}

Les différents éléments du contenu HTML sont affichés dans la landing page sous forme de blocs, correspondant à la balise **&lt;div&gt;** **&lt;/div&gt;**. Sélectionnez un bloc pour interagir avec lui. Il sera alors entouré d'une boîte bleue.

![](assets/des_lp_content_1.png)

Si un bloc est sélectionné, les objets parents de l’élément HTML correspondant s’affichent dans un chemin de navigation situé au bas de la zone de modification.

Lorsque le pointeur de la souris survole l’un des éléments du chemin de navigation, l’élément concerné est mis en surbrillance. Vous pouvez donc naviguer facilement entre les différents blocs et sélectionner exactement l’élément HTML que vous souhaitez modifier.

![](assets/des_lp_content_2.png)

Utilisez les options de la palette et de la barre d’outils contextuelle pour modifier, supprimer ou dupliquer le bloc.

Pour les blocs contenant du texte, cliquez de nouveau dans le bloc pour activer le mode de modification du texte. Le cadre autour du bloc devient vert. Vous pouvez ensuite sélectionner ou saisir du texte. Utilisez les options de la palette et de la barre d’outils contextuelle pour ajouter un lien ou modifier la mise en forme du texte.

![](assets/des_lp_content_3.png)

Paramètres définis pour un élément d’un bloc (liens, champs de personnalisation, blocs de contenu, etc.) peut être modifiée à tout moment à partir de la palette.

![](assets/des_lp_content_4.png)

### Ajouter une bordure et un arrière-plan dans l'éditeur de contenu  {#adding-a-border-and-a-background-in-the-content-editor}

Vous pouvez également définir une couleur **d’** arrière-plan en sélectionnant une couleur dans le graphique. Cette couleur est appliquée au bloc sélectionné.

![](assets/des_lp_content_5.png)

Vous pouvez ajouter une **bordure** au bloc sélectionné.

![](assets/des_lp_content_6.png)

### Changer le style du texte dans l'éditeur de contenu  {#changing-the-text-style-in-the-content-editor}

Pour modifier le style du texte, vous devez cliquer à l’intérieur d’un bloc de texte.

Pour modifier l’alignement du texte, sélectionnez l’une des trois icônes suivantes dans la palette de gauche :

![](assets/des_lp_content_7.png)

* **Aligner à gauche**: aligne le texte à gauche du bloc sélectionné (ajoute style="text-align: left;").
* **Centre**: centre le texte dans le bloc sélectionné (ajoute style="text-align: center;").
* **Aligner à droite** : aligne le texte à droite du bloc sélectionné (ajoute style="text-align: right;").

Vous pouvez également utiliser la barre d’outils pour modifier les attributs de police : adaptez la taille de la police, mettez le texte en gras ou en italique, soulignez ou modifiez la couleur du texte. Consultez [cette section](../../channels/using/designing-a-landing-page.md#landing-page-content-editor-interface).

### Insérer des images dans une landing page  {#inserting-images-in-a-landing-page}

1. Dans le contenu d'une landing page, sélectionnez un bloc contenant une image.
1. Sélectionnez le bouton **[!UICONTROL Insérer]**.

   ![](assets/des_insert_images_lp_1.png)

1. Sélectionnez **[!UICONTROL Image locale]** dans la barre d'outils contextuelle.

   ![](assets/des_insert_images_lp_2.png)

1. Sélectionnez un fichier.

   ![](assets/des_insert_images_lp_3.png)

1. Modifiez les propriétés de l’image selon vos besoins.

   ![](assets/des_insert_images_lp_4.png)

## Définir le contenu dynamique dans une landing page{#defining-dynamic-content-in-a-landing-page}

Pour définir du contenu dynamique dans une landing page, sélectionnez un bloc à l'aide du fil d'Ariane ou en cliquant directement sur un élément.

![](assets/dynamic_content_lp_1.png)

Certains blocs, tels que les images, ne peuvent pas être sélectionnés directement. Dans ce cas, sélectionnez le bloc parent à l’aide du chemin de navigation. Vous pouvez ensuite modifier tous les éléments inclus dans cet élément parent, y compris les images. La condition sera appliquée à tous les éléments enfants du bloc parent.

Le chemin de navigation est présenté dans la section [Gestion des blocs](../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style) .

Les étapes suivantes pour définir le contenu dynamique dans une page d’entrée sont similaires aux étapes à suivre pour un courrier électronique. Reportez-vous à [cette section](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Si un élément variante est présenté en rouge, cela signifie qu’une expression n’a pas encore été définie.

Vous pouvez naviguer entre les différents contenus dynamiques d’un bloc. Pour cela :

1. Sélectionnez le bloc.

   Les flèches apparaissent sur les côtés droit et gauche de l’image.

1. Cliquez sur la flèche droite pour parcourir le contenu dynamique disponible.

   ![](assets/dynamic_content_lp_2.png)

   Les flèches de chaque côté s’estompent selon que vous avez atteint le dernier ou le premier contenu dynamique disponible.

   ![](assets/dynamic_content_lp_3.png)

1. Pour supprimer toutes les conditions appliquées à un bloc, sélectionnez celui-ci et cliquez de nouveau sur l'icône **[!UICONTROL Désactiver le contenu dynamique]**.
1. Sélectionnez le contenu dynamique que vous souhaitez conserver.

   ![](assets/dynamic_content_lp_5.png)

Dans la palette :

* Les contenus auxquels une expression est entrée ne sont plus décrits en rouge, mais en gris.
* Le contenu actuellement sélectionné apparaît en bleu.

![](assets/dynamic_content_lp_4.png)
