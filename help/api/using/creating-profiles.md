---
solution: Campaign Standard
product: campaign
title: Créer un profil
description: Découvrez comment créer des profils à l’aide des API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
translation-type: ht
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: ht
source-wordcount: '105'
ht-degree: 100%

---

# Créer un profil {#creating-profiles}

La création de profils est effectuée avec une requête **POST** sur la ressource de profil.

>[!CAUTION]
>
>Si vous souhaitez associer un <b>orgUnit</b> au profil créé, vous devez étendre la ressource de profil à ce champ et, après la publication de l’extension, effectuer une requête POST sur le point d’entrée <b>ProfileAndServicesExt</b>.
>
>Pour plus d’informations sur l’extension de ressource du profil, consultez la <a href="https://helpx.adobe.com/fr/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">documentation de Campaign</a>.

<br/>

***Exemple de requête***

Exemple de requête POST pour créer un profil avec le message « john.doe@mail.com ».

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Elle renvoie le profil créé, avec l’adresse email « john.doe@mail.com ».

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
