---
title: '"Case d''utilisation du workflow: Créer une livraison hebdomadaire"'
seo-title: '"Case d''utilisation du workflow: Créer une livraison hebdomadaire"'
description: '"Case d''utilisation du workflow: Créer une livraison hebdomadaire"'
seo-description: '"Case d''utilisation du workflow: Créer une livraison hebdomadaire"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: 'execution-activities '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,case d'utilisation,requête,livraison,planificateur
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# Cas d'utilisation du flux de travail: Créer une livraison par courrier électronique tous les mardis{#creating-email-every-tuesday}

Vous pouvez envoyer un email tous les mardis à tous les clients pour des offres spéciales.

1. In **[!UICONTROL Marketing Activities]**, click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** comme type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Entrez les propriétés du workflow et cliquez sur **[!UICONTROL Créer]**.

## Creating a Scheduler activity{#creating-a-scheduler-activity}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Exécution]**, faites glisser et déposez une activité **[!UICONTROL du]** Planificateur.
1. Double-cliquez sur l'activité.
1. Configurez l'exécution de votre livraison.
1. Dans la fréquence **** d'exécution, sélectionnez **[!UICONTROL Hebdomadaire]**.
1. Sélectionnez une **[!UICONTROL heure]** et une fréquence **[!UICONTROL de]** répétition pour vos livraisons.
1. Dans **[!UICONTROL Jours de la semaine]**, sélectionnez **[!UICONTROL Mardi]**.
1. Spécifiez un paramètre **[!UICONTROL Start]** et **[!UICONTROL Expiration]** pour votre workflow.
1. Validez votre activité et sauvegardez votre workflow.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Pour démarrer votre flux de travail dans un **[!UICONTROL fuseau horaire]** spécifique, dans l'onglet Options **[!UICONTROL d']** exécution, définissez le fuseau horaire de votre planificateur dans le champ Fuseau horaire.

## Creating a Query activity{#creating-a-query-activity}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Ciblage]**, pour sélectionner les destinataires, faites glisser et déplacer une activité de **[!UICONTROL requête]** et double-cliquez dessus.
1. Dans **[!UICONTROL Raccourcis]** &gt; **[!UICONTROL Profil]**, faites glisser et déposez le **[!UICONTROL courrier électronique]**.
1. Sélectionnez **[!UICONTROL n'est pas vide]** en tant qu'opérateur.
1. Dans **[!UICONTROL Raccourcis]** &gt; **[!UICONTROL Général]**, ajoutez des profils et sélectionnez **[!UICONTROL ne plus contacter par e-mail]** avec la valeur **[!UICONTROL Non]**.
1. Cliquez sur **[!UICONTROL Confirmer]**.

![](assets/wf-complement-query.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Chaînes]**, faites glisser et déposez une livraison **[!UICONTROL par]** courriel.
1. Cliquez sur l'activité et sélectionnez ![](assets/edit_darkgrey-24px.png) à modifier.
1. Sélectionnez **[!UICONTROL Courrier]** récurrent et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle de courriel et cliquez sur **[!UICONTROL Suivant]**.
1. Entrez les propriétés du courrier électronique et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre e-mail, cliquez sur **[!UICONTROL Utiliser le Concepteur]** d'e-mails.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre e-mail en utilisant des champs et des liens.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour plus d'informations, reportez-vous à la [conception d'un e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Rubriques connexes :**

* [Activité de requête](../..//automating/using/query.md)
* [Activité Planificateur](../..//automating/using/scheduler.md)
* [Diffusion Email ](../..//automating/using/email-delivery.md)
* [Canal email](../..//channels/using/creating-an-email.md)
