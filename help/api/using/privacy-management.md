---
title: Gestion de la confidentialité
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gestion de la confidentialité {#privacy-management}

Les API de Campaign Standard fournissent des fonctionnalités qui permettent le traitement automatique des demandes liées à la réglementation de la confidentialité, comme le RDDC et l’ACCP.

Les actions que vous pouvez effectuer sont les suivantes :

* Créez une demande de confidentialité,
* Surveiller une demande de confidentialité,
* Récupérer un fichier de données de confidentialité,
* Gérez l’état d’exclusion d’un profil.

Le point de terminaison de l’API de confidentialité est **/privacy/privacyTool**. La description de la ressource PrivacyTool et les filtres associés sont disponibles dans les métadonnées de la ressource. Voir Mécanisme [de](../../api/using/metadata-mechanism.md)métadonnées.

L’exclusion de l’ACCP est gérée à l’aide de l’attribut de profil **ccpaOptOut** .

Pour plus d’informations sur la conformité à Adobe Campaign Standard et la confidentialité, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/kb/acs-privacy.html)dédiée.

## Création d’une demande de confidentialité {#creating-a-privacy-request}

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

## Surveillance d’une demande de confidentialité

Vous pouvez surveiller les informations sur une demande de confidentialité créée à l’aide d’une demande **GET** .

La description de la liste d’état est disponible dans la documentation [de gestion de la](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)confidentialité.

<br/>

***Exemple de requête***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>'
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Réponse à la demande GET.

```
{
            "PKey": "<PKEY>",
            "audit": "",
            "created": "2018-03-09 12:28:37.319Z",
            "desc": "",
            "gdprRequestData": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/gdprRequestData/"
            },
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
            "label": "Delete customer profile",
            "lastModified": "2018-03-09 12:39:21.232Z",
            "name": "GDPR6",
            "namespace": {
                "PKey": "<PKEY>",
                "title": "Email (defaultNamespace1)"
            },
            "namespaceName": "defaultNamespace1",
            "reconciliationValue": "customers@adobe.com",
            "regulation": "gdpr",
            "retryCount": 0,
            "status": "errorDataNotFound",
            "title": "Delete customer profile (GDPR6)",
            "type": "delete"
        }
```

## Récupération d’un fichier de données de confidentialité

>[!CAUTION]
>
>L’intégration du service [principal](https://adobe.io/apis/cloudplatform/gdpr.html) de confidentialité est la méthode à utiliser pour toutes les demandes d’accès et de suppression. À compter de la version 19.4, l’utilisation de l’API et de l’interface de campagne pour les demandes d’accès et de suppression est obsolète. Pour plus d'informations sur les fonctionnalités obsolètes et supprimées de Campaign Standard, reportez-vous à [cette page](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

Pour récupérer le fichier contenant toutes les informations associées à une valeur de rapprochement, procédez comme suit :

1. Exécutez une requête **POST** pour créer une nouvelle requête avec l’attribut **type="access"**, voir [Création d’une nouvelle requête](#creating-a-privacy-request)de confidentialité.

1. Effectuez une requête **GET** pour récupérer des informations sur la requête.

1. Récupérez le fichier de données en exécutant une requête **POST** sur l’URL **privacyRequestData** renvoyée, avec le nom interne de la requête de confidentialité dans la charge utile. Par exemple : {"name":"PT17"}.

<br/>

***Exemple de requête***

Créez une requête de confidentialité avec l’attribut type="access".

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
"type":"access"
}
```

<!-- + réponse -->

Effectuez une requête GET pour récupérer des informations sur la requête.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Elle renvoie l’attribut privacyRequestData avec une URL associée.

```
{
    ...
    "name": "PR2",
    "namespace": ...,
    "namespaceName": "defaultNamespace1",
    "privacyRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData/"
    },
    "reconciliationValue": "johndoe@mail.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "complete",
    "title": "EPR (PR2)",
    "type": "access"
    ...
},
```

Exécutez une requête POST sur l’URL privacyRequestData, avec le nom interne de la requête dans la charge utile.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
-d '{"name": "PR1"}'
```

Il renvoie le contenu du fichier.

```
"{data:<gdprRequestData _cs=\" ()\" id=\"8565163\" reconciliationValue=\"'customer@adobe.com'\">\n  <table name=\"nms:recipient\">\n    <rowId='8569152'\n\t\tlastName='customer'\n\t\tfirstName='customer'\n\t\tgender='1'\n\t\temail='customer@adobe.com'\n\t\tcreatedBy-id='8565162'\n\t\tmodifiedBy-id='8565162'\n\t\tlastModified='2018-03-15 13:54:28.708Z'\n\t\tcreated='2018-03-15 13:54:28.708Z'\n\t\tthumbnail='/nl/img/thumbnails/defaultProfil.png'\n\t\temailFormat='2'</row>\n  </table>\n  <table name=\"nms:broadLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\tid='8003'\n\t\taddress='customer@adobe.com'\n\t\tstatus='1'\n\t\tmsg-id='1194'\n\t\teventDate='2018-03-15 13:58:34.726Z'\n\t\tlastModified='2018-03-15 13:59:02.008Z'\n\t\tvariant='default'\n\t\tdelivery-id='8569153'\n\t\tpublicId='1'\n\t\tprofile-id='8569152'</row>\n  </table>\n  <table name=\"nms:trackingLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='-1178080215'\n\t\ttrackedDevice='pc'\n\t\tid='5000'\n\t\tlogDate='2018-03-15 14:00:51.650Z'\n\t\tsourceType='html'\n\t\tuserAgent='-1178080215'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='0'\n\t\ttrackedDevice=''\n\t\tid='6000'\n\t\tlogDate='2018-03-15 16:00:41.110Z'\n\t\tsourceType='html'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n  </table>\n</gdprRequestData>}"
```

## Gestion de l’exclusion de l’ACCP

L’état d’exclusion CCPA d’un profil peut être surveillé et géré à l’aide de l’attribut de profil **ccpaOptOut** et des valeurs "true" ou "false" :

`"ccpaOptOut": <value>`

* **true**:  interdit la vente de renseignements personnels.
* **false**: autorise la vente de renseignements personnels.

>[!CAUTION]
>
>L’attribut "Exclusion de l’ACCP" n’est disponible qu’à partir de la version 19.4. Pour les environnements 19.3, vous devez étendre la ressource Profils et ajouter un champ booléen. Ce champ sera ajouté à l’API avec le libellé choisi. Nous vous suggérons d'utiliser "Exclusion pour l'ACCP".
>
>For more on this, refer to the [Privacy management documentation](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

<br/>

***Exemples de requêtes***

* Exemple de requête GET pour récupérer l’état d’exclusion CCPA d’un profil.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Réponse à la demande GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Exemple de requête POST pour marquer un profil pour l’exclusion de l’ACCP.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   Réponse à la demande GET.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* Exemple de demande PATCH pour mettre à jour un profil pour l’exclusion de l’ACCP.

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   Réponse à la demande GET.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```
