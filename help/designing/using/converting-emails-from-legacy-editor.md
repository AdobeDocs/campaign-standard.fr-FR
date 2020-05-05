---
title: 'Conversion d’un courrier électronique hérité de l’éditeur de formulaires dans le concepteur de courrier électronique '
description: Découvrez comment utiliser les courriers électroniques créés dans l’Editeur hérité Courriel au concepteur de courriers électroniques.
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
source-git-commit: caab111b583534cc2e52aa9e45d9fd37c770783c

---


# Conversion du contenu des courriers électroniques de l’éditeur hérité {#converting-an-html-content}

Début de travail avec le concepteur de courrier électronique et de création de modèles et de fragments réutilisables à partir de votre code HTML de courrier électronique créé dans l’éditeur hérité.

>[!IMPORTANT]
>
>Cette section est destinée aux utilisateurs avancés qui sont familiers avec le code HTML.

Cette utilisation vous permet de créer un modèle de concepteur de courrier électronique à l’aide d’un courrier électronique HTML et de le diviser en composants HTML dans le concepteur de courrier électronique.

>[!NOTE]
>
>Tout comme le mode de compatibilité, un composant HTML est modifiable avec des options limitées : vous ne pouvez effectuer qu&#39;une édition statique.

## Préparation du contenu de votre courrier électronique

1. Sélectionnez un courrier électronique HTML.
1. Identifiez les sections pour diviser le courrier électronique HTML.
1. Découpez les différents blocs de votre code HTML.

## Créer votre structure de courriel

1. Open the **[!UICONTROL Email Designer]**  to create an empty email content.
1. Définissez les attributs au niveau du corps : les couleurs de fond, la largeur, etc. Voir à ce propos la section [Editer les styles d&#39;un email](../../designing/using/styles.md).
1. Ajouter autant de composants de structure que vous en avez. Voir à ce propos la section [Editer la structure de l&#39;email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

## Ajouter contenu HTML

1. Ajouter un composant HTML à chaque composant de structure. Voir à ce propos la section [Ajouter des fragments et des composants de contenu](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copiez-collez votre code HTML dans chaque composant.

## Gérer le style de votre courrier électronique {#manage-the-style-of-your-email}

1. Switch to **[!UICONTROL Mobile view]**. Voir à ce propos [cette section](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

1. Pour résoudre cela, passez en mode de code source, copiez votre section de style et collez-la dans une nouvelle section de style. Par exemple :

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Veillez à ajouter votre style après cette opération dans une autre balise de style personnalisée.
   >
   >Ne modifiez pas le CSS généré par le Concepteur d&#39;email :
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. Revenez à la vue mobile pour vérifier que votre contenu s&#39;affiche correctement et enregistrez vos modifications.

## Utilisation

Essayons de convertir ce courrier électronique, créé dans l’éditeur hérité, en **[!UICONTROL Email Designer]** modèle.

## Identifier la section de votre courrier électronique

Nous pouvons identifier 11 sections dans ce courriel.

![](assets/html-dce-view-mail.png)

Pour identifier l’élément qui est la section du code HTML, vous pouvez la sélectionner.

![](assets/breadcrumbs.png)

Pour afficher la version HTML du courrier électronique, cliquez sur **[!UICONTROL Show source]**.

### Créer un modèle de courrier électronique et sa structure

1. Effectuez un glisser-déposer **[!UICONTROL Structure components]** reflétant la disposition de notre courrier électronique.

1. Répétez cette opération autant de fois que nécessaire. Nous devons créer 11 composants structuraux.

   ![](assets/structure-components-migration.png)

### Insertion de composants de contenu HTML

1. Insérez un **[!UICONTROL HTML component]** dans chaque **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. Pour chaque section, cliquez sur **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. Insérez la section HTML.

1. Clics **[!UICONTROL Save]**.

Vous pouvez désormais vérifier le rendu de votre courrier électronique.

![](assets/migrated-email-result.png)

### Gestion des styles en fonction de la vue mobile

1. Insérez des éléments CSS pour vous assurer que votre adresse électronique convient à la vue mobile.

1. Passez au code source et copiez-collez votre section de style dans une nouvelle section de style.

Pour plus d’informations à ce sujet, reportez-vous à la section [Gérer le style de votre courrier électronique](#manage-the-style-of-your-email).

Votre message électronique hérité est désormais disponible dans le concepteur de messages électroniques.