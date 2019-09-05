---
title: Notions de modèle de données
seo-title: Notions de modèle de données
description: Notions de modèle de données
seo-description: Découvrez le modèle de données Adobe Campaign et comment le modifier.
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
translation-type: ht
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# Notions de modèle de données{#data-model-concepts}

Un modèle de données d'usine est fourni avec Adobe Campaign. Ce modèle de données peut être modifié par les [administrateurs](../../administration/using/users-management.md#functional-administrators) qui peuvent ajouter de nouvelles ressources ou des extensions à des ressources existantes.

>[!CAUTION]
>
>La création et la modification de ressources sont des opérations sensibles qui doivent être effectuées uniquement par des utilisateurs experts.

Le menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Développement]**, accessible via le logo Adobe Campaign, vous permet de gérer vos **ressources personnalisées**, de les **publier** et d'**accéder aux outils de diagnostic**.

Les données utilisées par Adobe Campaign sont décrites par le biais de différentes ressources.

Il est possible d'**enrichir le modèle de données** fourni en créant vos propres ressources personnalisées, comme des tables d'achats ou de produits par exemple.

Les ressources d'usine (comme les campagnes, les e-mails ou les audiences) ne peuvent pas être modifiées. Cependant, il est possible de les étendre pour leur ajouter de nouveaux champs.

>[!NOTE]
>
>Une représentation du modèle de données pour les ressources d'usine figure [ici](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

Il est également possible de **configurer la navigation** dans les écrans correspondant à la ressource créée.

Les champs d'extension sont générés avec un préfixe de sorte qu'ils n'entrent jamais en conflit avec les champs d'usine.
