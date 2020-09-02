---
title: Vue d’ensemble
description: Cette section explique dans le détail comment appeler un workflow avec des paramètres externes.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5da41379d718d78d7990fd2d767ec21216487b0d
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 88%

---


# Présentation {#calling-a-workflow-with-external-parameters}

Campaign Standard vous permet d’appeler un workflow avec des paramètres (un nom d’audience à cibler, un nom de fichier à importer, un contenu de message, etc.). De cette façon, vous pouvez facilement intégrer vos automatisations Campaign avec votre système externe.

Prenons l’exemple suivant où nous voulons envoyer des emails directement à partir d’un CMS. Dans ce cas, vous pouvez configurer votre système afin de sélectionner l’audience et le contenu email dans le CMS. Cliquer sur Envoyer appellera ensuite un workflow Campaign avec ces paramètres, vous permettant de les utiliser dans le workflow de manière à définir l’audience et le contenu d’URL à utiliser dans la diffusion.

Le processus pour appeler un workflow avec des paramètres est le suivant :

1. Déclarez les paramètres dans l’activité **[!UICONTROL Signal externe]**. Voir [Déclarer les paramètres dans l’activité Signal externe](../../automating/using/declaring-parameters-external-signal.md).
1. Configurez l’activité **[!UICONTROL Fin]** ou l’appel API pour définir les paramètres et déclencher l’activité **[!UICONTROL Signal externe]** du workflow. Voir la section [](../../automating/using/defining-parameters-calling-workflow.md)
1. Une fois le processus déclenché, les paramètres sont incorporés dans les variables de événement du processus et peuvent être utilisés dans le processus. Voir [](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
