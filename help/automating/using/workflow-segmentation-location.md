---
title: « Utilisation du flux de travail : » Segmentation sur place
seo-title: « Utilisation du flux de travail : » Segmentation sur place
description: « Utilisation du flux de travail : » Segmentation sur place
seo-description: « Utilisation du flux de travail : » Segmentation sur place
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'flux de travail, utilisation, requête, segmentation, livraison '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e77c8a65834009f2f7157d9535ae8e12e59244ff

---


# Utilisation du flux de travail : Segmentation sur place {#segmentation-on-location}

Vous pouvez envoyer un email de ciblage aux clients avec des offres sur leurs magasins locaux.

1. In **[!UICONTROL Marketing Activities]**, click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau Workflow]** comme type de flux de travail et cliquez **[!UICONTROL sur Suivant]**.
1. Entrez les propriétés du flux de travail et cliquez **[!UICONTROL sur Créer]**.

## Sélection des destinataires par courriel{#selecting-recipients-contactable-via-email}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Cibler]**, glisser-déposer une **[!UICONTROL activité de requête]**![](assets/query.png).
1. Double-cliquez sur l'activité.
1. Dans **[!UICONTROL les raccourcis]**, les **[!UICONTROL profils de glisser-déposer]** et de sélectionner **[!UICONTROL le courriel]** avec l'opérateur **[!UICONTROL n'est pas vide]**.
1. Dans **[!UICONTROL Raccourcis]**, **[!UICONTROL profils glisser-déposer]** et sélectionner le champ **[!UICONTROL n'est plus contact par email]** avec la valeur **[!UICONTROL non]**.
1. Cliquez **[!UICONTROL sur Confirmer]** deux fois.

## Creating a Segmentation activity{#creating-a-segmentation-activity}

1. Glisser-déposer une **[!UICONTROL activité de Segmentation]** et double-cliquez dessus.
1. Cliquez sur le segment puis ouvrez la transition pour cibler les gens de la première ville. Ici Boston.
1. Glisser-déposer **[!UICONTROL et]** sélectionner **[!UICONTROL la ville]** avec l'opérateur **[!UICONTROL égal à]** la valeur **[!UICONTROL Boston]**.
Note : Pour atteindre toutes les personnes qui sont entrées Boston, n'ayant pas eu à l'égard de l'affaire décocher l'option sensible à l'affaire.
1. Cliquez sur **[!UICONTROL Confirmer]**.
1. Dans **[!UICONTROL Liste des segments]** sortants, cliquez **[!UICONTROL sur Ajouter un élément]** et cliquez ![](assets/edit_darkgrey-24px.png) pour créer un segment ciblant les gens dans la deuxième ville. Ici Chicago.
1. Drag-and-Drop **[!UICONTROL Emplacement]** et sélectionnez **[!UICONTROL City]** avec l'opérateur **[!UICONTROL équivalent à]** et entrer **[!UICONTROL Chicago]** en valeur.
1. Pour atteindre toutes les personnes qui sont entrées Chicago, n'en pas à propos de l'affaire décoché l'option sensible de cas.
1. Cliquez sur **[!UICONTROL Confirmer]**.

## Creating an email delivery{#creating-an-email-delivery}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Canaux]**, glisser-déposer une **[!UICONTROL livraison par courriel]** après chaque segment.
1. Cliquez sur l'activité et sélectionnez ![](assets/edit_darkgrey-24px.png) à modifier.
1. Sélectionnez **[!UICONTROL Simple Email]** et cliquez **[!UICONTROL sur Suivant]**.
1. Sélectionnez un modèle de courriel et cliquez **[!UICONTROL sur Suivant]**.
1. Entrez les propriétés de courriel et cliquez **[!UICONTROL sur Suivant]**.
1. Pour créer la mise en page de votre email, cliquez sur **[!UICONTROL le designer Email]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre email avec des offres spécifiques à chaque emplacement.

Pour plus d'informations, reportez-vous [à la conception d'un courriel](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

1. Cliquez **[!UICONTROL sur Aperçu]** pour vérifier votre disposition.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

**Rubriques connexes :**

* [activité de requête](../../automating/using/query.md)
* [activité de segmentation](../../automating/using/segmentation.md)
* [Diffusion Email ](../../automating/using/email-delivery.md)
