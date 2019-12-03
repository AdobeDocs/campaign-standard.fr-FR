---
title: Créer un profil
description: Découvrez comment créer des profils à l’aide d’API.
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


# Créer un profil {#creating-profiles}

La création de profils est effectuée avec une requête **POST** sur la ressource de profil.

>[!CAUTION]
>
>Si vous souhaitez associer une <b>orgUnit</b> au profil créé, vous devez étendre la ressource de profil à ce champ et, après la publication de l’extension, effectuer une requête POST sur le point de terminaison <b>ProfileAndServicesExt</b> .
>
>Pour plus d’informations sur l’extension de ressource du profil, reportez-vous à la documentation <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles"></a>Campaign.

<br/>

***Exemple de requête***

Exemple de requête POST pour créer un profil avec le message "john.doe@mail.com".

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Il renvoie le profil nouvellement créé, avec l’adresse électronique "john.doe@mail.com".

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
