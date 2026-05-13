---
title: Enrichissement de la base de données
description: Découvrez les différentes méthodes pour enrichir la base de données.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
TQID: https://experienceleague.adobe.com/LROFX17EE6zvJRbH4P--NjtiJLwanqeudAKzwnQj0BI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 460
ht-degree: 100%

---

# Enrichissement de la base de données{#enriching-the-database}

Campaign Standard propose plusieurs outils pour vous aider à développer votre base de données marketing. Cette section décrit les différentes méthodes que vous pouvez utiliser pour injecter des données dans Campaign et contient des références à la documentation dédiée.

## Import de données par le biais de workflows {#importing-data-through-workflows}

Les workflows permettent de collecter des données et de les importer dans la base de données Campaign via les activités de [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md).

Les informations génériques et les bonnes pratiques relatives à l&#39;import de données par le biais de workflows sont présentées dans [cette section](../../automating/using/about-data-import-and-export.md).

Vous pouvez en outre configurer des modèles pour importer des données. L&#39;utilisation de modèles d&#39;import est recommandée si vous devez importer régulièrement des fichiers avec la même structure.

Vous pouvez configurer deux types de modèles :

* **Modèles de workflow** : il s&#39;agit de workflows préconfigurés que vous pouvez paramétrer une fois selon vos besoins. Vous pouvez ensuite les réutiliser chaque fois que vous souhaitez importer des données et mettre à jour la base de données.

  Vous trouverez un exemple de modèle de workflow pour importer des données dans [cette section](../../automating/using/creating-import-workflow-templates.md).

* **Modèles de données d&#39;import** : tout comme les modèles de workflow, il s&#39;agit de modèles reposant sur des workflows qui sont configurés pour télécharger des fichiers afin de mettre à jour la base de données. Une fois configurés, ils sont mis à disposition des utilisateurs avec une vue simplifiée dans le menu **[!UICONTROL Profil &amp; audiences]** / **[!UICONTROL Imports]**.

  Pour plus d&#39;informations sur les modèles de données d&#39;import, reportez-vous à la [documentation dédiée](../../automating/using/importing-data-with-import-templates.md).

## Collecte de données à partir de landing pages {#collecting-data-from-landing-pages}

Les landing pages sont des formulaires web qui peuvent être utilisés pour collecter des données et créer ou mettre à jour des informations existantes dans votre base de données.

Le principe est le suivant :

* Créez et concevez votre landing page en ajoutant des champs d&#39;entrée pour collecter des données (prénom, nom, email, etc.).
* Faites correspondre chaque champ d&#39;entrée avec le champ correspondant de la base de données.
* Rendez la landing page disponible en ligne via un site web ou un lien direct dans un message.

Pour plus d&#39;informations sur les landing pages, reportez-vous à la [documentation dédiée](../../channels/using/getting-started-with-landing-pages.md).

## Synchronisation des profils à partir de Microsoft Dynamics 365

L&#39;intégration de Campaign Standard avec Microsoft Dynamics 365 vous permet de transmettre les données de contact de Microsoft Dynamics 365 à la base de données Campaign.
Ces contacts sont alors visibles dans la liste Profils et peuvent être ciblés dans les campagnes marketing.

Pour plus d&#39;informations sur cette intégration, reportez-vous à la [documentation dédiée](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Veuillez noter que le connecteur Campaign Standard-Microsoft Dynamics 365 est actuellement à disponibilité limitée et qu&#39;il est soumis à plusieurs restrictions, détaillées dans la documentation.

## Import de données par le biais d&#39;appels d&#39;API

Les API Campaign Standard vous permettent d&#39;effectuer des opérations pour mettre à jour la base de données comme créer, mettre à jour ou supprimer des profils ou des services.

Pour plus d&#39;informations sur l&#39;utilisation des API, reportez-vous à la [documentation dédiée](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Avant d&#39;effectuer une mise à jour ou une création en masse de profils via des appels d&#39;API, vérifiez les limites d&#39;échelle correspondant à votre contrat de licence. Pour plus d’informations, consultez [cette page](https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html#RessourcesdinfrastructureinformatiqueparniveauxdeProfilsactifs).
