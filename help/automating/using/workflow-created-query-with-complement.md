---
title: '"Case d''utilisation du workflow: Créer des livraisons avec un complément"'
seo-title: '"Case d''utilisation du workflow: Créer des livraisons avec un complément"'
description: '"Case d''utilisation du workflow: Créer des livraisons avec un complément"'
seo-description: '"Case d''utilisation du workflow: Créer des livraisons avec un complément"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,cas d'utilisation,segmentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e56dcb4c2bbdc802c9d271d4a44d9a72b239ed

---


# Dossier d'utilisation du workflow : Création de livraisons avec un complément {#deliveries-with-complement}

Vous pouvez envoyer un e-mail aux clients: une pour les clients créés il y a moins d'un an, une pour les clients créés il y a plus d'un an.

1. In **[!UICONTROL Marketing Activities]**, click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** comme type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Entrez les propriétés du workflow et cliquez sur **[!UICONTROL Créer]**.

## Créer une activité de requête {#create-a-query-activity}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Ciblage]**, faites glisser et déposez une activité **[!UICONTROL de]** ![](assets/query.png)requête.
1. Double-cliquez sur l'activité.
1. Dans **[!UICONTROL Raccourcis]**, faites glisser-déplacer **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL e-mail]** avec l'opérateur **[!UICONTROL n'est pas vide]**.
1. Dans **[!UICONTROL Raccourcis]**, faites glisser et déplacer **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL ne plus contacter par e-mail]** avec la valeur **[!UICONTROL no]**.
1. Cliquez sur **[!UICONTROL Confirmer]**.

![](assets/wf-complement-query.png)

## Créer une activité de segmentation {#create-a-segmentation-activity}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Ciblage]**, faites glisser une activité de **[!UICONTROL segmentation]** et double-cliquez dessus.
1. Survolez le segment puis cliquez sur ![](assets/edit_darkgrey-24px.png) pour cibler les clients ajoutés cette année dans la base de données.
1. Faites glisser et déposez **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL Créé]** avec le type de filtre **[!UICONTROL Relatif]**.
1. Changez le **[!UICONTROL niveau de précision]** en **[!UICONTROL Année]** et sélectionnez **[!UICONTROL Cette année]**.
1. Cliquez deux fois sur **[!UICONTROL Confirmer]** .
1. Dans Options **** avancées, cochez **[!UICONTROL Générer un complément]** pour créer un segment ciblant les destinataires restants.
1. Cliquez sur **[!UICONTROL Confirmer]**.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Pour observer la structure de la règle, cliquez sur Mode **** avancé.

## Creating an Email delivery {#create-an-email-delivery}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Canaux]**, faites glisser et déposer une livraison de courrier électronique après chaque segment.
1. Cliquez sur l'activité et sélectionnez ![](assets/edit_darkgrey-24px.png) à modifier.
1. Sélectionnez **[!UICONTROL Envoyer un e-mail]** unique et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle de courriel et cliquez sur **[!UICONTROL Suivant]**.
1. Entrez les propriétés du courrier électronique et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre e-mail, cliquez sur **[!UICONTROL Email Designer]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre e-mail avec des offres spécifiques à chaque livraison.
1. Cliquez sur **[!UICONTROL Aperçu]** pour vérifier votre disposition.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour plus d'informations, reportez-vous à la [conception d'un e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)

**Rubriques connexes :**

* [Requête](../../automating/using/query.md)
* [Activité de segmentation](../../automating/using/segmentation.md)
* [Diffusion Email ](../../automating/using/email-delivery.md)
