---
title: Lecture d'audience
description: L'activité Lecture d'audience permet de récupérer une audience existante et de l'affiner en y appliquant des conditions de filtrage supplémentaires.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9a77a2c7-cc1c-416f-8103-bb7d5c84a373
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '225'
ht-degree: 100%

---

# Lecture d&#39;audience{#read-audience}

## Description {#description}

![](assets/prefill.png)

L&#39;activité **[!UICONTROL Lecture d&#39;audience]** permet de récupérer une audience existante et de l&#39;affiner en y appliquant des conditions de filtrage supplémentaires.

## Contexte d&#39;utilisation  {#context-of-use}

L&#39;activité **[!UICONTROL Lecture d&#39;audience]** est une version simplifiée de l&#39;activité **[!UICONTROL Requête]**, conçue pour les cas où l&#39;on souhaite simplement sélectionner une audience existante.

**Rubriques connexes :**

* [Cas pratique : union sur deux audiences affinées](../../automating/using/union-on-two-refined-audiences.md)
* [Cas pratique : réconcilier une audience de type fichier avec la base de données](../../automating/using/reconcile-file-audience-with-database.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Lecture d&#39;audience]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Sélectionnez l&#39;audience que vous souhaitez récupérer dans l&#39;onglet **[!UICONTROL Propriétés]**.

   Les types d’audience suivants peuvent être récupérés : **[!UICONTROL Liste]**, **[!UICONTROL Requête]**, **[!UICONTROL Fichier]** et **[!UICONTROL Experience Cloud]**. Pour plus d&#39;informations sur les types d&#39;audiences, consultez la documentation [Audiences](../../audiences/using/about-audiences.md).

   L&#39;option **[!UICONTROL Utiliser une audience dynamique]** vous permet de définir le nom de l&#39;audience à cibler en fonction des variables d&#39;événements du workflow. Voir à ce propos [cette page](../../automating/using/customizing-workflow-external-parameters.md).

   ![](assets/readaudience_activity1.png)

1. Pour appliquer un filtrage supplémentaire à l&#39;audience sélectionnée, ajoutez des conditions via l&#39;onglet **[!UICONTROL Filtrage de la source]** de l&#39;activité.

   Pour plus d&#39;informations sur la création des conditions de filtrage, voir la documentation [Créer des requêtes](../../automating/using/editing-queries.md#creating-queries).

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.
