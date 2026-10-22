---
title: Points d’entrée
description: En savoir plus sur les points d’entrée des API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 100%
---
# Points d’entrée {#endpoints}

Points d’entrée disponibles des API REST d’Adobe Campaign :

* **/profileAndServices** : permet d’interagir avec les champs d’usine. Les champs étendus ne sont pas accessibles par ce point d’entrée.
* **/profileAndServicesExt** : permet d’interagir avec les champs personnalisés ajoutés lors de l’extension des ressources personnalisées Profile ou Services. Pour plus d’informations sur les ressources personnalisées, reportez-vous à [cette section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>** : permet d’interagir avec l’API des messages transactionnels (le nom du point d’entrée de l’API des messages transactionnels dépend de la configuration de votre instance). Pour plus d’informations, consultez [cette section](../../api/using/managing-transactional-messages.md).
* **/workflow/exécution** : permet d’interagir avec les workflows. Pour plus d’informations, consultez [cette section](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool** : permet d’interagir avec l’API de confidentialité pour permettre le traitement automatique des demandes d’accès aux informations personnelles. Pour plus d’informations, consultez [cette section](../../api/using/creating-a-privacy-request.md).
* **/history** : permet de récupérer l’historique marketing des profils. Pour plus d’informations sur les profils de clients intégrés dans Campaign, reportez-vous à la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/audiences/using/integrated-customer-profile.html).

Par défaut, les principales ressources disponibles pour les API **profileAndServices** et **profileAndServicesExt** sont les suivantes :

* **/profile** : permet d’interagir avec les profils issus de la base de données Campaign. Pour ajouter des profils à un service, utilisez le point d’entrée **/service**. Pour plus d’informations sur les profils dans Campaign, reportez-vous à la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/audiences/using/about-profiles.html).
* **/service** : permet de gérer les services d’abonnement. Pour plus d’informations sur les services dans Campaign, reportez-vous à la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Toutes les autres ressources étendues ou créées sont exclusivement disponibles via l’API **ProfileAndServicesExt**. Elles doivent être liées à la ressource **Profile** pour être accessibles.
