---
title: '"Case d''utilisation du workflow: Segmentation sur site"'
seo-title: '"Case d''utilisation du workflow: Segmentation sur site"'
description: '"Case d''utilisation du workflow: Segmentation sur site"'
seo-description: '"Case d''utilisation du workflow: Segmentation sur site"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'workflow,case d''utilisation,requête,segmentation,livraison '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e56dcb4c2bbdc802c9d271d4a44d9a72b239ed

---


# Dossier d'utilisation du workflow : Segmentation sur l'emplacement {#segmentation-on-location}

Vous pouvez envoyer un e-mail de ciblage aux clients avec des offres sur leurs magasins locaux.

1. In **[!UICONTROL Marketing Activities]**, click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** comme type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Entrez les propriétés du workflow et cliquez sur **[!UICONTROL Créer]**.

## Sélection de destinataires pouvant être contactés par e-mail{#selecting-recipients-contactable-via-email}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Ciblage]**, faites glisser et déposez une activité **[!UICONTROL de]** ![](assets/query.png)requête.
1. Double-cliquez sur l'activité.
1. Dans **[!UICONTROL Raccourcis]**, faites glisser-déplacer **[!UICONTROL Profils]** et sélectionnez le champ **[!UICONTROL e-mail]** avec l'opérateur **[!UICONTROL n'est pas vide]**.
1. Dans **[!UICONTROL Raccourcis]**, faites glisser-déplacer **[!UICONTROL Profils]** et sélectionnez le champ **[!UICONTROL ne plus contacter par e-mail]** avec la valeur **[!UICONTROL no]**.
1. Cliquez deux fois sur **[!UICONTROL Confirmer]** .

![](assets/wf-complement-query.png)

## Creating a Segmentation activity{#creating-a-segmentation-activity}

1. Faites glisser une activité de **[!UICONTROL segmentation]** et double-cliquez dessus.
1. Cliquez sur le segment puis ouvrez la transition pour cibler les personnes dans la première ville. Ici Boston.
1. Glissez et déposez **[!UICONTROL Emplacement]** et sélectionnez **[!UICONTROL Ville]** avec l'opérateur **[!UICONTROL égal à]** et la valeur **[!UICONTROL Boston]**.
Note : Pour atteindre toutes les personnes qui sont entrées à Boston, sans tenir compte de l'affaire, décochez l'option sensible à la casse.
1. Cliquez sur **[!UICONTROL Confirmer]**.
1. Dans **[!UICONTROL Liste des segments]** sortants, cliquez sur **[!UICONTROL Ajouter un élément]** et cliquez sur ![](assets/edit_darkgrey-24px.png) pour créer un segment ciblant les personnes de la deuxième ville. Ici Chicago.
1. Faites glisser et déposer **[!UICONTROL Emplacement]** et sélectionnez **[!UICONTROL Ville]** avec l'opérateur **[!UICONTROL égale à]** et entrez **[!UICONTROL Chicago]** en valeur.
1. Pour atteindre toutes les personnes qui sont entrées chicago, sans tenir compte de l'affaire, décochez l'option sensible à la casse.
1. Cliquez sur **[!UICONTROL Confirmer]**.

## Creating an email delivery{#creating-an-email-delivery}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Chaînes]**, faites glisser et déposer une livraison **[!UICONTROL par]** courriel après chaque segment.
1. Cliquez sur l'activité et sélectionnez ![](assets/edit_darkgrey-24px.png) à modifier.
1. Sélectionnez **[!UICONTROL Simple email]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle de courriel et cliquez sur **[!UICONTROL Suivant]**.
1. Entrez les propriétés du courrier électronique et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre e-mail, cliquez sur **[!UICONTROL Email Designer]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre e-mail avec des offres spécifiques à chaque emplacement.

Pour plus d'informations, reportez-vous à la [conception d'un e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Cliquez sur **[!UICONTROL Aperçu]** pour vérifier votre disposition.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

![](assets/wf-segmentation-location.png)

**Rubriques connexes :**

* [Activité de requête](../../automating/using/query.md)
* [Activité de segmentation](../../automating/using/segmentation.md)
* [Diffusion Email ](../../automating/using/email-delivery.md)
