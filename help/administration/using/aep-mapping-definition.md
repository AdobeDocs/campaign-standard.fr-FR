---
title: Définition d’un mapping
description: Découvrez comment mapper un champ Campaign Standard avec un champ XDM (Experience Data Model).
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 327d0e4f862b39c60fb3943d1128f4f42828bc0d

---


# Définition d’un mapping {#mapping-definition}

>[!IMPORTANT]
>
>Le service Campaign Standard Data est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l&#39;Assistance clientèle d&#39;Adobe si vous souhaitez y accéder.

Dans cette section, vous allez découvrir comment mapper un champ Campaign Standard avec un champ XDM (Experience Data Model).

Pour effectuer cette tâche, les prérequis sont les suivants :

* une définition de schéma XDM via l’interface ou en utilisant l’API REST associée à XDM ;
* la création d’un jeu de données en fonction de la définition de schéma XDM.

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** , puis sélectionnez l’ **[!UICONTROL Data mappings]** entrée.

1. Click on **[!UICONTROL Create]** to start a new XDM mapping.

   ![](assets/aep_createmapping.png)

1. Renseignez les champs obligatoires et sélectionnez :

   * une **dimension de ciblage** : il s’agit du schéma Campaign Standard à mapper ;
   * un **jeu de données** : il s’agit du package de données associé à un schéma XDM dans Adobe Experience Platform.

>[!NOTE]
>
>Pour qu’un lot soit ingéré dans Real-time Customer Profile ou Identity Service, le jeu de données doit être [activé pour Real-time Customer Profile](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html).
>
>Si le jeu de données sélectionné est déjà utilisé dans un mapping de données existant, un avertissement s’affiche pour vous informer que vos données peuvent être remplacées dans Adobe Experience Platform. Cette situation peut se produire lorsqu’il existe des destinataires communs dans les mappings de données utilisant un même jeu de données.

The following screen presents the **[!UICONTROL Field mappings]** section where you can create a new mapping for each field in the Campaign Standard schema.

![](assets/aep_fieldmappings.png)

The **[!UICONTROL Create new field mapping]** button allows you to select the Campaign Standard field and the corresponding field path expression in the XDM schema.

Si vous ne parvenez pas à trouver un champ Campaign Standard, vous pouvez utiliser le champ de recherche pour le rechercher. Actuellement, la recherche ne fonctionne que pour les champs ouverts dans la hiérarchie.

![](assets/aep_mapfield.png)

Les ressources étendues définies dans Campaign Standard sont mappées comme tous les champs natifs. Elles sont définies dans l’extension _customer/default dans XDM.

![](assets/aep_fieldscusmapping.png)

Vous pouvez personnaliser l’extension XDM via l’API et définir votre propre extension pour mieux contrôler le mapping.

Voir le [tutoriel relatif à l’API Schema Registry](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html) pour en savoir plus.

Pour mapper un champ d’énumération, vous devez utiliser l’éditeur d’expression afin de définir chaque valeur d’énumération correspondant à la valeur XDM. Par exemple, postalAdressfield doit être défini comme suit :

![](assets/aep_enummapping.png)

Si la valeur XDM est définie sous la forme d’une énumération dans le schéma XDM, vous pouvez utiliser la fonction EXDM native qui remplacera automatiquement la syntaxe **lif**.

![](assets/aep_enummappingexdm.png)

Pour éditer un mapping XDM, ouvrez-le, modifiez les informations souhaitées, puis enregistrez-le.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>For now, if you edit a value in the **[!UICONTROL Field mappings]** section then click outside of the field, your change does not display in the interface until you click the **[!UICONTROL Save]** button. This behaviour occurs only once, when the edit on **[!UICONTROL Field Mappings]** is the first edit on the page.
