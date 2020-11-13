---
title: Appeler un workflow avec des paramètres externes
description: Cette section explique dans le détail comment appeler un workflow avec des paramètres externes.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
translation-type: tm+mt
source-git-commit: 121b36056317cc89909607220f988c02ae470f08
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 80%

---


# Déclarer les paramètres dans l’activité Signal externe     {#declaring-the-parameters-in-the-external-signal-activity}

Pour appeler un workflow avec des paramètres, la première étape consiste à les déclarer dans une activité **[!UICONTROL Signal externe]**.

1. Ouvrez l’activité **[!UICONTROL Signal externe]** et sélectionnez ensuite l’onglet **[!UICONTROL Paramètres]**.
1. Cliquez sur le bouton **[!UICONTROL Créer un élément]**, puis spécifiez le nom et le type de chaque paramètre.

   >[!CAUTION]
   >
   >Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [this page](../../automating/using/defining-parameters-calling-workflow.md)). De plus, les types des paramètres doivent être cohérents par rapport aux valeurs attendues.

   ![](assets/extsignal_declaringparameters_1.png)

1. Une fois les paramètres déclarés, terminez la configuration du workflow, puis exécutez-le.
