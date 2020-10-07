---
title: Gestion du droit d’opposition du CCPA
description: Découvrez comment gérer le droit d’opposition du CCPA avec les API
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 100%

---


# Gestion du droit d’opposition du CCPA {#managing-ccpa-optout}

Il est possible de surveiller et gérer l’état du droit d’opposition (opt-out) à la vente d’informations personnelles du CCPA à l’aide de l’attribut de profil **ccpaOptOut** et des valeurs « true » ou « false » :

`"ccpaOptOut": <value>`

* **true** : interdit la vente d’informations personnelles.
* **false** : autorise la vente d’informations personnelles.

>[!CAUTION]
>
>L’attribut « Option d’Opt-out du CCPA » n’est disponible qu’à partir de la version 19.4. Pour les environnements 19.3, vous devez développer la ressource Profiles et ajouter un champ booléen. Ce champ sera ajouté à l’API avec le libellé choisi. Nous vous suggérons d’utiliser « Option d’Opt-out du CCPA ».
>
>Pour plus d’informations à ce sujet, consultez la [documentation relative à la gestion de la confidentialité](https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html#ccpa).

<br/>

***Exemples de requêtes***

* Exemple de requête GET pour récupérer dans un profil l’état du droit d’opposition du CCPA.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Réponse à la requête GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Exemple de requête POST pour indiquer le droit d’opposition du CCPA dans un profil.

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

   Réponse à la requête GET.

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

* Exemple de requête PATCH pour mettre à jour un profil concernant le droit d’opposition du CCPA.

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

   Réponse à la requête GET.

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
