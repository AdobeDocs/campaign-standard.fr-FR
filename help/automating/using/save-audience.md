---
solution: Campaign Standard
product: campaign
title: Sauvegarde d'audience
description: L'activité Sauvegarde d'audience permet de mettre à jour une audience existante ou de créer une nouvelle audience à partir de la population calculée en amont dans un workflow.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: saveAudience,main
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '865'
ht-degree: 100%

---


# Sauvegarde d&#39;audience{#save-audience}

## Description {#description}

![](assets/save_audience.png)

L&#39;activité **[!UICONTROL Sauvegarde d&#39;audience]** permet de mettre à jour une audience existante ou de créer une nouvelle audience à partir de la population calculée en amont dans un workflow. Les audiences créées ou pouvant être mises à jour à partir de cette activité sont de type **Liste** ou **Fichier**. Elles sont ajoutées à la liste des audiences de l&#39;application, disponible via le menu **[!UICONTROL Audiences]**.

>[!NOTE]
>
>Si l&#39;audience créée par le biais de l&#39;activité **[!UICONTROL Sauvegarde d&#39;audience]** a été enrichie de données additionnelles, vous ne pourrez pas utiliser ces données pour personnaliser une diffusion autonome. Elles ne peuvent être utilisées qu’à partir d’une diffusion exécutée dans un workflow.

Cette activité permet également d&#39;exporter des profils en tant qu&#39;audience/segment Adobe Experience Cloud. Cela permet par la suite de pouvoir exploiter ces audiences dans d&#39;autres solutions Adobe Experience Cloud. Pour plus d&#39;informations sur les audiences partagées, voir [Utilisation de Campaign et People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Sauvegarde d&#39;audience]** est essentiellement utilisée afin de conserver des groupes de population calculés dans le même workflow, en les convertissant en audiences réutilisables.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Sauvegarde d&#39;audience]** dans votre workflow.
1. Connectez-la à la suite d&#39;autres activités de ciblage telles qu&#39;une requête, une intersection, une union ou une exclusion.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Sélectionnez l&#39;action que vous souhaitez réaliser :

   * **[!UICONTROL Mettre à jour une audience existante]** : sélectionnez une audience existante et choisissez le type de mise à jour :

      * **[!UICONTROL Remplacer le contenu de l&#39;audience par les nouvelles données]** : l&#39;intégralité du contenu de l&#39;audience est remplacée. Les anciennes données sont perdues. Seules les données issues de la transition entrante de l&#39;activité de sauvegarde d&#39;audience sont conservées.
      * **[!UICONTROL Compléter l&#39;audience avec les nouvelles données]** : les anciennes données de l&#39;audience sont conservées et sont complétées avec celles issues de la transition entrante de l&#39;activité de sauvegarde d&#39;audience.
   * **[!UICONTROL Créer et mettre à jour une audience]** : saisissez le nom d&#39;une audience et choisissez le type de mise à jour. L&#39;audience est créée si elle n&#39;existe pas. Si elle existe déjà, elle est mise à jour selon le mode choisi :

      * **[!UICONTROL Remplacer le contenu de l&#39;audience par les nouvelles données]** : l&#39;intégralité du contenu de l&#39;audience est remplacée. Les anciennes données sont perdues. Seules les données issues de la transition entrante de l&#39;activité de sauvegarde d&#39;audience sont conservées.

         Attention, cette option écrase le type et la dimension de ciblage de l&#39;audience mise à jour.

      * **[!UICONTROL Compléter l&#39;audience avec les nouvelles données]** : les anciennes données de l&#39;audience sont conservées et sont complétées avec celles issues de la transition entrante de l&#39;activité de sauvegarde d&#39;audience.

         Attention, cette option provoque une erreur si le type ou la dimension de ciblage de l&#39;audience mise à jour ne sont pas compatibles avec le paramétrage actuel du workflow. Par exemple, il est impossible de compléter une audience de type fichier avec des profils issus d&#39;une requête.
   * **[!UICONTROL Créer une nouvelle audience]** : renseignez le nom de l&#39;audience à créer. L&#39;heure et la date de création de l&#39;audience seront automatiquement ajoutées au nom de l&#39;audience. Cela permet à l&#39;audience d&#39;être unique à chaque exécution du workflow.
   * **[!UICONTROL Partager dans Adobe Experience Cloud]** : si vous avez ciblé des profils et que vous souhaitez exporter votre audience vers Adobe Experience Cloud, sélectionnez cette option, puis sélectionnez une audience partagée existante ou créez une audience.

      Sélectionnez également une **[!UICONTROL Source de données partagées]** qui correspond à la ressource des données contenues dans l&#39;audience, afin que les données soient correctement réconciliées dans Adobe Experience Cloud.

      En utilisant cette option, l&#39;audience partagée n&#39;est pas ajoutée à la liste des audiences d&#39;Adobe Campaign, disponible via le menu **[!UICONTROL Audiences]**.

      >[!NOTE]
      >
      >Cette option n&#39;est disponible que si la fonctionnalité de partage d&#39;audiences avec Adobe Experience Cloud a été paramétrée par votre administrateur. Pour plus d&#39;informations, voir [Utilisation de Campaign et People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   Le type des audiences sauvegardées ou des audiences disponibles lors d&#39;une mise à jour dépend des activités placées en amont dans le workflow.

   Si la dimension de ciblage de l&#39;audience est inconnue au moment de la sauvegarde (par exemple si elle est issue d&#39;un import de fichier), l&#39;audience créée ou mise à jour est de type **[!UICONTROL Fichier]**.

   Si la dimension de ciblage de l&#39;audience sauvegardée est déjà définie au moment de la sauvegarde (par exemple si elle est issue d&#39;un ciblage, après une requête, etc.), l&#39;audience créée ou mise à jour est de type **[!UICONTROL Liste]**.

   Le contenu de l&#39;audience sauvegardée est ensuite disponible dans la vue détaillée de l&#39;audience, accessible depuis le menu **[!UICONTROL Audiences]**. Les colonnes disponibles depuis cette vue correspondent aux colonnes de la transition entrante de l&#39;activité de sauvegarde de l&#39;audience du workflow. Par exemple : les colonnes du fichier importé, les données additionnelles ajoutées depuis une requête.

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Exemple {#example}

Le workflow défini dans cet exemple illustre la mise à jour régulière d&#39;une audience à partir d&#39;un ciblage :

* Il est exécuté automatiquement une fois par mois grâce à un **[!UICONTROL Planificateur]**.
* Une **[!UICONTROL Requête]** permet de récupérer tous les profils abonnés aux différents services disponibles de l&#39;application.
* La **[!UICONTROL Sauvegarde d&#39;audience]** permet de mettre à jour l&#39;audience spécifiée en y supprimant les profils s&#39;étant désabonnés des services depuis la dernière exécution du workflow et en y ajoutant les nouveaux abonnés.

![](assets/save_audience_example_1.png)

L&#39;activité **[!UICONTROL Sauvegarde d&#39;audience]** est paramétrée comme suit :

![](assets/save_audience_example_2.png)

