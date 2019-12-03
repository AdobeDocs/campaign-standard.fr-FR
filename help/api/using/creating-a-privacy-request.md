---
title: Création d’une demande de confidentialité
description: Découvrez comment créer une requête de confidentialité avec des API
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


# Création d’une demande de confidentialité {#creating-a-privacy-request}

>[!CAUTION]
>
>L’intégration du service [principal](https://adobe.io/apis/cloudplatform/gdpr.html) de confidentialité est la méthode à utiliser pour toutes les demandes d’accès et de suppression. À compter de la version 19.4, l’utilisation de l’API et de l’interface de campagne pour les demandes d’accès et de suppression est obsolète. Pour plus d'informations sur les fonctionnalités obsolètes et supprimées de Campaign Standard, reportez-vous à [cette page](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

Les requêtes de confidentialité sont créées à l’aide d’une requête **POST** .

Avant de créer des requêtes, vous devez définir l’espace de noms que vous utiliserez. Pour en savoir plus, consultez la documentation [sur la gestion de la](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)confidentialité.

La charge utile doit contenir les paramètres suivants :

* **name**: un nom interne unique
* **namespace**: nom d’espace de noms configuré dans l’interface de Campaign Standard
* **réconciliationValue**: la valeur de rapprochement basée sur la clé de rapprochement définie dans l'espace de noms
* **libellé**: l’étiquette de demande
* **type**: type de requête. Les valeurs acceptées sont "access" ou "delete".
* **règlement**: le type de réglementation. Exemple : "GDPR", "ACCP". Ce paramètre est obligatoire et disponible à partir de la version 19.4 de Campaign Standard. Si vous utilisez une version plus ancienne, vous n’avez pas besoin de l’ajouter à votre charge utile.

<br/>

***Exemple de requête***

Cette requête POST crée une requête de confidentialité basée sur une clé de rapprochement de courrier électronique définie dans l’espace de noms AMCDS2 :

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

Réponse à la demande POST.

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
