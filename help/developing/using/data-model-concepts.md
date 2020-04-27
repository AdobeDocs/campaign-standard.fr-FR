---
title: Notions de modèle de données
description: Découvrez le modèle de données Adobe Campaign et comment le modifier.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Notions de modèle de données{#data-model-concepts}

Un modèle de données d&#39;usine est fourni avec Adobe Campaign. Ce modèle de données peut être modifié par les [administrateurs](../../administration/using/users-management.md#functional-administrators) qui peuvent ajouter de nouvelles ressources ou des extensions à des ressources existantes.

>[!CAUTION]
>
>La création et la modification de ressources sont des opérations sensibles qui doivent être effectuées uniquement par des utilisateurs experts.

The **[!UICONTROL Administration]** > **[!UICONTROL Development]** menu, accessed via the Adobe Campaign logo, allows you to manage your **custom resources**, **publish** them, and **access the diagnostic tools**.

Les données utilisées par Adobe Campaign sont décrites par le biais de différentes ressources. Il est possible d&#39;**enrichir le modèle de données** fourni en créant vos propres ressources personnalisées, comme des tables d&#39;achats ou de produits par exemple.

Les ressources intégrées (telles que les campagnes, les courriels ou les  de ) ne peuvent pas être modifiées. Cependant, il est possible de les étendre pour leur ajouter de nouveaux champs.

Les champs d’extension sont générés avec un préfixe afin de ne jamais entrer en conflit avec les champs intégrés.

>[!NOTE]
>
>Vous trouverez une représentation de modèle de données pour les ressources intégrées dans [cette page](../../developing/using/datamodel-introduction.md).

Il est également possible de [configurer la navigation](configuring-the-screen-definition.md) dans les écrans correspondant à la ressource créée.

Il est possible **d&#39;exporter et d&#39;importer** des ressources personnalisées, par exemple d&#39;un environnement de développement vers un environnement de production. Voir à ce propos ce [cas pratique détaillé](../../automating/using/exporting-importing-custom-resources.md).
