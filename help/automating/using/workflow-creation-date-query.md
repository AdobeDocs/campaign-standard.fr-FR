---
title: '"Case d''utilisation du workflow: Création de livraisons à la date de création du profil"'
seo-title: '"Case d''utilisation du workflow: Création de livraisons à la date de création du profil"'
description: '"Case d''utilisation du workflow: Création de livraisons à la date de création du profil"'
seo-description: '"Case d''utilisation du workflow: Création de livraisons à la date de création du profil"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: 'execution-activities '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,case d'utilisation,requête
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# Cas d'utilisation du workflow : Créer des livraisons à la date de création des profils {#creation-date-query}

Vous pouvez envoyer une offre par courriel à l'occasion de l'anniversaire de la création du profil du client.

1. In **[!UICONTROL Marketing Activities]**, click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** comme type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Entrez les propriétés du workflow et cliquez sur **[!UICONTROL Créer]**.

## Creating a Scheduler activity {#creating-a-scheduler-activity}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Exécution]**, faites glisser et déposez une activité **[!UICONTROL du]** Planificateur.
1. Double-cliquez sur l'activité.
1. Configurez l'exécution de votre livraison.
1. Dans la fréquence **** d'exécution, sélectionnez **[!UICONTROL Quotidien]**.
1. Sélectionnez une **[!UICONTROL heure]** et la fréquence **[!UICONTROL d'exécution de la]** répétition pour votre workflow.
1. Sélectionnez une date de **[!UICONTROL début]** et une date d' **[!UICONTROL expiration]** pour votre workflow.
1. Validez votre activité et sauvegardez votre workflow.

>[!NOTE]
>
>Pour démarrer votre workflow à un fuseau horaire spécifique, dans l'onglet Options **[!UICONTROL d']** exécution, définissez le fuseau horaire de votre planificateur dans le champ **[!UICONTROL fuseau]** horaire.

![](assets/time_zone.png)

## Creating a Query activity {#creating-a-query-activity}

1. Pour sélectionner des destinataires, faites glisser-déplacer une activité **** Requête et double-cliquez dessus.
1. Ajouter **[!UICONTROL des profils]** et sélectionner **[!UICONTROL ne plus contacter par e-mail]** avec la valeur **[!UICONTROL no]**.

### Récupération des profils créés le même jour que le jour de l'exécution {#retriving-profiles-created-on-the-same-day}

1. Dans **[!UICONTROL Profil]**, faites glisser et déposez le champ **[!UICONTROL Créé]** . et cliquez sur Mode ****Avancé.
   ![](assets/advanced_mode.png)
1. Dans la **[!UICONTROL liste des fonctions]**, double-cliquez sur **[!UICONTROL Jour]** à partir du noeud **[!UICONTROL Date]**.
1. Ensuite, insérez le champ **[!UICONTROL Créé]** comme argument.
1. Sélectionnez **[!UICONTROL égal à (=)]** comme opérateur.
1. Pour Valeur, sélectionnez **[!UICONTROL Jour]** dans le noeud **[!UICONTROL Date]** de la **[!UICONTROL liste des fonctions]**.
1. Insérez la fonction **[!UICONTROL GetDate()]** comme argument.

Vous avez récupéré les profils dont le jour de création est égal au jour actuel.

Vous devriez finir par :

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Cliquez sur **[!UICONTROL Confirmer]**.

### Récupération des profils créés le même mois que le mois d'exécution{#retriving-profiles-created-on-the-same-month}

1. Dans l'éditeur **[!UICONTROL Requête]** , sélectionnez la première requête et dupliquez-la.
1. Ouvrez le doublon.
1. Remplacez **[!UICONTROL Jour]** par **[!UICONTROL Mois]** dans la requête.
1. Cliquez sur **[!UICONTROL Confirmer]**.

![](assets/month_rule.png)

Vous devriez finir par ceci :

``` Month(@created) = Month(GetDate()) ```

La dernière requête s'affiche:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. Faites glisser et déposez une livraison de courrier électronique.
1. Cliquez sur l'activité et sélectionnez ![](assets/edit_darkgrey-24px.png) à modifier.
1. Sélectionnez **[!UICONTROL Courrier]** récurrent et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle de courriel et cliquez sur **[!UICONTROL Suivant]**.
1. Entrez les propriétés du courrier électronique et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre e-mail, cliquez sur **[!UICONTROL Email Designer]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre e-mail en utilisant des champs et des liens.
Pour plus d'informations, reportez-vous à la [conception d'un e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Cliquez sur **[!UICONTROL Aperçu]** pour vérifier votre disposition.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

**Rubriques connexes :**

* [Requête](../../automating/using/query.md)
* [Planificateur](../../automating/using/scheduler.md)
* [Diffusion Email ](../../automating/using/email-delivery.md)
* [Canal email](../../channels/using/creating-an-email.md)
