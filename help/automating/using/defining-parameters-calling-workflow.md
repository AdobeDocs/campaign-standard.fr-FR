---
title: Définir les paramètres lors de l'appel du workflow
description: Cette section explique dans le détail comment appeler un workflow avec des paramètres externes.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
TQID: https://experienceleague.adobe.com/-YjlK1Op8P08sxb--BOHl8AWyciX4BqPnCPQ3lpD3Co
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 203
ht-degree: 100%

---

# Définir les paramètres lors de l&#39;appel du workflow {#defining-the-parameters-when-calling-the-workflow}

Cette section explique comment définir des paramètres lors de l’appel d’un workflow. Pour plus d’informations sur l’exécution de cette opération à partir d’un appel API, consultez la [documentation des API REST](../../api/using/triggering-a-signal-activity.md).

Avant de définir les paramètres, vérifiez les éléments suivants :

* Les paramètres ont été déclarés dans l’activité **[!UICONTROL Signal externe]**. Voir [cette page](../../automating/using/declaring-parameters-external-signal.md).
* Le workflow contenant l’activité Signal est en cours d’exécution.

Pour configurer l’activité **[!UICONTROL Fin]**, suivez les étapes ci-dessous :

1. Ouvrez l’activité **[!UICONTROL Fin]**, puis sélectionnez l’onglet **[!UICONTROL Signal externe]**.
1. Sélectionnez le workflow et l’activité Signal externe que vous voulez appeler.
1. Cliquez sur le bouton **[!UICONTROL Créer un élément]** pour ajouter un paramètre, puis indiquez son nom et sa valeur.

   * **[!UICONTROL Nom]** : nom déclaré dans l&#39;activité **[!UICONTROL Signal externe]** (voir [cette page](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Valeur]** : valeur que vous souhaitez assigner au paramètre. La valeur doit respecter la **syntaxe standard**, décrite dans [cette section](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Veillez à ce que tous les paramètres soient déclarés dans l’activité **[!UICONTROL Signal externe]**. Dans le cas contraire, une erreur se produira lors de l’exécution de l’activité.

1. Une fois les paramètres définis, confirmez l’activité, puis enregistrez votre workflow.
