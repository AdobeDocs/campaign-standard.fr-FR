---
title: Gestion des audiences d’Adobe Experience Platform
description: Découvrez comment gérer Adobe Experience Platform dans Campaign Standard.
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
source-git-commit: 2ef524d1d276abb1ff0a7149462452cafe8e5cd3

---


# Gestion des audiences d’Adobe Experience Platform {#about-audiences}

>[!IMPORTANT]
>
>Le service Destinations d’audience est actuellement en version bêta, qui peut faire l’objet de fréquentes mises à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta pour l&#39;Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez le service à la clientèle d’Adobe si vous souhaitez y accéder.

## Accès aux audiences d’Adobe Experience Platform

Pour accéder au créateur de segments d’Adobe Experience Platform, accédez à la carte **[!UICONTROL Audiences]**sur la page d’accueil de Campaign Standard (ou au lien**[!UICONTROL  Audiences]** dans l’en-tête), puis sélectionnez l’environnement **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Vous serez d’abord dirigé vers la page de liste des segments d’Adobe Experience Platform, où vous pourrez accéder aux segments existants d’Adobe Experience Platform pour les modifier davantage.

Une barre de recherche et un filtre sont disponibles pour vous aider à trouver le segment Adobe Experience Platform souhaité.

![](assets/aep_audiences_list.png)

## Création d’audiences Adobe Experience Platform

Pour créer une audience Adobe Experience Platform directement dans Campaign Standard, procédez comme suit :

1. Dans la page de liste des segments d’Adobe Experience Platform, cliquez sur le bouton **[!UICONTROL Nouveau public]**situé dans le coin droit.

   ![](assets/aep_audiences_creation_create.png)

1. Le créateur de segments unifiés doit désormais s’afficher dans votre espace de travail. Il vous permet de créer un segment à l’aide des données d’Adobe Experience Platform qui seront éventuellement utilisées pour créer votre audience.

1. Nommez le segment dans le volet de droite et entrez une description (facultatif).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Pour créer un segment, vous devez sélectionner une stratégie **de** fusion correspondant à votre objectif marketing pour ce segment.

   Dans le volet des paramètres, une stratégie de fusion par défaut de plateforme est sélectionnée. Pour plus d’informations sur les stratégies de fusion, reportez-vous à la section dédiée du guide [d’utilisation du créateur de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segments.

   ![](assets/aep_audiences_mergepolicy.png)

1. Définissez les règles qui identifieront les profils à récupérer dans votre audience.

   Pour ce faire, faites glisser les attributs et/ou événements de votre choix depuis le volet de gauche vers l’espace de travail, définissez les règles correspondantes, puis cliquez sur le bouton **[!UICONTROL Créer un segment]**pour enregistrer le segment (voir[Utilisation du créateur](../../audiences/using/aep-using-segment-builder.md)de segments unifié).

   ![](assets/aep_audiences_creation_query.png)

L’audience est maintenant prête à être activée. Vous pouvez l’utiliser comme cible pour vos campagnes (voir [Ciblage des audiences](../../automating/using/aep-targeting-audiences.md)de la plateforme Adobe Experience Platform).

## Modifier une audience

Pour modifier une audience, ouvrez-la et modifiez les règles selon vos besoins dans l’interface du créateur de segments unifiés (voir [Utilisation du créateur](../../audiences/using/aep-using-segment-builder.md)de segments unifiés).

Une fois les modifications effectuées, cliquez sur le bouton **[!UICONTROL Enregistrer le segment]**pour mettre à jour votre audience.

![](assets/aep_audiences_editing.png)
