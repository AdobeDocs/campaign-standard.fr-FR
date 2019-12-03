---
title: Points de fin
description: En savoir plus sur les points de fin des API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f251e4b5187aa09f65a5d8d6215f208a09cd9159

---


# Points de fin {#endpoints}

Points de fin disponibles pour l’API REST d’Adobe Campaign :

* **/profileAndServices**: interagir avec les champs prêts à l’emploi. Les champs étendus ne sont pas accessibles avec ce point de fin.
* **/profileAndServicesExt**: interagir avec les champs personnalisés ajoutés lors de l’extension de ressource personnalisée Profil ou Services. For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI&gt;**: interagir avec l’API des messages transactionnels (le nom du point de fin de l’API des messages transactionnels dépend de la configuration de votre instance). Voir à ce propos [cette section](../../api/using/managing-transactional-messages.md).
* **/workflow/exécution**: interagir avec les processus. Voir à ce propos [cette section](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagir avec l’API de confidentialité pour permettre le processus automatique des demandes de confidentialité. Voir à ce propos [cette section](../../api/using/creating-a-privacy-request.md).
* **/history**: récupérer l’historique marketing des profils. Pour plus d’informations sur les profils de clients intégrés dans Campaign, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)Campaign.

Par défaut, les ressources principales disponibles pour les API **profileAndServices** et **profileAndServicesExt** sont les suivantes :

* **/profile**: interagir avec les profils de la base de données Campaign. Pour ajouter des profils à un service, utilisez le point de terminaison **/service** . Pour plus d’informations sur les profils dans Campaign, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)Campaign.
* **/service**: gestion des services d’abonnement. Pour plus d’informations sur les services dans Campaign, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)Campaign.

>[!NOTE]
>
>Toutes les autres ressources qui ont été étendues ou créées sont disponibles via l’API **ProfileAndServicesExt** uniquement. Ils doivent être liés à la ressource **Profil** pour être accessibles.
