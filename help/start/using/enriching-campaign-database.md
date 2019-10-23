---
title: Enrichissement de la base de données
seo-title: Enrichissement de la base de données
description: Enrichissement de la base de données
seo-description: Découvrez les différentes méthodes pour enrichir la base de données.
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2e114c4a9a6d6189c192ba72140a0e0b55f325ed

---


# Enrichissement de la base de données{#enriching-the-database}

Campaign Standard propose plusieurs outils pour vous aider à développer votre base de données marketing. Cette section décrit les différentes méthodes que vous pouvez utiliser pour injecter des données dans Campaign, avec des références aux documentations dédiées.

## Importation de données par le biais de processus {#importing-data-through-workflows}

Les processus vous permettent de collecter des données et de les importer dans la base de données Campaign par le biais d’activités de gestion [**[!UICONTROL des]**](../../automating/using/about-data-management-activities.md) données.

Les informations génériques et les bonnes pratiques relatives à l’importation de données par le biais de processus sont présentées dans [cette section](../../automating/using/importing-data.md).

De plus, vous pouvez configurer des modèles pour importer des données. L’utilisation de modèles d’importation est recommandée si vous devez importer régulièrement des fichiers avec la même structure.

Vous pouvez configurer deux types de modèles :

* **Modèles** de processus : il s’agit de processus préconfigurés que vous pouvez configurer une fois en fonction de vos besoins, puis réutiliser chaque fois que vous souhaitez importer des données et mettre à jour la base de données.

   Vous trouverez un exemple de modèle de flux de travail pour importer des données dans [cette section](../../automating/using/importing-data.md#example--import-workflow-template).

* **Importer des modèles** de données : tout comme les modèles de processus, il s’agit de modèles basés sur des processus, configurés pour télécharger des fichiers afin de mettre à jour la base de données. Une fois configurés, ils sont accessibles aux utilisateurs avec une vue simplifiée sous le menu **[!UICONTROL Profil et audiences]** / **[!UICONTROL Importation]** .

   Pour plus d’informations sur les modèles de données d’importation, reportez-vous à la documentation [](../../automating/using/importing-data-with-import-templates.md)dédiée.

## Collecte de données à partir de pages d'entrée {#collecting-data-from-landing-pages}

Les pages d’entrée sont des formulaires Web qui peuvent être utilisés pour collecter des données et créer ou mettre à jour des informations existantes dans votre base de données.

Le principe est le suivant :

* Créez et concevez votre page d'entrée en ajoutant des champs d'entrée pour collecter les données (prénom, nom, courriel, etc.).
* Mappez chaque champ d’entrée avec le champ correspondant de la base de données.
* Rendre la page d'entrée disponible en ligne par l'intermédiaire d'un site Web ou d'un lien direct vers un message.

For more on landing pages, refer to the [dedicated documentation](../../channels/using/about-landing-pages.md).

## Synchronisation des profils à partir de Microsoft Dynamics 365

L'intégration de Campaign Standard avec Microsoft Dynamics 365 vous permet de transmettre les données de contact de Microsoft Dynamics 365 à la base de données Campaign.
Ces contacts sont alors visibles dans la liste Profils et peuvent être ciblés dans les campagnes marketing.

For more on this integration, refer to the [dedicated documentation](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).

>[!NOTE]
>
>Veuillez noter que le connecteur Campaign Standard-Microsoft Dynamics 365 est actuellement à disponibilité limitée et qu'il est soumis à plusieurs restrictions, détaillées dans la documentation.

## Importation de données par le biais d’appels d’API

Les API de Campaign Standard vous permettent d’effectuer des opérations de mise à jour de la base de données, comme la création, la mise à jour ou la suppression de profils ou de services.

For more on how to use the APIs, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

>[!CAUTION]
>
>Avant d'effectuer la création en masse de profils ou la mise à jour via des appels d'API, veuillez vérifier les limites d'échelle correspondant à votre contrat de licence. Voir à ce propos [cette page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
