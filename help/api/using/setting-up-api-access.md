---
title: Configuration de l’accès à l’API
description: Découvrez comment configurer l’accès aux API de Campaign Standard.
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


# Configuration de l’accès à l’API {#setting-up-api-access}

L’accès à l’API d’Adobe Campaign Standard est configuré par les étapes ci-dessous. Chacune de ces étapes est détaillée dans la documentation [d’E/S](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe.

>[!CAUTION]
>
>Pour gérer les certificats dans les E/S Adobe, assurez-vous que vous disposez des droits d’administrateur <b></b> système sur l’entreprise ou d’un compte <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">de</a> développeur dans la console d’administration.

1. **Vérifiez que vous disposez d’un certificat** numérique ou créez-en un si nécessaire. Les clés publique et privée fournies avec le certificat sont nécessaires dans les étapes suivantes.
1. **Créez une nouvelle intégration au service** Adobe Campaign dans les E/S Adobe et configurez-la. Vos informations d’identification seront alors générées (clé API, secret client...).
1. **Créez un jeton Web JSON (JWT)** à partir des informations d’identification précédemment générées et signez-le avec votre clé privée. Le JWT code toutes les informations d’identité et de sécurité dont Adobe a besoin pour vérifier votre identité et vous accorder l’accès à l’API.
1. **Echangez votre JWT pour un jeton** d’accès via une requête POST. Ce jeton d’accès devra être utilisé dans chaque en-tête de vos demandes d’API.

Pour établir une session d’API d’E/S Adobe de service à service sécurisé, chaque demande adressée à un service Adobe doit inclure dans l’en-tête d’autorisation les informations ci-dessous.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZATION&gt;**: Il s’agit de votre ID d’ORGANISATION personnel, un ID d’ORGANISATION est fourni par Adobe pour chacune de vos instances :

   * &lt;ORGANISATION&gt; : votre instance de production,
   * &lt;ORGANIZATION-mkt-stage&gt;: votre instance de scène.
   Pour obtenir votre valeur d’ID d’ORGANISATION, contactez votre administrateur ou votre contact technique Adobe. Vous pouvez également le récupérer dans les E/S Adobe lors de la création d’une nouvelle intégration, dans la liste des licences (voir la documentation <a href="https://www.adobe.io/authentication.html">sur les E/S</a>Adobe).

* **&lt;ACCESS_TOKEN&gt;**: Votre jeton d’accès personnel, récupéré lors de l’échange de votre jeton Web JSON par le biais d’une requête POST.

* **&lt;API_KEY&gt;**: votre clé d'API personnelle. Il est fourni dans les E/S Adobe après la création d’une nouvelle intégration à Adobe Campaign Service.

   ![texte alt](assets/tenant.png)
