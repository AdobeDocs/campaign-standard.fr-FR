---
solution: Campaign Standard
product: campaign
title: Création de diffusions à la date de création du profil
description: Ce cas pratique montre comment créer des diffusions à la date de création du profil.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
translation-type: ht
source-git-commit: 45c80b5e6bf2169c5acf6eea70da9e2f130982c8
workflow-type: ht
source-wordcount: '415'
ht-degree: 100%

---


# Création de diffusions à la date de création des profils {#creation-date-query}

Vous pouvez envoyer une offre par email à la date anniversaire de la création du profil du client.

1. Dans **[!UICONTROL Activités marketing]**, cliquez sur **[!UICONTROL Créer]** et sélectionnez **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** en tant que type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés du workflow, puis cliquez sur **[!UICONTROL Créer]**.

## Créer une activité Planificateur {#creating-a-scheduler-activity}

1. Dans **[!UICONTROL Activités]** > **[!UICONTROL Exécution]**, effectuez un glisser-déposer d&#39;une activité [](../../automating/using/scheduler.md)Planificateur.
1. Double-cliquez sur l&#39;activité.
1. Configurez l&#39;exécution de votre diffusion.
1. Dans **[!UICONTROL Fréquence d&#39;exécution]**, sélectionnez **[!UICONTROL Quotidienne]**.
1. Sélectionnez une **[!UICONTROL Heure]** et **[!UICONTROL Répéter le traitement selon la périodicité suivante]** pour votre workflow.
1. Sélectionnez une date de **[!UICONTROL Début]** et d&#39;**[!UICONTROL Expiration]** de votre workflow.
1. Validez votre activité et sauvegardez votre workflow.

>[!NOTE]
>
>Pour démarrer votre workflow dans un fuseau horaire spécifique, dans l&#39;onglet **[!UICONTROL Options d&#39;exécution]**, configurez le fuseau horaire du planificateur dans le champ **[!UICONTROL Fuseau horaire.]** Par défaut, le fuseau horaire sélectionné est celui défini dans les propriétés du workflow (voir [Construire un workflow](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Créer une activité Requête {#creating-a-query-activity}

1. Pour sélectionner les destinataires, effectuez un glisser-déposer d&#39;une activité [](../../automating/using/query.md)Requête et double-cliquez dessus.
1. Ajoutez des **[!UICONTROL Profils]** et sélectionnez **[!UICONTROL Ne plus contacter par email]** avec la valeur **[!UICONTROL non]**.

### Récupération des profils créés le même jour que le jour d’exécution {#retrieving-profiles-created-on-the-same-day}

1. Dans **[!UICONTROL Profil]**, effectuez un glisser-déposer du champ **[!UICONTROL Créé le]**. et cliquez sur **[!UICONTROL Mode avancé]**.
   ![](assets/advanced_mode.png)
1. Dans la **[!UICONTROL Liste des fonctions]**, double-cliquez sur **[!UICONTROL Jour]** depuis le nœud **[!UICONTROL Date]**.
1. Ensuite, insérez le champ **[!UICONTROL Créé le]** en tant qu&#39;argument.
1. Sélectionnez **[!UICONTROL égal à (=)]** comme opérateur.
1. Pour la valeur, sélectionnez **[!UICONTROL Jour]** depuis le nœud **[!UICONTROL Date]** dans la **[!UICONTROL Liste des fonctions]**.
1. Insérez la fonction **[!UICONTROL GetDate()]** en tant qu&#39;argument.

Vous avez récupéré les profils dont le jour de création correspond au jour en cours.

Vous devez obtenir :

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Cliquez sur **[!UICONTROL Confirmer]**.

### Récupérer les profils créés le même mois que le mois d’exécution{#retrieving-profiles-created-on-the-same-month}

1. Dans l&#39;éditeur de **[!UICONTROL requêtes]**, sélectionnez la première requête et dupliquez-la.
1. Ouvrez le duplicata.
1. Remplacez **[!UICONTROL Jour]** par **[!UICONTROL Mois]** dans la requête.
1. Cliquez sur **[!UICONTROL Confirmer]**.

![](assets/month_rule.png)

Vous devez obtenir :

``` Month(@created) = Month(GetDate()) ```

La requête finale affiche :

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Créer une diffusion email{#creating-an-email-delivery}

1. Placez une activité [Diffusion Email](../../automating/using/email-delivery.md).
1. Cliquez sur l&#39;activité et sélectionnez ![](assets/edit_darkgrey-24px.png) pour édition.
1. Sélectionnez **[!UICONTROL Email récurrent]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle d&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés de l&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Pour créer la mise en page de votre email, cliquez sur **[!UICONTROL Concepteur d&#39;email]**.
1. Insérez des éléments ou sélectionnez un modèle existant.
1. Personnalisez votre email à l&#39;aide de champs et de liens.
Pour plus d&#39;informations, consultez la section décrivant la [conception d&#39;un email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Cliquez sur **[!UICONTROL Aperçu]** pour vérifier votre mise en page.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

**Rubriques connexes :**

* [Canal email](../../channels/using/creating-an-email.md)
