---
title: Création d’une diffusion hebdomadaire
description: Ce cas pratique montre comment créer une diffusion hebdomadaire.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '297'
ht-degree: 100%

---


# Création d’une diffusion email tous les mardis{#creating-email-every-tuesday}

Vous pouvez envoyer un email tous les mardis à tous les clients pour des offres spéciales.

1. Dans **[!UICONTROL Activités marketing]**, cliquez sur **[!UICONTROL Créer]** et sélectionnez **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** en tant que type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés du workflow, puis cliquez sur **[!UICONTROL Créer]**.

## Créer une activité Planificateur{#creating-a-scheduler-activity}

1. Dans **[!UICONTROL Activités]** > **[!UICONTROL Exécution]**, effectuez un glisser-déposer d&#39;une activité [](../../automating/using/scheduler.md)Planificateur.
1. Double-cliquez sur l&#39;activité.
1. Configurez l&#39;exécution de votre diffusion.
1. Dans **[!UICONTROL Fréquence d&#39;exécution]**, sélectionnez **[!UICONTROL Hebdomadaire]**.
1. Sélectionnez une **[!UICONTROL Heure]** et **[!UICONTROL Répéter le traitement selon la périodicité suivante]** pour vos diffusions.
1. Dans **[!UICONTROL Jours de la semaine]**, sélectionnez **[!UICONTROL Mardi]**.
1. Spécifiez un paramètre de **[!UICONTROL Début]** et d&#39;**[!UICONTROL Expiration]** pour le workflow.
1. Validez votre activité et sauvegardez votre workflow.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Pour démarrer votre workflow dans un **[!UICONTROL Fuseau horaire]** spécifique, dans l&#39;onglet **[!UICONTROL Options d&#39;exécution]**, configurez le fuseau horaire du planificateur dans le champ Fuseau horaire. Par défaut, le fuseau horaire sélectionné est celui défini dans les propriétés du workflow (voir [Construire un workflow](../../automating/using/building-a-workflow.md)).

## Créer une activité Requête{#creating-a-query-activity}

1. Dans **[!UICONTROL Activités]** > **[!UICONTROL Ciblage]**, pour sélectionner des destinataires, effectuez un glisser-déposer d’une activité [Requête](../../automating/using/query.md) et double-cliquez dessus.
1. Dans **[!UICONTROL Raccourcis]** > **[!UICONTROL Profil]**, effectuez un glisser-déposer de l&#39;élément **[!UICONTROL Email]**.
1. Sélectionnez **[!UICONTROL n&#39;est pas vide]** en tant qu&#39;opérateur.
1. Dans **[!UICONTROL Raccourcis]** > **[!UICONTROL Général]**, ajoutez des profils et sélectionnez **[!UICONTROL Ne plus contacter par email]** avec la valeur **[!UICONTROL Non]**.
1. Cliquez sur **[!UICONTROL Confirmer]**.

![](assets/wf-complement-query.png)

## Créer une diffusion email{#creating-an-email-delivery}

1. Dans **[!UICONTROL Activités]** > **[!UICONTROL Canaux]**, effectuez un glisser-déposer d’une activité [Diffusion Email](../../automating/using/email-delivery.md).
1. Cliquez sur l&#39;activité et sélectionnez ![](assets/edit_darkgrey-24px.png) pour édition.
1. Sélectionnez **[!UICONTROL Email récurrent]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle d&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés de l&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la disposition de votre email, cliquez sur **[!UICONTROL Utiliser le Concepteur d&#39;email]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre email à l&#39;aide de champs et de liens.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour plus d&#39;informations, consultez la section décrivant la [conception d&#39;un email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Rubriques connexes :**

* [Canal email](../../channels/using/creating-an-email.md)
