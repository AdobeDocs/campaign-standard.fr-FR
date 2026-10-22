---
title: Vue d'ensemble
description: Cette section explique dans le détail comment appeler un workflow avec des paramètres externes.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
TQID: 'https://experienceleague.adobe.com/Pin9vFRMMylFFKw6VSvQowwXvzAn1Ihg76e2cSoaeyw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%
---
# Vue d&#39;ensemble {#calling-a-workflow-with-external-parameters}

Campaign Standard vous permet d&#39;appeler un workflow avec des paramètres (un nom d&#39;audience à cibler, un nom de fichier à importer, un contenu de message, etc.). De cette façon, vous pouvez facilement intégrer vos automatisations Campaign avec votre système externe.

Prenons l’exemple suivant où nous voulons envoyer des emails directement à partir d’un CMS. Dans ce cas, vous pouvez configurer votre système afin de sélectionner l’audience et le contenu email dans le CMS. Cliquer sur Envoyer appellera ensuite un workflow Campaign avec ces paramètres, vous permettant de les utiliser dans le workflow de manière à définir l’audience et le contenu d’URL à utiliser dans la diffusion.

Le processus pour appeler un workflow avec des paramètres est le suivant :

1. Déclarez les paramètres dans l’activité **[!UICONTROL Signal externe]**. Voir [Déclarer les paramètres dans l’activité Signal externe](../../automating/using/declaring-parameters-external-signal.md).
1. Configurez l’activité **[!UICONTROL Fin]** ou l’appel API pour définir les paramètres et déclencher l’activité **[!UICONTROL Signal externe]** du workflow. Voir [cette page](../../automating/using/defining-parameters-calling-workflow.md).
1. Une fois le workflow déclenché, les paramètres sont ingérés dans les variables d&#39;événements du workflow et peuvent être utilisés au sein de ce dernier. Voir [cette page](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
