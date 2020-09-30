---
title: Configuration de l’accès aux API
description: Découvrez comment configurer l’accès aux API de Campaign Standard.
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
source-git-commit: b0e69280912ee70e6f53efd24782474395c57f74
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Configuration de l’accès aux API {#setting-up-api-access}

Pour configurer l’accès aux API d’Adobe Campaign Standard, procédez comme suit. Chacune de ces étapes est détaillée dans la documentation [Adobe IO](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Pour gérer les certificats dans Adobe IO, assurez-vous de disposer des droits d’<b>administrateur système</b> sur l’organisation ou d’un [compte de développeur](https://helpx.adobe.com/fr/enterprise/using/manage-developers.html) dans la console d’administration.</a>

1. **Vérifiez que vous disposez d’un certificat numérique**, ou créez-en un si nécessaire. Les clés publique et privée fournies avec le certificat sont nécessaires dans les étapes suivantes.
1. **Créez une nouvelle intégration avec Adobe Campaign Service** dans Adobe IO et configurez-la. Vos informations d’identification seront alors générées (clé d’API, secret client...).
1. **Créez un jeton Web JSON (JWT)** à partir des informations d’identification précédemment générées, et signez-le avec votre clé privée. Le jeton JWT code toutes les informations d’identité et de sécurité dont Adobe a besoin pour vérifier votre identité et vous accorder l’accès à l’API.
1. **Échangez votre JWT pour un jeton d’accès** via une requête POST. Ce jeton d’accès devra être utilisé dans chaque en-tête de vos requêtes d’API.

Pour établir une session d’API Adobe I/O de service à service sécurisée, chaque requête adressée à un service Adobe doit inclure les informations ci-dessous dans l’en-tête d’autorisation.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZATION>** : il s’agit de votre ORGANIZATION ID personnel, fourni par Adobe pour chacune de vos instances :

   * &lt;ORGANIZATION> : votre instance de production,
   * &lt;ORGANIZATION-mkt-stage> : votre instance d’évaluation.

   Pour obtenir votre valeur ORGANIZATION ID, contactez votre administrateur ou votre contact technique Adobe. Vous pouvez également la récupérer dans Adobe I/O lors de la création d’une nouvelle intégration, dans la liste des licences (voir la <a href="https://www.adobe.io/authentication.html">documentation Adobe IO</a>).

* **&lt;ACCESS_TOKEN>** : votre jeton d’accès personnel, récupéré lors de l’échange de votre jeton Web JSON par le biais d’une requête POST.

* **&lt;API_KEY>** : votre clé d’API personnelle. Elle est fournie dans Adobe I/O après la création d’une nouvelle intégration avec Adobe Campaign Service.

   ![texte alternatif](assets/tenant.png)

## Résolution des problèmes

Lors de l’intégration d’Adobe IO, si l’erreur suivante s’affiche :

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Pour vérifier si le paramètre CNAME est correctement créé, contactez votre administrateur ou votre contact technique Adobe.