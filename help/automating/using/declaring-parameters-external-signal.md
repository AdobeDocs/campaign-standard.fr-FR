---
solution: Campaign Standard
product: campaign
title: Appeler un workflow avec des paramètres externes
description: Cette section explique dans le détail comment appeler un workflow avec des paramètres externes.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 100%

---


# Déclarer les paramètres dans l’activité Signal externe       {#declaring-the-parameters-in-the-external-signal-activity}

Pour appeler un workflow avec des paramètres, la première étape consiste à les déclarer dans une activité **[!UICONTROL Signal externe]**.

1. Ouvrez l’activité **[!UICONTROL Signal externe]** et sélectionnez ensuite l’onglet **[!UICONTROL Paramètres]**.
1. Cliquez sur le bouton **[!UICONTROL Créer un élément]**, puis spécifiez le nom et le type de chaque paramètre.

   >[!CAUTION]
   >
   >Veillez à ce que le nom et le nombre de paramètres soient identiques à ce qui est défini lors de l&#39;appel du workflow (voir [cette page](../../automating/using/defining-parameters-calling-workflow.md)). De plus, les types des paramètres doivent être cohérents par rapport aux valeurs attendues.

   ![](assets/extsignal_declaringparameters_1.png)

1. Une fois les paramètres déclarés, terminez la configuration du workflow, puis exécutez-le.
