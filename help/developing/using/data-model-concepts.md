---
solution: Campaign Standard
product: campaign
title: Notions de modèle de données
description: Découvrez le modèle de données Adobe Campaign et comment le modifier.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 100%

---


# Notions de modèle de données{#data-model-concepts}

Un modèle de données d’usine est fourni avec Adobe Campaign. Ce modèle de données peut être modifié par les [administrateurs](../../administration/using/users-management.md#functional-administrators) qui peuvent ajouter de nouvelles ressources ou des extensions à des ressources existantes.

>[!CAUTION]
>
>La création et la modification de ressources sont des opérations sensibles qui doivent être effectuées uniquement par des utilisateurs experts.

Le menu **[!UICONTROL Administration]** > **[!UICONTROL Développement]** accessible via le logo Adobe Campaign, vous permet de gérer vos **ressources personnalisées**, de les **publier** et d’**accéder aux outils de diagnostic**.

Les données utilisées par Adobe Campaign sont décrites par le biais de différentes ressources. Il est possible d’**enrichir le modèle de données** fourni en créant vos propres ressources personnalisées, comme des tables d’achats ou de produits par exemple.

Les ressources natives (comme les campagnes, les e-mails ou les audiences) ne peuvent pas être modifiées. Cependant, il est possible de les étendre pour leur ajouter de nouveaux champs.

Les champs d’extension sont générés avec un préfixe de sorte qu’ils n’entrent jamais en conflit avec les champs natifs.

>[!NOTE]
>
>Vous trouverez une représentation de modèle de données pour les ressources natives dans [cette page](../../developing/using/datamodel-introduction.md).

Il est également possible de [configurer la navigation](configuring-the-screen-definition.md) dans les écrans correspondant à la ressource créée.

Il est possible **d’exporter et d’importer** des ressources personnalisées, par exemple d’un environnement de développement vers un environnement de production. Voir à ce propos ce [cas pratique détaillé](../../automating/using/exporting-importing-custom-resources.md).

>[!CAUTION]
>
>Seuls les [administrateurs](../../administration/using/users-management.md#functional-administrators) fonctionnels, avec un rôle d’**[!UICONTROL administration]** et un accès aux entités **Toutes**, peuvent accéder aux logs d’envoi, aux logs de messages, aux logs de tracking, aux logs d’exclusion et aux logs d’abonnement. Un utilisateur autre qu’administrateur peut cibler ces logs mais en commençant par une table liée (profils, diffusion).
