---
title: 'Conception d''emails à l''aide de contenu existant '
seo-title: 'Conception d''emails à l''aide de contenu existant '
description: 'Conception d''emails à l''aide de contenu existant '
seo-description: Découvrez comment concevoir des emails à l'aide d'un contenu d'email existant dans le Concepteur d'email.
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
source-git-commit: fe2f9ef93e87bfd269a3503eb6d8c88461caf694

---

# Conception à l'aide de contenu existant {#designing-using-existing-content}

## Sélectionner un contenu existant{#selecting-an-existing-content}

Un ensemble de contenus prédéfinis est fourni avec Adobe Campaign. Vous pouvez utiliser un de ces contenus ou, si le contenu du message que vous devez envoyer est préparé hors d'Adobe Campaign, vous pouvez l'importer depuis votre ordinateur ou une URL.

Lorsque vous créez un email ou une landing page, vous pouvez choisir de charger un contenu existant à partir d'une autre source.

>[!NOTE]
>
>Les images ci-après illustrent le chargement d'un contenu existant à l'aide du [Concepteur d'email](../../designing/using/overview.md).

1. Après la création de l'email ou de la landing page, ouvrez son contenu.
1. Cliquez sur l'icône Accueil pour accéder à la page d'accueil du **[!UICONTROL Concepteur d'email]**.

   ![](assets/des_loading_1.png)

1. Sélectionnez la source du contenu à charger :

   * [Modèles de contenu](../../designing/using/using-reusable-content.md#content-templates) : cliquez sur l'onglet **[!UICONTROL Modèles]**.
   * [Contenu entièrement nouveau](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) : cliquez sur le bouton **[!UICONTROL Créer]**.
   * [Contenu depuis votre ordinateur sous la forme d'un fichier ZIP ou HTML](#importing-content-from-a-file) : cliquez sur le bouton **[!UICONTROL Télécharger]**.
   * [Contenu depuis une URL existante](#importing-content-from-a-url) (uniquement pour les emails) : cliquez sur le bouton **[!UICONTROL Importer depuis l'URL]**.
   ![](assets/des_loading_2.png)

1. Chargez le contenu. Le contenu sélectionné remplace le contenu actuel.

   Une fois importé, le contenu peut être édité et personnalisé.

   >[!NOTE]
   >
   >Le [Concepteur d'email](../../designing/using/overview.md) utilise un balisage spécifique. Le contenu HTML standard téléchargé dans Campaign doit correspondre au balisage attendu pour être entièrement compatible et éditable dans le Concepteur d'email. S'il ne correspond pas, votre contenu est téléchargé en [mode de compatibilité](#compatibility-mode). Pour rendre compatibles les contenus existants, reportez-vous à [cette section](#editing-existing-contents-with-the-email-designer).

**Rubriques connexes :**

* [Créer un email](../../channels/using/creating-an-email.md)
* [Gestion des landing pages](../../channels/using/about-landing-pages.md)

## Editer des contenus existants avec le Concepteur d'email{#editing-existing-contents-with-the-email-designer}

Pour tirer pleinement parti des possibilités d'édition du [Concepteur d'email](../../designing/using/overview.md), votre code HTML importé doit contenir des balises spécifiques qui le rendent compatibles avec l'éditeur WYSIWYG.

Si tout ou partie du code HTML ne contient pas ce balisage, le contenu est alors chargé en '[mode de compatibilité](#compatibility-mode)'.

Pour rendre du contenu externe existant entièrement éditable dans le Concepteur d'email, voir la section [Concevoir un email à l'aide d'un contenu existant](../../designing/using/using-existing-content.md).

## Import en cours {#importing}

### Importer du contenu depuis un fichier {#importing-content-from-a-file}

Dans la page d'accueil du Concepteur d'email, cliquez sur le bouton **[!UICONTROL Télécharger]** pour télécharger un fichier depuis votre ordinateur, puis confirmez l'opération.

La structure du dossier compressé est libre. Toutefois, le référencement des fichiers en HTML doit être relatif et doit respecter l'arborescence du dossier compressé.

Les formats supportés lors de l'import sont les suivants :

* un fichier HTML avec feuille de style incorporée,
* un dossier compressé (.zip) contenant le fichier HTML, la feuille de style (.CSS) et les images.

>[!NOTE]
>
>Pour le contenu des emails, il est recommandé d'importer des fichiers HTML uniques avec une feuille de style incorporée.

#### Importer du contenu depuis une URL {#importing-content-from-a-url}

Avant d'importer du contenu depuis une URL, vérifiez que les exigences suivantes sont respectées :

* Le contenu doit être publiquement disponible via cette URL.
* Pour des raisons de sécurité, seules les URL commençant par **[!UICONTROL https]** sont autorisées.
* Vérifiez que toutes les ressources (images, CSS) sont définies dans des liens absolus et HTTPS. Sinon, après l'envoi de l'email, la page miroir serait affichée sans ses ressources. Voici un exemple de définition d'un lien absolu :

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>Le chargement de contenu depuis une URL n'est possible que pour le canal email.

Pour récupérer du contenu existant depuis une URL, procédez comme suit :

1. Dans la page d'accueil du Concepteur d'email, cliquez sur le bouton **[!UICONTROL Importer depuis l'URL]**.

   ![](assets/email_designer_importfromurl.png)

1. Définissez l'URL à partir de laquelle le contenu sera récupéré.
1. Cliquez sur **[!UICONTROL Confirmer]**.

**Rubrique connexe :**

Vidéo [Importer du contenu depuis une URL](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent)

### Récupérer automatiquement du contenu depuis une URL au moment de la préparation {#retrieving-content-from-a-url-automatically-at-preparation-time}

L'import de contenu à partir d'une URL lors de la préparation du message permet de récupérer le contenu HTML le plus récent à chaque préparation. Ainsi, le contenu des emails récurrents est toujours mis à jour au moment de l'envoi. Cette fonctionnalité permet également de créer un message planifié à une date spécifique, même si le contenu n'est pas encore prêt.

Pour récupérer du contenu au moment de la préparation d'une diffusion, procédez comme suit :

1. Sélectionnez l'option **[!UICONTROL Contenu importé lors de la préparation]**.

   ![](assets/email_designer_importfromurl2.png)

1. Le contenu de l'URL s'affiche en lecture seule dans l'éditeur.

   >[!CAUTION]
   >
   >A ce stade, l'affichage HTML dans l'éditeur de contenu ne doit pas être pris en compte. Il sera récupéré pendant la phase de préparation.

1. Pour prévisualiser le contenu de l'URL récupéré, ouvrez le message une fois qu'il a été créé, puis cliquez sur le bouton **[!UICONTROL Prévisualiser]**.

Il est possible de personnaliser l'URL distante à partir de laquelle le contenu sera récupéré. Pour cela, procédez comme suit :

1. Cliquez sur le libellé de l'email en haut de l'écran pour accéder à l'onglet **[!UICONTROL Propriétés]** du Concepteur d'email.
1. Recherchez le champ **[!UICONTROL URL distante]**.

   ![](assets/email_designer_importfromurl4.png)

1. Insérez le champ de personnalisation, le bloc de contenu ou le texte dynamique de votre choix.

   Le bloc de contenu **[!UICONTROL Date actuelle - YYYYMMDD]**, par exemple, permet d'insérer la date du jour.

   >[!NOTE]
   >
   >Les champs de personnalisation disponibles sont uniquement liés aux attributs de **diffusion** (date de création de l'email, statut, libellé de la campagne, etc.).

### Mode de compatibilité {#compatibility-mode}

Lorsque vous téléchargez un contenu, il doit contenir des balises spécifiques pour être entièrement compatible et éditable à l'aide de l'éditeur WYSIWYG du Concepteur d'email.

Si tout ou partie du code HTML téléchargé n'est pas conforme avec le balisage attendu, le contenu est alors chargé en "mode de compatibilité", ce qui limite les possibilités d'édition via l'interface utilisateur.

Lorsqu'un contenu est chargé en mode de compatibilité, vous pouvez toujours effectuer les modifications suivantes via l'interface utilisateur (les actions indisponibles sont masquées) :

* changer le texte ou changer une image,
* insérer des liens et des champs de personnalisation,
* éditer quelques options de style dans le bloc HTML sélectionné
* Définir du contenu conditionnel

![](assets/email_designer_compatibility.png)

D'autres modifications telles que l'ajout de nouvelles sections à votre email ou des styles sophistiqués doivent être effectuées directement dans le code source de l'email via le mode HTML.

Pour plus d'informations sur la conversion d'un email existant en email compatible avec le Concepteur d'email, voir [cette section](../../designing/using/using-existing-content.md).

**Rubrique connexe** :

* [Créer un email](../../channels/using/creating-an-email.md)
* [Vidéo d'introduction au Concepteur d'email](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=fre_fr)
* [Concevoir entièrement un contenu d'email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Convertir un contenu HTML  {#converting-an-html-content}

Si vous voulez créer un framework de fragments et de modèles modulaires qui peuvent être associés afin d'être réutilisés dans plusieurs emails, vous devriez envisager de convertir le code HTML de votre email en modèle de Concepteur d'email.

Ce cas pratique présente comment convertir rapidement le code HTML d'un email en composants du Concepteur d'email.

>[!CAUTION]
>
>Cette section est destinée aux utilisateurs avancés qui sont familiers avec le code HTML.

>[!NOTE]
>
>De la même manière que le mode de compatibilité, un composant HTML est éditable avec des options limitées : vous pouvez uniquement effectuer l'édition locale.

En dehors du Concepteur d'email, veillez à ce que le code HTML d'origine soit divisé en sections réutilisables.

Si tel n'est pas le cas, divisez les différents blocs de votre code HTML. Par exemple :

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

Une fois tous vos blocs identifiés, répétez la procédure suivante dans le Concepteur d'email pour chaque section de votre email existant :

1. Ouvrez le Concepteur d'email pour créer un contenu d'email vide.
1. Définissez les attributs au niveau du corps : les couleurs de fond, la largeur, etc. Voir à ce propos la section [Editer les styles d'un email](../../designing/using/styles.md).
1. Ajoutez un composant de structure. Voir à ce propos la section [Editer la structure de l'email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Ajoutez un composant HTML. Voir à ce propos la section [Ajouter des fragments et des composants de contenu](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copiez votre code HTML et collez-le dans ce composant.
1. Passer en vue Mobile. Voir à ce propos [cette section](../../designing/using/styles.md#switching-to-mobile-view).

   La vue en responsive design est endommagée, car il manque votre CSS.

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
   >Ne modifiez pas le CSS généré par le Concepteur d'email : `<style acrite-template-css="true">`  et `<style acrite-custom-styles="" type="text/css">`. Veillez à ajouter votre style après.

1. Revenez à la vue mobile pour vérifier que votre contenu s'affiche correctement et enregistrez vos modifications.
