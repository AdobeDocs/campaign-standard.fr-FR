---
title: Interface de l'éditeur de contenu de landing page
seo-title: Interface de l'éditeur de contenu de landing page
description: Interface de l'éditeur de contenu de landing page
seo-description: Découvrez comment utiliser les différentes sections de l'éditeur, telles que la barre d'actions, pour modifier le contenu de votre landing page.
page-status-flag: never-activated
uuid: 53729a68-eed2-4c5d-bc14-02c80e897c44
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-landing-page-content
discoiquuid: 08e2bbda-e409-467f-b462-d74256dc6ebc
internal: n
snippet: y
translation-type: ht
source-git-commit: 76c3d473f6cc7e825fdabadeec2405cb5c13abd1

---


# Interface de l'éditeur de contenu de landing page{#landing-page-content-editor-interface}

L'éditeur de contenu de landing page permet de définir, modifier et personnaliser facilement du contenu dans Adobe Campaign. Pour y accéder, cliquez sur le bloc **[!UICONTROL Contenu]** dans le tableau de bord des landing pages.

L'éditeur de contenu est organisé en trois sections distinctes. Elles permettent de visualiser le contenu et de le modifier.

![](assets/des_lp_content_8.png)

1. La **palette** située à gauche de l'écran permet de modifier les paramètres du bloc sélectionné. Les options pouvant être modifiées sont les suivantes : couleur de fond, bordure, alignement du texte, condition de visibilité, etc. Voir [Insertion d'un champ de personnalisation](../../designing/using/inserting-a-personalization-field.md).
1. La **barre d'actions** regroupe les options générales de la page. Vous pouvez sélectionner un modèle et changer le mode d'affichage. Voir [Barre d'actions de l'éditeur de landing page](../../designing/using/landing-page-content-editor-interface.md#landing-page-editor-action-bar).
1. La **zone d'édition** principale permet d'interagir directement avec le contenu, grâce à la barre d'outils contextuelle : insérer un lien sur une image, modifier la police de caractères, supprimer un champ, etc. Voir [Barre d'outils de l'éditeur de landing page](../../designing/using/landing-page-content-editor-interface.md#landing-page-editor-toolbar).

## Barre d'actions de l'éditeur de landing page  {#landing-page-editor-action-bar}

La barre d'actions contient différents boutons permettant d'agir sur le contenu en cours de création.

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
   <td> Permet de sélectionner un contenu d'usine ou d'importer votre propre contenu HTML. Reportez-vous à <a href="../../designing/using/selecting-an-existing-content.md">Charger un contenu existant</a>.<br /> </td> 
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

## Barre d'outils de l'éditeur de landing page  {#landing-page-editor-toolbar}

La barre d'outils est un **élément contextuel** de l'interface de l'éditeur qui présente des fonctionnalités différentes selon la zone sélectionnée. Elle regroupe des boutons d'action et des boutons permettant de modifier le style du texte. Les modifications effectuées s'appliquent toujours sur la zone sélectionnée. Lorsque vous sélectionnez un bloc, vous pouvez par exemple le supprimer ou le dupliquer. Lorsque vous sélectionnez du texte à l'intérieur d'un bloc, vous pouvez le transformer en lien ou le mettre en gras.

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
   <td> Permet d'ajouter un lien vers une URL. Le paramétrage d'un lien est présenté dans la section <a href="../../designing/using/inserting-a-link.md">Insérer un lien</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien vers une landing page</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d'accéder à une landing page Adobe Campaign. Le paramétrage d'un lien est présenté dans la section <a href="../../designing/using/inserting-a-link.md">Insérer un lien</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien d'abonnement</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d'insérer un lien d'abonnement à un service. Le paramétrage d'un lien est présenté dans la section <a href="../../designing/using/inserting-a-link.md">Insérer un lien</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Lien de désabonnement</span> <br /> </td> 
   <td> Tout élément<br /> </td> 
   <td> Permet d'insérer un lien de désabonnement à un service. Le paramétrage d'un lien est présenté dans la section <a href="../../designing/using/inserting-a-link.md">Insérer un lien</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Supprimer le lien</span> <br /> </td> 
   <td> Lien<br /> </td> 
   <td> Permet de supprimer, après confirmation, le lien ainsi que tous les paramétrages liés.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insérer un champ de personnalisation</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet d'ajouter un champ de la base de données dans le contenu. Voir <a href="../../designing/using/inserting-a-personalization-field.md">Insertion d'un champ de personnalisation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Insérer un bloc de contenu</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet d'insérer un bloc de personnalisation dans le contenu. Voir <a href="../../designing/using/adding-a-content-block.md">Ajouter un bloc de contenu</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Activer le contenu dynamique</span> <br /> </td> 
   <td> Elément de texte<br /> </td> 
   <td> Permet d'insérer un contenu dynamique dans le contenu. Voir <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">Définir le contenu dynamique</a>.<br /> </td> 
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

