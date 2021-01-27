---
solution: Campaign Standard
product: campaign
title: Création d’une demande d’accès à des informations personnelles
description: Découvrez comment créer une demande d’accès à des informations personnelles avec les API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 100%

---


# Création d’une demande d’accès à des informations personnelles {#creating-a-privacy-request}

>[!CAUTION]
>
>L’intégration de [Privacy Core Service](https://adobe.io/apis/cloudplatform/gdpr.html) est la méthode appropriée pour toutes les demandes d’accès et de suppression. Depuis la version 19.4, l’utilisation de l’API et de l’interface de Campaign pour les demandes d’accès et de suppression est obsolète. Pour plus d’informations sur les fonctionnalités de Campaign Standard obsolètes et supprimées, consultez [cette page](../../rn/using/deprecated-features.md).

Les demandes d’accès aux informations personnelles sont créées à l’aide d’une requête **POST**.

Avant de créer des requêtes, vous devez définir l’espace de noms que vous allez utiliser. Pour plus d’informations à ce sujet, consultez la [documentation relative à la gestion de la confidentialité](https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html#ManagingPrivacyRequests).

La payload doit contenir les paramètres suivants :

* **name** : nom interne unique
* **namespace** : nom d’espace de noms configuré dans l’interface de Campaign Standard
* **reconciliationValue** : valeur de réconciliation basée sur la clé de réconciliation définie dans l’espace de noms
* **label** : libellé de la requête
* **type** : type de requête. Les valeurs acceptées sont « access » ou « delete ».
* **regulation** : type de réglementation. Exemple : « GDPR », « ACCP ». Ce paramètre est obligatoire et disponible à partir de la version 19.4 de Campaign Standard. Si vous utilisez une version plus ancienne, vous n’avez pas besoin de l’ajouter à votre payload.

<br/>

***Exemple de requête***

Cette requête POST crée une demande d’accès à des informations personnelles basée sur une clé de réconciliation d’email définie dans l’espace de noms AMCDS2 :

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

Réponse à la requête POST.

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```
