---
title: Création de diffusions avec un complémentaire
description: Ce cas pratique montre comment créer des diffusions avec un complémentaire.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '296'
ht-degree: 100%

---


# Création de diffusions avec un complémentaire {#deliveries-with-complement}

Vous pouvez envoyer un email à vos clients : un email pour les clients créés il y a moins d&#39;un an et un autre pour ceux créés il y a plus d&#39;un an.

1. Dans **[!UICONTROL Activités marketing]**, cliquez sur **[!UICONTROL Créer]** et sélectionnez **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** en tant que type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés du workflow, puis cliquez sur **[!UICONTROL Créer]**.

## Créer une activité Requête {#create-a-query-activity}

1. Dans **[!UICONTROL Activités]** > **[!UICONTROL Ciblage]**, effectuez un glisser-déposer d’une activité [Requête](../../automating/using/query.md).
1. Double-cliquez sur l&#39;activité.
1. Dans **[!UICONTROL Raccourcis]**, effectuez un glisser-déposer d&#39;un élément **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL email]** avec l&#39;opérateur **[!UICONTROL n&#39;est pas vide]**.
1. Dans **[!UICONTROL Raccourcis]**, effectuez un glisser-déposer d&#39;un élément **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL Ne plus contacter par email]** avec la valeur **[!UICONTROL non]**.
1. Cliquez sur **[!UICONTROL Confirmer]**.

![](assets/wf-complement-query.png)

## Créer une activité Segmentation {#create-a-segmentation-activity}

1. Dans **[!UICONTROL Activités]** >**[!UICONTROL Ciblage]**, effectuez un glisser-déposer d’une activité [Segmentation](../../automating/using/segmentation.md) et double-cliquez dessus.
1. Pointez sur le segment, puis cliquez sur ![](assets/edit_darkgrey-24px.png) pour cibler les clients ajoutés cette année dans la base de données.
1. Effectuez un glisser-déposer d&#39;un élément **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL Créé le]** avec le type de filtre **[!UICONTROL Relatif]**.
1. Remplacez le **[!UICONTROL Niveau de précision]** par **[!UICONTROL An]** et sélectionnez **[!UICONTROL L&#39;année en cours]**.
1. Cliquez sur **[!UICONTROL Confirmer]** à deux reprises.
1. Dans **[!UICONTROL Options avancées]**, cochez l&#39;option **[!UICONTROL Générer le complémentaire]** pour créer un segment ciblant les destinataires restants.
1. Cliquez sur **[!UICONTROL Confirmer]**.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Pour examiner la structure de la règle, cliquez sur **[!UICONTROL Mode avancé]**.

## Créer une diffusion email {#create-an-email-delivery}

1. Dans **[!UICONTROL Activités]** > **[!UICONTROL Canaux]**, effectuez un glisser-déposer d&#39;une activité [Diffusion Email](../../automating/using/email-delivery.md) après chaque segment.
1. Cliquez sur l&#39;activité et sélectionnez ![](assets/edit_darkgrey-24px.png) pour édition.
1. Sélectionnez **[!UICONTROL Email unique]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle d&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés de l&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre email, cliquez sur **[!UICONTROL Concepteur d&#39;email]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre email avec des offres spécifiques à chaque diffusion.
1. Cliquez sur **[!UICONTROL Aperçu]** pour vérifier votre mise en page.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour plus d&#39;informations, consultez la section décrivant la [conception d&#39;un email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)
