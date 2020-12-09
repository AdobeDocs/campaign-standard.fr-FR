---
solution: Campaign Standard
product: campaign
title: Gestion du droit d’opposition du CCPA
description: Découvrez comment gérer le droit d’opposition du CCPA avec les API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '148'
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
>Pour plus d&#39;informations à ce sujet, consultez la [documentation sur les demandes d&#39;accès à des informations personnelles](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

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
