---
title: Utilisation du créateur de segment unifié
description: Découvrez comment utiliser le créateur de segments unifiés pour créer   de.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fcb6a145b19b68865babba659bf0bfb7623397c8

---


# Utilisation du créateur de segment unifié {#using-the-unified-segment-builder}

>[!IMPORTANT]
>
>Le service Audience Destinations est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.

Le créateur de segments unifiés vous permet de créer   en définissant des règles basées sur les données provenant du service [de  de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)unifié.

Cette section présente les concepts globaux lors de la création d’un segment. Pour plus d’informations sur le créateur de segments unifiés lui-même, consultez le guide [d’utilisation du créateur de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segments.

L’interface du créateur de segments unifiés se compose comme suit :

* Le volet de gauche fournit tous les attributs, les  de et les  de disponibles pour créer le segment en faisant glisser les champs de votre choix dans l’espace de travail du créateur de segments.
* La zone centrale fournit un espace de travail pour créer le segment en définissant et en combinant des règles à partir des champs disponibles.
* L’en-tête et le volet de droite affichent les propriétés du segment (nom, description et estimation des  qualifiés du segment).

![](assets/aep_audiences_interface.png)

## Création d’un segment

Pour créer un segment, procédez comme suit :

Le créateur de segments unifiés doit désormais s’afficher dans votre espace de travail. Il vous permet de créer un segment à l’aide des données d’Adobe Experience Platform qui seront éventuellement utilisées pour créer votre  de .

1. Nommez le segment, puis entrez une description (facultatif).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Assurez-vous que la stratégie de fusion souhaitée est sélectionnée dans le volet des paramètres.

   Pour plus d’informations sur les stratégies de fusion, reportez-vous à la section dédiée du guide [d’utilisation du créateur de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segments.

   ![](assets/aep_audiences_mergepolicy.png)

1. Recherchez les champs de votre choix dans le volet de gauche, puis faites-les glisser dans l’espace de travail central.

   ![](assets/aep_audiences_dragfield.png)

1. Configurez les règles correspondant aux champs déplacés.

   ![](assets/aep_audiences_configure_rules.png)

1. Cliquez sur le **[!UICONTROL Create segment]** bouton.

## Recherche des champs appropriés pour un segment

Le volet de gauche  tous les attributs, les  de et lesde  disponibles pour la création de règles.

Les champs répertoriés sont des attributs capturés par votre  de et rendus disponibles via le système [de modèle de données d’](https://www.adobe.io/apis/experienceplatform/home/xdm.html)expérience (XDM).

Les champs sont organisés en onglets :

* **[!UICONTROL Attributes]**: Attributs  existants pouvant provenir de votre base de données  et/ou de la plateforme Adobe Experience Platform. Ils font référence à des informations statiques jointes à un  (p. ex., adresse électronique, pays de résidence, statut  du de fidélité, etc.).

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:   qui identifient les consommateurs qui ont eu une certaine interaction avec votre, les points de contact de vos clients, comme &quot;quiconque a commandé deux fois en deux semaines&quot;. Il peut être diffusé en continu à partir d’Adobe Analytics ou directement assimilé dans Adobe Experience Platform à l’aide d’outils ETL tiers.

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**La segmentation** multientité vous permet d’étendre les données  avec des données supplémentaires basées sur des produits, des magasins ou d’autres classes  non. Une fois connecté, les données d’autres classes deviennent disponibles comme si elles étaient natives du  .
>
>Consultez à ce sujet la [documentation dédiée](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/tutorials/segmentation/multi_entity_segmentation.md).

Par défaut, le créateur de segments unifiés affiche les champs dans lesquels des données sont déjà présentes. Pour afficher le  complet du, y compris les champs pour lesquels les données ne sont pas présentes, activez l’ **[!UICONTROL Show full XDM schema]** option à partir des paramètres.

![](assets/aep_audiences_populatedfields.png)

Le symbole à la fin de chaque champ fournit des informations supplémentaires sur l’attribut et sur la manière de l’utiliser.

![](assets/aep_audiences_isymbol.png)

## Définition de règles pour un segment

>[!NOTE]
>
>La section ci-dessous fournit des informations générales sur la définition des règles. Pour plus d’informations, reportez-vous au guide [d’utilisation du créateur de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segments.

Pour créer une règle, procédez comme suit :

1. Recherchez le champ du volet de gauche qui reflète les attributs ou le  sur lequel la règle sera basée.

1. Faites glisser le champ sur l’espace de travail central, puis configurez-le selon la définition de segment souhaitée. Pour ce faire, plusieurs fonctions de chaîne et de date/heure sont disponibles.

   Dans l&#39;exemple ci-dessous, la règle tous les  avec un sexe égal à &quot;Homme&quot;.

   ![](assets/aep_audiences_malegender.png)

   La population estimée correspondant au segment est automatiquement recalculée dans la **[!UICONTROL Segment Properties]** section.

1. Le **[!UICONTROL View Profiles]** bouton vous donne un  des 20 premiers enregistrements correspondant à la règle, ce qui vous permet de valider rapidement le segment.

   ![](assets/aep_audiences_samplepreview.png)

   Vous pouvez ajouter autant de règles supplémentaires que vous le souhaitez, afin de  le approprié .

   Lors de l’ajout d’une règle à un , elle sera ajoutée à toutes les règles existantes avec l’opérateur logique ET. Si nécessaire, cliquez sur l’opérateur logique pour le modifier.

   ![](assets/aep_audiences_andoperator.png)

Une fois liées, les deux règles forment un .

## Comparaison de champs

Le créateur de segments unifiés vous permet de comparer deux champs pour définir une règle. Par exemple, les femmes dont l’adresse du domicile se trouve dans un code postal différent de leur adresse professionnelle.

Pour ce faire, procédez comme suit :

1. Faites glisser le premier champ à comparer (par exemple, le code postal de l’adresse d’accueil) sur l’espace de travail central.

   ![](assets/aep_audiences_comparing_1.png)

1. Sélectionnez le deuxième champ (par exemple, le code postal de l&#39;adresse de travail) qui sera comparé au premier champ.

   Faites-le glisser sur l’espace de travail central, dans le même que le premier champ, dans la **[!UICONTROL Drop here to compare operands]** zone.

   ![](assets/aep_audiences_comparing_2.png)

1. Configurez l’opérateur entre les deux champs selon vos besoins. Dans cet exemple, nous voulons que notre segment  le  avec l’adresse de domicile différente de l’adresse de travail.

   ![](assets/aep_audiences_comparing_3.png)

La règle est maintenant configurée et prête à être activée en tant que  .
