---
solution: Campaign Standard
product: campaign
title: A propos de la gestion de la confidentialité
description: En savoir plus sur la gestion de la confidentialité avec les API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 100%

---


# A propos de la gestion de la confidentialité {#about-privacy-management}

Les API de Campaign Standard fournissent des fonctionnalités qui permettent le traitement automatique des demandes liées à la réglementation de la confidentialité, comme le RGPD et le CCPA.

Les actions que vous pouvez effectuer sont les suivantes :

* créer une demande d’accès à des informations personnelles,
* suivre une demande d’accès à des informations personnelles,
* récupérer un fichier de données de confidentialité,
* gérer l’état du droit d’opposition du CCPA dans un profil.

Le point d’entrée de l’API de confidentialité est **/privacy/privacyTool**. La description de la ressource PrivacyTool et les filtres associés sont disponibles dans les métadonnées de la ressource. Voir la section [Mécanisme des métadonnées](../../api/using/metadata-mechanism.md).

Le droit d’opposition du CCPA est géré à l’aide de l’attribut de profil **ccpaOptOut**.

Pour plus d’informations sur Adobe Campaign Standard et la conformité en matière de confidentialité, reportez-vous à la [documentation dédiée](https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html).
