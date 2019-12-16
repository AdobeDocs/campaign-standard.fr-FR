---
title: Gestion des styles
description: Découvrez comment gérer les styles d'email dans le Concepteur d'email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ddbf8ea62c4f8bba4ea53dc1daa7064704c97db2

---


# Gestion des styles {#managing-styles}


Dans le Concepteur d'email, lorsque vous sélectionnez un élément, plusieurs options spécifiques au type de contenu sélectionné s'affichent dans le volet **[!UICONTROL Paramètres]**. Vous pouvez utiliser ces options pour changer facilement le style de votre email.

## Sélectionner un élément {#selecting-an-element}

Pour sélectionner un élément dans l'interface du Concepteur d'email, vous pouvez :

* cliquer directement dans l'email,
* ou parcourir l'arborescence disponible depuis les options situées dans la **Palette** gauche.

![](assets/des_tree_structure.png)

Parcourir la structure permet d'effectuer une sélection plus précise. Vous pouvez sélectionner :

* l'ensemble du composant de structure,
* une des colonnes qui composent le composant de structure,
* ou un composant situé à l'intérieur d'une colonne.

![](assets/des_tree_structure_selection.png)

Pour sélectionner une colonne, vous pouvez également procéder comme suit :

1. Sélectionnez un composant de structure (directement dans l'email ou à l'aide de l'arborescence dans la **Palette** gauche).
1. Dans la **barre d'outils contextuelle**, cliquez sur **[!UICONTROL Sélectionner une colonne]** pour choisir la colonne désirée.

Consultez un exemple dans [cette section](#example--adjusting-vertical-alignment-and-padding).

## Ajuster les paramètres de style {#adjusting-style-settings}

1. Sélectionnez un élément dans votre email. Voir à ce propos la section [Sélectionner un élément](#selecting-an-element).
1. Ajustez les paramètres selon vos besoins. Chaque élément sélectionné offre un ensemble différent de paramètres.

   Vous pouvez insérer des arrière-plans, modifier les tailles, changer l'alignement horizontal ou vertical, gérer les couleurs, ajouter une [marge ou une marge intérieure](#selecting-an-element), etc.

   Pour cela, utilisez les options affichées dans le volet **[!UICONTROL Paramètres]** ou [ajoutez des attributs de style intégré](#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. Enregistrez votre contenu.

## A propos de la marge et de la marge intérieure {#about-padding-and-margin}

L'interface du Concepteur d'email permet d'ajuster rapidement les paramètres de marge et de marge intérieure.

**[!UICONTROL Marge intérieure]** : ce paramètre permet de gérer l'espace situé à l'intérieur de la bordure d'un élément.

![](assets/des_padding.png)

Par exemple :

* Utilisez la marge intérieure pour définir des marges à gauche et à droite d'une image.
* Utilisez la marge intérieure du haut et du bas pour ajouter davantage d'espace à un composant **[!UICONTROL Texte]** ou **[!UICONTROL Diviseur]**.
* Pour définir les bordures entre les colonnes au sein d'un élément de structure, définissez la marge intérieure de chaque colonne.

**[!UICONTROL Marge]** : ce paramètre permet de gérer l'espace entre la bordure de l'élément et l'élément suivant.

![](assets/des_margin.png)

>[!NOTE]
>
>Selon votre sélection (composant de structure, de colonne ou de contenu), le résultat sera différent. Adobe vous recommande de définir les paramètres **[!UICONTROL Marge intérieure]** et **[!UICONTROL Marge]** au niveau des colonnes.

Pour la **[!UICONTROL marge]** et la **[!UICONTROL marge intérieure]**, cliquez sur l'icône représentant un verrou pour rompre la synchronisation entre les paramètres supérieur et inférieur ou droite et gauche. Vous pouvez ainsi ajuster séparément chaque paramètre.

![](assets/des_padding_lock_icon.png)

## Alignement du style {#about-alignment}

* **Alignement du texte** : placez le curseur de votre souris sur du texte et servez-vous de la barre d'outils contextuelle pour l'aligner.

   ![](assets/des_text_alignment.png)

* L'**Alignement horizontal** peut être appliqué au texte, aux images et aux boutons, mais pas aux composants **[!UICONTROL Diviseur]** et **[!UICONTROL Social]** à l'heure actuelle.

   ![](assets/des_horizontal_alignment.png)

* Pour définir l'**alignement vertical**, sélectionnez une colonne au sein d'un composant de structure et choisissez une option dans le volet Paramètres.

   ![](assets/des_set_vertical_alignment.png)

## Définition des arrière-plans {#about-backgrounds}

Lorsqu'il s'agit de définir des fonds dans le Concepteur d'email, Adobe a les recommandations suivantes :

1. Appliquez une couleur de fond au corps de votre email si votre design le requiert.
1. Dans la plupart des cas, définissez les couleurs de fond au niveau des colonnes.
1. Evitez d'utiliser des couleurs de fond sur des composants d'image ou de texte, car elles sont difficiles à gérer.

Vous trouverez ci-dessous les paramètres de fond disponibles.

* Définissez une **[!UICONTROL Couleur de fond]** pour l'ensemble de l'email. Assurez-vous de sélectionner les paramètres du corps dans l'arborescence de navigation accessible à partir de la palette gauche.

   ![](assets/des_background_body.png)

* Définissez la même couleur de fond pour tous les composants de structure en sélectionnant **[!UICONTROL Couleur de fond de la fenêtre]**. Cette option vous permet de sélectionner un paramètre différent de la couleur de fond.

   ![](assets/des_background_viewport.png)

* Définissez une couleur de fond différente pour chaque composant de structure. Sélectionnez une structure dans l'arborescence de navigation accessibles à partir de la palette gauche afin d'appliquer une couleur de fond spécifique uniquement sur cette structure.

   ![](assets/des_background_structure.png)

   Veillez à ne pas définir de couleur de fond de la fenêtre, car celle-ci peut masquer les couleurs de fond de la structure.

* Définissez une **[!UICONTROL Image de fond]** pour le contenu d'un composant de structure.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >Certains programmes de messagerie ne prennent pas en charge les images de fond. Assurez-vous de sélectionner une couleur de fond de secours appropriée dans le cas où l'image ne pourrait s'afficher.

* Définissez une couleur de fond au niveau des colonnes.

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >Il s'agit du cas pratique le plus courant. Adobe vous recommande de définir les couleur de fond au niveau des colonnes afin de profiter d'une plus grande flexibilité lors de l'édition de l'ensemble du contenu d'email.

   Vous pouvez également définir une image de fond au niveau des colonnes, mais cette option est rarement utilisée.

### Exemple : ajustement de la marge intérieure et de l'alignement vertical {#example--adjusting-vertical-alignment-and-padding}

Vous souhaitez ajuster la marge intérieure et l'alignement vertical à l'intérieur d'un composant de structure composé de trois colonnes. Pour cela, procédez comme suit :

1. Sélectionnez le composant de structure, directement dans l'email ou à l'aide de l'arborescence dans la **Palette** gauche.
1. Dans la **barre d'outils contextuelle**, cliquez sur **[!UICONTROL Sélectionner une colonne]** et choisissez celle à éditer. Vous pouvez également la sélectionner dans l'arborescence.

   ![](assets/des_selecting_column.png)

   Les paramètres éditables pour cette colonne sont affichés dans le volet **[!UICONTROL Paramètres]** situé à droite.

1. Sous **[!UICONTROL Alignement vertical]**, sélectionnez **[!UICONTROL Monter]**.

   ![](assets/des_vertical_alignment.png)

   Le composant de contenu s'affiche au-dessus de la colonne.

1. Sous **[!UICONTROL Marge intérieure]**, définissez la marge intérieure supérieure à l'intérieur de la colonne. Cliquez sur l'icône représentant un verrou pour rompre la synchronisation avec la marge intérieure inférieure.

   Définissez la marge intérieure droite et gauche de cette colonne.

   ![](assets/des_adjusting_padding.png)

1. Procédez de façon similaire pour ajuster l'alignement et la marge intérieure des autres colonnes.

   ![](assets/des_adjusting_columns.png)

1. Enregistrez vos modifications.

## Style des liens {#about-styling-links}

Vous pouvez souligner un lien et sélectionner sa couleur et sa cible dans le Concepteur d'email.

1. Dans un composant dans lequel un lien est inséré, sélectionnez le texte du libellé du lien.

1. Dans les paramètres du composant, cochez la case **[!UICONTROL Souligner le lien]** pour souligner le texte du libellé de votre lien.

   ![](assets/stylelinks-selecttext.png)

1. Pour sélectionner le contexte de navigation dans lequel votre lien sera ouvert, sélectionnez une **[!UICONTROL Cible]**.

   ![](assets/stylelinks-target.png)

1. Pour changer la couleur de votre lien, cliquez sur **[!UICONTROL Couleur du lien]**.

   ![](assets/stylelinks-colorpicker.png)

1. Choisissez la couleur dont vous avez besoin.

   ![](assets/stylelinks-colorchanged.png)

1. Enregistrez vos modifications.

## Ajouter des attributs de style intégrés {#adding-inline-styling-attributes}

Dans l'interface du Concepteur d'email, lorsque vous sélectionnez un élément et affichez ses paramètres dans le volet latéral, vous pouvez personnaliser les attributs intégrés et leur valeur pour cet élément spécifique.

1. Sélectionnez un élément de votre contenu.
1. Sur le panneau latéral, recherchez les paramètres de **[!UICONTROL styles intégrés]**.

   ![](assets/email_designer_inlineattributes.png)

1. Modifiez les valeurs des attributs existants, ou ajoutez-en de nouveaux à l'aide du bouton **+**. Vous pouvez ajouter tout attribut et toute valeur compatible CSS.

Le style est ensuite appliqué à l'élément sélectionné. Si aucun attribut de style spécifique n'est défini pour les éléments enfants, ils héritent du style de l'élément parent.

## Passer en vue mobile {#switching-to-mobile-view}

Vous pouvez affiner le responsive design d'un email en éditant séparément toutes les options de style pour l'affichage mobile. Par exemple, vous pouvez adapter les marges et la marge intérieure, utiliser des polices de plus grande ou plus petite taille, modifier les boutons ou appliquer différentes couleurs de fond qui seront spécifiques à la version mobile de votre email.

Toutes les options de style sont disponibles dans la vue mobile. Les paramètres de style du concepteur de courrier électronique sont présentés précédemment sur cette page.

1. Créez un email et commencez à éditer le contenu. Voir à ce propos la section [Concevoir entièrement un contenu d'email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Pour accéder à la vue mobile dédiée, cliquez sur le bouton **[!UICONTROL Passer en vue Mobile]**.

   ![](assets/email_designer_mobile_view_switch.png)

   La version mobile de l'email s'affiche. Elle contient tous les composants et styles définis dans la vue de poste de travail.

1. Editez indépendamment tous les paramètres de style tels que la couleur de fond, l'alignement, la marge intérieure, la marge, la famille de polices, la couleur du texte, etc.

   ![](assets/email_designer_mobile_view.png)

1. Lorsque vous éditez un paramètre de style dans la vue mobile, les modifications ne s'appliquent qu'à l'affichage mobile.

   Par exemple, réduisez la taille d'une image, ajoutez un fond vert et modifiez la marge intérieure dans la vue mobile.

   ![](assets/email_designer_mobile_view_change.png)

1. Vous pouvez masquer un composant lorsqu'il est affiché sur un appareil mobile. Pour cela, sélectionnez **[!UICONTROL Afficher uniquement sur les postes de travail]** dans les **[!UICONTROL Options d'affichage]**.
Vous pouvez également choisir de masquer ce composant sur les postes de travail. Il ne s'affichera donc plus que sur les appareils mobiles. Pour cela, sélectionnez **[!UICONTROL Afficher uniquement sur les appareils mobiles]**.
Par exemple, cette option vous permet d'afficher une image spécifique sur les appareils mobiles et une autre image sur les postes de travail.
Vous pouvez définir cette option à partir de la vue mobile ou de poste de travail.

   ![](assets/email_designer_mobile_hide.png)

1. Cliquez de nouveau sur le bouton **[!UICONTROL Passer en vue Mobile]** pour retourner à la vue de poste de travail standard. Les changements de style que vous venez d'effectuer ne sont pas pris en compte.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >La seule exception concerne les paramètres de **[!UICONTROL style intégré]**. Toute modification des paramètres de style intégré est également appliquée à la vue de poste de travail standard.

1. Toute autre modification apportée à la structure ou au contenu de l'email, telle que des modifications de texte, le téléchargement d'une nouvelle image, l'ajout d'un nouveau composant, etc. est également appliquée à la vue standard.

   Par exemple, passez en vue mobile, modifiez du texte et remplacez une image.

   ![](assets/email_designer_mobile_view_change_content.png)

   Cliquez de nouveau sur le bouton **[!UICONTROL Passer en vue Mobile]** pour retourner à la vue de poste de travail standard. Les modifications sont prises en compte.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. La suppression d'un style dans la vue mobile vous ramène au style appliqué en mode de poste de travail.

   Par exemple, dans la vue mobile, appliquez une couleur de fond verte à un bouton.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Passez en vue de poste de travail et appliquez un fond gris au même bouton.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Passez de nouveau en vue mobile, puis désactivez le paramètre **[!UICONTROL Couleur de fond]**.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   La couleur de fond définie dans la vue de poste de travail est maintenant appliquée : elle devient grise (non vide).

   La seule exception concerne le paramètre **[!UICONTROL Couleur de bordure]**. Lorsqu'il est désactivé dans la vue mobile, aucune bordure n'est plus appliquée, même si une couleur de bordure est définie dans la vue de poste de travail.

>[!NOTE]
>
>La vue mobile n'est pas disponible dans les [fragments](../../designing/using/using-reusable-content.md#about-fragments).
