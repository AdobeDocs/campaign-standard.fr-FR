---
title: A propos de la gestion de la confidentialité
description: En savoir plus sur la gestion de la confidentialité avec les API
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# A propos de la gestion de la confidentialité {#about-privacy-management}

Les API de Campaign Standard fournissent des fonctionnalités qui permettent le traitement automatique des demandes liées à la réglementation de la confidentialité, comme le RDDC et l’ACCP.

Les actions que vous pouvez effectuer sont les suivantes :

* Créez une demande de confidentialité,
* Surveiller une demande de confidentialité,
* Récupérer un fichier de données de confidentialité,
* Gérez l’état d’exclusion d’un profil.

Le point de terminaison de l’API de confidentialité est **/privacy/privacyTool**. La description de la ressource PrivacyTool et les filtres associés sont disponibles dans les métadonnées de la ressource. Voir Mécanisme [de](../../api/using/metadata-mechanism.md)métadonnées.

L’exclusion de l’ACCP est gérée à l’aide de l’attribut de profil **ccpaOptOut** .

Pour plus d’informations sur la conformité à Adobe Campaign Standard et la confidentialité, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/kb/acs-privacy.html)dédiée.
