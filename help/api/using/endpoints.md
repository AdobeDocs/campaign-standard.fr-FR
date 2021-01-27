---
solution: Campaign Standard
product: campaign
title: Points d’entrée
description: En savoir plus sur les points d’entrée des API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 100%

---


# Points d’entrée {#endpoints}

Points d’entrée disponibles des API REST d’Adobe Campaign :

* **/profileAndServices** : permet d’interagir avec les champs d’usine. Les champs étendus ne sont pas accessibles par ce point d’entrée.
* **/profileAndServicesExt** : permet d’interagir avec les champs personnalisés ajoutés lors de l’extension des ressources personnalisées Profile ou Services. Pour plus d’informations sur les ressources personnalisées, reportez-vous à [cette section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>** : permet d’interagir avec l’API des messages transactionnels (le nom du point d’entrée de l’API des messages transactionnels dépend de la configuration de votre instance). Voir à ce propos [cette section](../../api/using/managing-transactional-messages.md).
* **/workflow/exécution** : permet d’interagir avec les workflows. Voir à ce propos [cette section](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool** : permet d’interagir avec l’API de confidentialité pour permettre le traitement automatique des demandes d’accès aux informations personnelles. Voir à ce propos [cette section](../../api/using/creating-a-privacy-request.md).
* **/history** : permet de récupérer l’historique marketing des profils. Pour plus d’informations sur les profils de clients intégrés dans Campaign, reportez-vous à la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/audiences/using/integrated-customer-profile.html).

Par défaut, les principales ressources disponibles pour les API **profileAndServices** et **profileAndServicesExt** sont les suivantes :

* **/profile** : permet d’interagir avec les profils issus de la base de données Campaign. Pour ajouter des profils à un service, utilisez le point d’entrée **/service**. Pour plus d’informations sur les profils dans Campaign, reportez-vous à la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/audiences/using/about-profiles.html).
* **/service** : permet de gérer les services d’abonnement. Pour plus d’informations sur les services dans Campaign, reportez-vous à la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Toutes les autres ressources étendues ou créées sont exclusivement disponibles via l’API **ProfileAndServicesExt**. Elles doivent être liées à la ressource **Profile** pour être accessibles.
