---
title: A propos de la conception du contenu d'une landing page
seo-title: A propos de la conception du contenu d'une landing page
description: A propos de la conception du contenu d'une landing page
seo-description: Découvrez les spécificités de l'éditeur de contenu de landing page.
page-status-flag: never-activated
uuid: 8b230690-8a63-44da-b4ed-8e9d8fd84262
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-landing-page-content
discoiquuid: 212720d2-5d57-4e7a-bb72-10512050e78c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---

# A propos de la conception du contenu d'une landing page{#about-landing-page-content-design}

Utilisez l'éditeur de contenu standard pour créer et modifier le contenu de vos landing pages dans Adobe Campaign.

Cette section décrit les spécificités de l'éditeur de contenu de landing page:

* [Interface de l'éditeur de contenu de landing page](../../channels/using/landing-page-content-editor-interface.md)
* [Gérer la structure et le style d'une landing page](../../channels/using/managing-landing-page-structure-and-style.md)
* [Modifier les propriétés des données d'un formulaire pour une landing page](../../channels/using/changing-a-landing-page-form-data-properties.md)

Pour en savoir plus sur les actions qui sont communes à une ou plusieurs activités marketing, reportez-vous aux sections suivantes :

* Pour plus d'informations sur la personnalisation du contenu d'une landing page, voir les sections [Insertion d'un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field) et [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block).
* Pour plus d'informations sur la définition du contenu dynamique dans une landing page, voir la section [Définir le contenu dynamique dans une landing page](../../channels/using/defining-dynamic-content-in-a-landing-page.md).
* Pour plus d'informations sur l'insertion de liens dans une landing page, voir la section [Insérer un lien](../../designing/using/links.md#inserting-a-link).
* Pour plus d'informations sur l'insertion d'images dans une landing page, voir la section [Insérer des images](../../designing/using/images.md).

Consultez également les [bonnes pratiques générales pour concevoir du contenu](../../designing/using/overview.md#content-design-best-practices).

>[!NOTE]
>
>Si votre instance a été installée avant la version 19.0 d’Adobe Campaign Standard, vous avez toujours accès à l'ancien éditeur de contenu d'email. L'interface, les principes d'utilisation et la configuration sont pratiquement les mêmes que ceux décrits ci-dessous pour les landing pages. Cependant, toutes les fonctionnalités peuvent ne pas être disponibles ou gérées dans l'ancien éditeur de contenu d'email qui est obsolète à compter de la version 19.0. Pour éditer rapidement le contenu de votre email par le biais de l'interface de type glisser-déposer avec des fonctionnalités étendues, utilisez le [Concepteur d'email](../../designing/using/overview.md).

## Meilleures pratiques en matière de conception de pages d'atterrissage {#landing-pages-best-practices-design}

* Lors de l'édition du **contenu d'une landing page** :

   * Avant d'importer un modèle de page HTML dans Adobe Campaign, assurez-vous que le modèle s'ouvre et s'affiche correctement dans les différents navigateurs.
   * Si la page HTML contient des scripts en langage JavaScript, ils doivent s'exécuter sans erreur hors de l'éditeur. Evitez en général d'utiliser des scripts dans le contenu des messages pour qu'il soit correctement traité par les clients de messagerie.
   * Lors de la construction d'un modèle, il est conseillé d'ajouter un attribut **'type'** aux balises . Cette information sera interprétée par l'éditeur et aidera l'utilisateur à associer un champ de la base de données au champ du formulaire lors du paramétrage de l'application Web.
   Exemple de code HTML dans le modèle :

   ```
   <input id="email" type="email" name="email"/>
   ```

   La liste officielle des attributs 'type' est disponible à l'adresse suivante : [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)