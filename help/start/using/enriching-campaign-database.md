---
title: Enrichissement de la base de données
description: Découvrez les différentes méthodes pour enrichir la base de données.
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
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Enrichissement de la base de données{#enriching-the-database}

Campaign Standard propose plusieurs outils pour vous aider à développer votre base de données marketing. Cette section décrit les différentes méthodes que vous pouvez utiliser pour injecter des données dans Campaign et contient des références à la documentation dédiée.

## Import de données par le biais de workflows {#importing-data-through-workflows}

Les workflows permettent de collecter des données et de les importer dans la base de données Campaign via les activités de [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md).

Les informations génériques et les bonnes pratiques relatives à l'import de données par le biais de workflows sont présentées dans [cette section](../../automating/using/importing-data.md).

Vous pouvez en outre configurer des modèles pour importer des données. L'utilisation de modèles d'import est recommandée si vous devez importer régulièrement des fichiers avec la même structure.

Vous pouvez configurer deux types de modèles :

* **Modèles de workflow** : il s'agit de workflows préconfigurés que vous pouvez paramétrer une fois selon vos besoins. Vous pouvez ensuite les réutiliser chaque fois que vous souhaitez importer des données et mettre à jour la base de données.

   Vous trouverez un exemple de modèle de workflow pour importer des données dans [cette section](../../automating/using/importing-data.md#example--import-workflow-template).

* **Modèles de données d'import** : tout comme les modèles de workflow, il s'agit de modèles reposant sur des workflows qui sont configurés pour télécharger des fichiers afin de mettre à jour la base de données. Une fois configurés, ils sont mis à disposition des utilisateurs avec une vue simplifiée dans le menu **[!UICONTROL Profil &amp; audiences]** / **[!UICONTROL Imports]**.

   Pour plus d'informations sur les modèles de données d'import, reportez-vous à la [documentation dédiée](../../automating/using/importing-data-with-import-templates.md).

## Collecte de données à partir de landing pages {#collecting-data-from-landing-pages}

Les landing pages sont des formulaires web qui peuvent être utilisés pour collecter des données et créer ou mettre à jour des informations existantes dans votre base de données.

Le principe est le suivant :

* Créez et concevez votre landing page en ajoutant des champs d'entrée pour collecter des données (prénom, nom, email, etc.).
* Faites correspondre chaque champ d'entrée avec le champ correspondant de la base de données.
* Rendez la landing page disponible en ligne via un site web ou un lien direct dans un message.

Pour plus d'informations sur les landing pages, reportez-vous à la [documentation dédiée](../../channels/using/about-landing-pages.md).

## Synchronisation des profils à partir de Microsoft Dynamics 365

L'intégration de Campaign Standard avec Microsoft Dynamics 365 vous permet de transmettre les données de contact de Microsoft Dynamics 365 à la base de données Campaign.
Ces contacts sont alors visibles dans la liste Profils et peuvent être ciblés dans les campagnes marketing.

Pour plus d'informations sur cette intégration, reportez-vous à la [documentation dédiée](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).

>[!NOTE]
>
>Veuillez noter que le connecteur Campaign Standard-Microsoft Dynamics 365 est actuellement à disponibilité limitée et qu'il est soumis à plusieurs restrictions, détaillées dans la documentation.

## Import de données par le biais d'appels d'API

Les API Campaign Standard vous permettent d'effectuer des opérations pour mettre à jour la base de données comme créer, mettre à jour ou supprimer des profils ou des services.

Pour plus d'informations sur l'utilisation des API, reportez-vous à la [documentation dédiée](../../api/using/about-campaign-standard-apis.md).

>[!CAUTION]
>
>Avant d'effectuer une mise à jour ou une création en masse de profils via des appels d'API, vérifiez les limites d'échelle correspondant à votre contrat de licence. Voir à ce propos [cette page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
