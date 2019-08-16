---
title: Editer les styles d'un email
seo-title: Editer les styles d'un email
description: Editer les styles d'un email
seo-description: Editez rapidement le style de votre contenu par le biais du Concepteur d'email grâce aux paramètres faciles d'accès.
page-status-flag: never-activated
uuid: 1fac228d-c02c-410a-a4bd-0c3b163ab5f9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 09c66cd5-2bbf-4846-ac8a-312ab5c18473
internal: n
snippet: y
translation-type: ht
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Editer les styles d'un email{#editing-email-styles}

## Editer un élément {#editing-an-element}

Dans le Concepteur d'email, lorsque vous sélectionnez un élément, plusieurs options spécifiques au type de contenu sélectionné s'affichent dans le volet **[!UICONTROL Paramètres]**. Vous pouvez utiliser ces options pour changer facilement le style de votre email.

### Sélectionner un élément  {#selecting-an-element}

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

Consultez un exemple dans [cette section](../../designing/using/editing-email-styles.md#example--adjusting-vertical-alignment-and-padding).

### Ajuster les paramètres de style  {#adjusting-style-settings}

1. Sélectionnez un élément dans votre email. Voir à ce propos la section [Sélectionner un élément](../../designing/using/editing-email-styles.md#selecting-an-element).
1. Ajustez les paramètres selon vos besoins. Chaque élément sélectionné offre un ensemble différent de paramètres.

   Vous pouvez insérer des arrière-plans, modifier les tailles, changer l'alignement horizontal ou vertical, gérer les couleurs, ajouter une [marge ou une marge intérieure](../../designing/using/editing-email-styles.md#about-padding-and-margin), etc.

   Pour cela, utilisez les options affichées dans le volet **[!UICONTROL Paramètres]** ou [ajoutez des attributs de style intégré](../../designing/using/editing-email-styles.md#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. Enregistrez votre contenu.

### A propos de la marge et de la marge intérieure  {#about-padding-and-margin}

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

### A propos de l'alignement  {#about-alignment}

* **Alignement du texte** : placez le curseur de votre souris sur du texte et servez-vous de la barre d'outils contextuelle pour l'aligner.

   ![](assets/des_text_alignment.png)

* L'**Alignement horizontal** peut être appliqué au texte, aux images et aux boutons, mais pas aux composants **[!UICONTROL Diviseur]** et **[!UICONTROL Social]** à l'heure actuelle.

   ![](assets/des_horizontal_alignment.png)

* Pour définir l'**alignement vertical**, sélectionnez une colonne au sein d'un composant de structure et choisissez une option dans le volet Paramètres.

   ![](assets/des_set_vertical_alignment.png)

### A propos des fonds  {#about-backgrounds}

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

Vous souhaitez ajuster la marge intérieure et l'alignement vertical à l'intérieur d'un composant de structure composé de trois colonnes. Pour ce faire, procédez comme suit :

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

## Ajouter des attributs de style intégrés  {#adding-inline-styling-attributes}

Dans l'interface du Concepteur d'email, lorsque vous sélectionnez un élément et affichez ses paramètres dans le volet latéral, vous pouvez personnaliser les attributs intégrés et leur valeur pour cet élément spécifique.

1. Sélectionnez un élément de votre contenu.
1. Sur le panneau latéral, recherchez les paramètres de **[!UICONTROL styles intégrés]**.

   ![](assets/email_designer_inlineattributes.png)

1. Modifiez les valeurs des attributs existants, ou ajoutez-en de nouveaux à l'aide du bouton **+**. Vous pouvez ajouter tout attribut et toute valeur compatible CSS.

Le style est ensuite appliqué à l'élément sélectionné. Si aucun attribut de style spécifique n'est défini pour les éléments enfants, ils héritent du style de l'élément parent.
