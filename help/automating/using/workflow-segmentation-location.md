---
title: Segmentation en fonction de la localisation
description: Ce cas pratique montre comment effectuer une segmentation en fonction de la localisation.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,segmentation,delivery
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: feedc2f5-63da-44a5-b8f0-15afdfd47daa
TQID: https://experienceleague.adobe.com/JWuP-ztPWX--nU-tPpPYUrwL-FsEKTJqdWX1KByF-80
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 307
ht-degree: 100%

---

# Segmentation en fonction de la localisation {#segmentation-on-location}

Vous pouvez envoyer un email de ciblage aux clients avec des offres dans leurs magasins locaux.

1. Dans **[!UICONTROL Activités marketing]**, cliquez sur **[!UICONTROL Créer]** et sélectionnez **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** en tant que type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés du workflow, puis cliquez sur **[!UICONTROL Créer]**.

## Sélectionner les destinataires pouvant être contactés par email{#selecting-recipients-contactable-via-email}

1. Dans **[!UICONTROL Activités]** > **[!UICONTROL Ciblage]**, effectuez un glisser-déposer d’une [](../../automating/using/query.md)activité Requête ![](assets/query.png).
1. Double-cliquez sur l&#39;activité.
1. Dans **[!UICONTROL Raccourcis]**, effectuez un glisser-déposer d&#39;un élément **[!UICONTROL Profils]** et sélectionnez le champ **[!UICONTROL email]** avec l&#39;opérateur **[!UICONTROL n&#39;est pas vide]**.
1. Dans **[!UICONTROL Raccourcis]**, effectuez un glisser-déposer d&#39;un élément **[!UICONTROL Profils]** et sélectionnez le champ **[!UICONTROL Ne plus contacter par email]** avec la valeur **[!UICONTROL non]**.
1. Cliquez sur **[!UICONTROL Confirmer]** à deux reprises.

![](assets/wf-complement-query.png)

## Créer une activité Segmentation{#creating-a-segmentation-activity}

1. Effectuez un glisser-déposer d&#39;une activité [Segmentation](../../automating/using/segmentation.md) et double-cliquez dessus.
1. Cliquez sur le segment, puis ouvrez la transition pour cibler les gens de la première ville. Ici, Paris.
1. Effectuez un glisser-déposer de l’élément **[!UICONTROL Localisation]** et sélectionnez **[!UICONTROL Ville]** avec l’opérateur **[!UICONTROL égal à]** et la valeur **[!UICONTROL Boston]**.
Remarque : pour accéder à toutes les personnes ayant saisi boston, indépendamment de la casse, décochez l’option Sensible à la casse.
1. Cliquez sur **[!UICONTROL Confirmer]**.
1. Dans **[!UICONTROL Liste des segments en sortie]**, cliquez sur **[!UICONTROL Ajouter un élément]** et sur ![](assets/edit_darkgrey-24px.png) pour créer un segment ciblant les personnes dans la deuxième ville. Ici, Toulouse.
1. Effectuez un glisser-déposer de l&#39;élément **[!UICONTROL Localisation]**, sélectionnez **[!UICONTROL Ville]** avec l&#39;opérateur **[!UICONTROL égal à]** et saisissez la valeur **[!UICONTROL Toulouse]**.
1. Pour atteindre toutes les personnes qui ont entré toulouse, quelle que soit la casse, décochez l&#39;option Sensible à la casse.
1. Cliquez sur **[!UICONTROL Confirmer]**.

## Créer une diffusion email{#creating-an-email-delivery}

1. Dans **[!UICONTROL Activités]** > **[!UICONTROL Canaux]**, effectuez un glisser-déposer d’une activité [Diffusion Email](../../automating/using/email-delivery.md) après chaque segment.
1. Cliquez sur l&#39;activité et sélectionnez ![](assets/edit_darkgrey-24px.png) pour édition.
1. Sélectionnez **[!UICONTROL Email simple]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle d&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés de l&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre e-mail, cliquez sur **[!UICONTROL concepteur d’e-mail]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre email avec des offres spécifiques à chaque emplacement.

   Pour plus d&#39;informations, consultez la section décrivant la [conception d&#39;un email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Cliquez sur **[!UICONTROL Aperçu]** pour vérifier votre mise en page.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

![](assets/wf-segmentation-location.png)
