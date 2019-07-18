---
title: Notions de modèle de données
seo-title: Notions de modèle de données
description: Notions de modèle de données
seo-description: Découvrez le modèle de données Adobe Campaign et comment le modifier.
page-status-flag: jamais activé
uuid: cacd 563 f -6936-4 b 3 e -83 e 3-5 d 4 ae 31 d 44 e 8
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: développement
content-type: référence
topic-tags: about-custom-resources
discoiquuid: 4 e 0468 da -3052-4 ce 5-8174-45 aba 1 f 5 c 4 ed
context-tags: Cusresource, overview ; Eventcusresource, présentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c880b265cf83cb76b2cdbe3cbdd77182adb71bb1

---


# Notions de modèle de données{#data-model-concepts}

Un modèle de données d'usine est fourni avec Adobe Campaign. Ce modèle de données peut être modifié par les [administrateurs](../../administration/using/types-of-users.md#functional-administrators) qui peuvent ajouter de nouvelles ressources ou des extensions à des ressources existantes.

>[!CAUTION]
>
>La création et la modification de ressources sont des opérations sensibles qui doivent être effectuées uniquement par des utilisateurs experts.

The **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** menu, accessed via the Adobe Campaign logo, allows you to manage your **custom resources**, **publish** them, and **access the diagnostic tools**.

Les données utilisées par Adobe Campaign sont décrites par le biais de différentes ressources.

Il est possible d'**enrichir le modèle de données** fourni en créant vos propres ressources personnalisées, comme des tables d'achats ou de produits par exemple.

Les ressources d'usine (comme les campagnes, les e-mails ou les audiences) ne peuvent pas être modifiées. Cependant, il est possible de les étendre pour leur ajouter de nouveaux champs.

>[!NOTE]
>
>Une représentation du modèle de données pour les ressources d'usine figure [ici](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

Il est également possible de **configurer la navigation** dans les écrans correspondant à la ressource créée.

Les champs d'extension sont générés avec un préfixe de sorte qu'ils n'entrent jamais en conflit avec les champs d'usine.
