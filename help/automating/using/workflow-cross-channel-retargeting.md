---
title: '"Cas pratique de workflow : reciblage des personnes n''ayant pas ouvert l''email"'
description: '"Cas pratique de workflow : reciblage des personnes n''ayant pas ouvert l''email"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'workflow,use-case,query,wait,delivery '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Cas pratique de workflow : workflow de reciblage envoyant une diffusion aux personnes n'ayant pas ouvert l'email{#retargeting-delivery-to-non-openers}

Vous pouvez envoyer un email à des clients et ensuite un SMS à ceux qui n'ont pas ouvert l'email.

1. Dans **[!UICONTROL Activités marketing]**, cliquez sur **[!UICONTROL Créer]** et sélectionnez **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** en tant que type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés du workflow, puis cliquez sur **[!UICONTROL Créer]**.

## Créer une activité Requête{#creating-a-query-activity}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Ciblage]**, effectuez un glisser-déposer d'une activité **[!UICONTROL Requête]** ![](assets/query.png).
1. Double-cliquez sur l'activité.
1. Dans **[!UICONTROL Raccourcis]**, effectuez un glisser-déposer d'un élément **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL email]** avec l'opérateur **[!UICONTROL n'est pas vide]**.
1. Dans **[!UICONTROL Raccourcis]**, effectuez un glisser-déposer d'un élément **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL Ne plus contacter par email]** avec la valeur **[!UICONTROL non]**.
1. Cliquez sur **[!UICONTROL Confirmer]**.

![](assets/wf-complement-query.png)

## Créer une diffusion email{#creating-an-email-delivery}

1. Faites glisser et déposer une **[!UICONTROL diffusion Email]** après chaque segment.
1. Cliquez sur l'activité et sélectionnez ![](assets/edit_darkgrey-24px.png) pour édition.
1. Sélectionnez **[!UICONTROL Email simple]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez **[!UICONTROL Ajouter une transition sortante sans la population]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle d'email et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés de l'email et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre email, cliquez sur **[!UICONTROL Utiliser le Concepteur d'email]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre email avec des offres spécifiques à chaque emplacement. Pour plus d'informations, consultez la section décrivant la [conception d'un email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Cliquez sur **[!UICONTROL Aperçu]** pour vérifier votre mise en page.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Ciblage des personnes n'ayant pas ouvert l'email dans une activité Requête{#targeting-non-openers-in-a-query-activity}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Exécution]**, effectuez un glisser-déposer d'une activité **[!UICONTROL Attente]** ![](assets/wait.png).
1. Dans **[!UICONTROL Durée]**, cliquez sur ![](assets/duration-icon.png) et sélectionnez un jour.
1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Ciblage]**, effectuez un glisser-déposer d'une activité **[!UICONTROL Requête]** ![](assets/query.png).
1. Double-cliquez sur l'activité.
1. Dans **[!UICONTROL Raccourcis]**, effectuez un glisser-déposer des **[!UICONTROL Logs de tracking]** et de l'opérateur **[!UICONTROL existe]**.
1. Dans **[!UICONTROL Raccourcis]** &gt; **[!UICONTROL Diffusion]**, effectuez un glisser-déposer de l'élément **[!UICONTROL diffusion]** avec l'opérateur **[!UICONTROL est égal à]** et sélectionnez la diffusion comme valeur.
1. Dans **[!UICONTROL Raccourcis]** &gt; **[!UICONTROL Diffusion]**, effectuez un glisser-déposer de l'élément **[!UICONTROL type]** et sélectionnez **[!UICONTROL Ouverture]** comme valeur.
1. Sélectionnez l'opérateur **[!UICONTROL sauf]** entre les règles.
1. Cliquez sur **[!UICONTROL Confirmer]**.

## Créer une diffusion SMS{#creating-a-sms-delivery}

1. Effectuez un glisser-déposer d'une diffusion SMS après chaque segment.
1. Cliquez sur l'activité et sélectionnez ![](assets/edit_darkgrey-24px.png) pour édition.
1. Sélectionnez **[!UICONTROL SMS simple]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle de SMS et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés SMS et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre SMS, cliquez sur **[!UICONTROL Concepteur d'email]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre SMS avec des offres spécifiques à chaque emplacement.
Pour plus d'informations, consultez la section décrivant la [conception d'un SMS](../../channels/using/creating-an-sms-message.md).
1. Cliquez sur **[!UICONTROL Aperçu]** pour vérifier votre mise en page.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

![](assets/wf-retargeting-non-openers.png)

**Rubriques connexes :**

* [Requête](../../automating/using/query.md)
* [Diffusion SMS](../../automating/using/sms-delivery.md)
* [Diffusion Email ](../../automating/using/email-delivery.md)
* [Canal email](../../channels/using/creating-an-email.md)
