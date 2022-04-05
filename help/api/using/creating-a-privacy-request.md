---
title: Création d’une demande d’accès à des informations personnelles
description: Découvrez comment créer une demande d’accès à des informations personnelles avec les API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 97%

---

# Création d&#39;une demande d&#39;accès à des informations personnelles {#creating-a-privacy-request}

>[!CAUTION]
>
>L’intégration [Privacy Core Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service) est la méthode appropriée pour toutes les demandes d’accès et de suppression <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

Les demandes d’accès aux informations personnelles sont créées à l’aide d’une requête **POST**.

Avant de créer des requêtes, vous devez définir l’espace de noms que vous allez utiliser. Pour plus d’informations à ce sujet, consultez la [documentation relative à la gestion de la confidentialité](../../start/using/privacy-requests.md).

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
