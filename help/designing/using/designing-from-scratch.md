---
solution: Campaign Standard
product: campaign
title: 'Conception d’emails à partir de zéro '
description: Découvrez comment concevoir des emails à partir de zéro dans le Concepteur d’email.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 100%

---


# Conception d’emails à partir de zéro {#designing-an-email-content-from-scratch}

Découvrez comment maîtriser l’édition de contenu d’email. Avec le Concepteur d’email, vous pouvez créer des emails et des modèles avec ou sans votre propre contenu prédéfini.

Voici les principales étapes pour créer entièrement un contenu d’email à l’aide du Concepteur d’email :

1. Créez un email et ouvrez son contenu.
1. Ajoutez des composants de structure pour former l’email. Voir [Modifier la structure de l’email](#defining-the-email-structure).
1. Insérez des composants de contenu et des fragments dans les composants de structure. Voir [Ajouter des fragments et des composants de contenu](#defining-the-email-structure).
1. Ajoutez des images et éditez le texte de l’email. Voir [Insérer des images](../../designing/using/images.md#inserting-images).
1. Personnalisez votre email en ajoutant des champs de personnalisation, des liens, etc. Voir [Insertion d’un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field), [Insérer un lien](../../designing/using/links.md#inserting-a-link) et [Définir du contenu dynamique dans un email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Définissez l’objet de l’email. Voir [Personnaliser l’objet d’un email](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Prévisualisez l’email.
1. Enregistrez votre contenu et traitez votre message après avoir vérifié que vous avez défini une audience et correctement planifié l’envoi.

Vous pouvez également regarder cette [vidéo de présentation](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=fre_fr).

>[!NOTE]
>
>Pour éviter de créer entièrement un contenu d’email, vous pouvez utiliser des modèles de contenu d’usine. Voir à ce propos la section [Modèles de contenu](../../designing/using/using-reusable-content.md#content-templates).

## Définition de la structure d’un email {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="À propos des composants Structure"
>abstract="Les composants de structure définissent la disposition de votre email."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Définition des colonnes de l’email"
>abstract="Le Concepteur d’email vous permet de définir facilement la disposition de votre email en définissant la structure des colonnes."

Le Concepteur d’email permet de définir facilement la structure de votre email. En ajoutant et en déplaçant des éléments structurels à l’aide de simples actions de glisser-déposer, vous pouvez concevoir la forme de votre email en quelques secondes.

Pour éditer la structure d’un email :

1. Ouvrez un contenu existant ou créez un contenu d’email.
1. Accédez aux **[!UICONTROL Composants de structure]** en sélectionnant l’icône **+** de gauche.

   ![](assets/email_designer_structure.png)

1. Déposez les composants de structure dont vous avez besoin pour former votre email.

   ![](assets/email_designer_structure_components.png)

   Une ligne bleue matérialise la position exacte des composants de structure avant de les déposer. Vous pouvez placer vos composants au-dessus, entre ou sous n’importe quel composant, mais pas à l’intérieur.

   >[!NOTE]
   >
   >Les colonnes empilées ne sont pas compatibles avec tous les programmes de messagerie. Lorsqu’elles ne sont pas prises en charge, les colonnes ne sont pas empilées.
   >
   >Une fois qu’ils ont été placés dans l’email, vous ne pouvez pas déplacer ni supprimer vos composants, à moins qu’un composant de contenu ou un fragment ne soit déjà placé à l’intérieur.

1. Plusieurs composants de structure constitués d’une ou de plusieurs colonnes sont disponibles.

   Sélectionnez le composant **[!UICONTROL n:n colonne]** pour définir le nombre de colonnes de votre choix (entre 3 et 10). Vous pouvez aussi définir la largeur de chaque colonne en déplaçant les flèches situées au bas de celle-ci.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >La taille de chaque colonne ne peut pas être inférieure à 10 % de la largeur totale du composant de structure. Vous ne pouvez pas supprimer une colonne qui n’est pas vide.

Lorsque la structure est définie, vous pouvez ajouter des fragments de contenu et des composants à votre email.

## Utilisation d’un pré-titre {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Utilisation d’un pré-titre "
>abstract="Le pré-titre permet de configurer un texte de résumé court qui vous permettra de bénéficier d’un taux d’ouverture plus élevé pour votre email."

Un pré-titre est un texte de résumé court qui suit l’objet d’un message lorsque vous le visualisez depuis votre boîte de réception. Le pré-titre permet d’obtenir un taux d’ouverture plus élevé.

Sélectionnez la zone de modification du **[!UICONTROL pré-titre]** et complétez le contenu.

![](assets/email_designer_preheader.png)

Vous pouvez ajouter un **[!UICONTROL bloc de contenu]**, un **[!UICONTROL contenu dynamique]** ou un **[!UICONTROL champ de personnalisation]** dans le contenu du pré-titre.

>[!NOTE]
>
>Le pré-titre n’est pas compatible avec tous les programmes de messagerie. Lorsqu’il n’est pas pris en charge, le pré-titre ne s’affiche pas.


## Utilisation des composants de contenu {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="À propos des composants de contenu"
>abstract="Les composants de contenu sont des espaces réservés de contenu vides que vous pouvez modifier pour créer un email."

Les composants de contenu sont des composants bruts et vides que vous pouvez éditer une fois qu’ils ont été placés dans un email.

Vous pouvez ajouter autant de composants de contenu que vous le souhaitez dans un composant de structure. Vous pouvez également les déplacer à l’intérieur du composant de structure ou vers un autre composant de structure.

Voici la liste des composants disponibles dans le Concepteur d’email :

### **[!UICONTROL Bouton]**

Si vous avez besoin d’utiliser plusieurs boutons, plutôt que d’éditer chaque bouton à partir de zéro, vous pouvez dupliquer le composant **[!UICONTROL Bouton]** à l’aide de la barre d’outils contextuelle.

Vous pouvez aussi enregistrer des boutons dans des fragments réutilisables. Voir à ce propos [Créer un fragment de contenu](../../designing/using/using-reusable-content.md#creating-a-content-fragment) et [Enregistrer du contenu en tant que fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

Sélectionnez **[!UICONTROL Vue de la version de secours]** pour afficher l’image de remplacement dans le Concepteur d’email.

### **[!UICONTROL Texte]**

    Utilisez ce composant pour insérer du texte dans votre email. Vous pouvez ajuster la couleur, le style et la taille de votre texte dans **[!UICONTROL Paramètres des composants]**.

### **[!UICONTROL Diviseur]**

    Utilisez ce composant pour insérer une ligne de séparation dans votre email. Vous pouvez sélectionner la couleur, le style et la taille de la ligne de rupture dans **[!UICONTROL Paramètres des composants]**.

### **[!UICONTROL Html]**

Utilisez ce composant pour copier-coller les différentes parties de votre code HTML existant. Vous pouvez ainsi créer des composants HTML modulaires autonomes.

>[!NOTE]
>
>Un composant HTML autonome est éditable avec des options limitées. Si tous les styles ne sont pas intégrés, veillez à ajouter le CSS adéquat dans la     section **head** du code HTML, sinon l’email ne sera pas réactif. Utilisez le bouton **[!UICONTROL Aperçu]** afin de tester la réactivité de votre contenu (voir [Prévisualiser des messages](../../sending/using/previewing-messages.md)).

Pour rendre un contenu externe compatible avec le Concepteur d’email, Adobe recommande de créer entièrement un message et de copier le contenu de votre email existant dans des fragments et des composants.

Si un contenu ne peut pas être recréé, vous pouvez copier et coller le code HTML de l’email d’origine à l’aide du composant de contenu **[!UICONTROL Html]**. Assurez-vous de bien connaître le langage HTML avant de poursuivre.

<!-- A full example is presented below. -->

>[!NOTE]
>
>Le nouveau contenu ne sera pas une copie exacte de votre email d’origine, mais les étapes ci-après vous guideront tout au long de la création d’un message qui sera aussi ressemblant que possible.

    **Avant de copier votre contenu**
    
    1. Dans votre email d’origine, identifiez les sections réutilisables et celles qui seront uniques à chaque email que vous enverrez.
    1. Enregistrez toutes les images et les ressources que vous souhaitez utiliser.
    1. Si vous maîtrisez le langage HTML, divisez votre contenu HTML d’origine en plusieurs parties différentes.

### Vidéo {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="Paramètres vidéo"
>abstract="Utilisez ce composant pour insérer une vidéo dans votre email. Notez que les vidéos ne fonctionnent pas sur tous les clients de messagerie. Nous vous conseillons de définir une image de remplacement."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Informations supplémentaires"


Insérez le composant vidéo dans un composant de structure de votre email et saisissez le lien vidéo dans **[!UICONTROL Paramètres des composants]**.

>[!NOTE]
>
>Remarque : la vidéo n’est pas compatible avec tous les programmes de messagerie. Lorsqu’elle n’est pas prise en charge, la version de secours est affichée.

### Image

Utilisez ce composant pour insérer une image dans votre email.

Insérez le composant d’image dans un composant de structure, puis cliquez sur Parcourir pour télécharger un fichier image depuis votre ordinateur.

### **[!UICONTROL Social]**

Utilisez ce composant pour insérer des liens vers des pages de réseaux sociaux dans votre email. Vous pouvez sélectionner les liens à afficher et la taille de leur icône dans **[!UICONTROL Paramètres des composants]**.

### Carrousel {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="Paramètres du carrousel"
>abstract="Découvrez comment insérer et configurer un carrousel dans votre contenu. Notez que le carrousel ne fonctionne pas sur tous les clients de messagerie et qu’une image de remplacement s&#39;affichera s’il n’est pas pris en charge."

1. Placez le composant **[!UICONTROL Carrousel]** à l’intérieur d’un composant de structure.
1. Parcourez votre ordinateur pour sélectionner des images.

   ![](assets/des_carousel_browse.png)

1. Dans le volet **[!UICONTROL Paramètres]**, définissez le nombre de vignettes souhaitées dans le carrousel.
1. Sélectionnez une image de remplacement à partir de votre ordinateur.

   ![](assets/des_carousel_fallback.png)

Le composant carrousel n’est pas compatible avec tous les programmes de messagerie. Chargez une image de remplacement pour l’afficher lorsque le carrousel n’est pas pris en charge dans un email.

>[!NOTE]
>
>Le composant carrousel est compatible avec les plateformes de messagerie suivantes : Apple Mail 7, Apple Mail 8, Outlook 2011 pour Mac, Outlook 2016 pour Mac, Mozilla Thunderbird, iPad et iPad mini iOS, iPhone iOS, Android, AOL (Chrome, Firefox et Safari).

**Rubriques connexes** :

- [Créer un email](../../channels/using/creating-an-email.md)
- [Sélectionner une audience dans un message](../../audiences/using/selecting-an-audience-in-a-message.md)
- [Planification de l’envoi des messages](../../sending/using/about-scheduling-messages.md)
- [Prévisualiser un message](../../sending/using/previewing-messages.md)
- [Rendu des emails](../../sending/using/email-rendering.md)
