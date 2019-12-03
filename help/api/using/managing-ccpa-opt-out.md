---
title: Gestion de l’exclusion de l’ACCP
description: Découvrez comment gérer l’exclusion CCPA avec les API
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


# Gestion de l’exclusion de l’ACCP {#managing-ccpa-optout}

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
