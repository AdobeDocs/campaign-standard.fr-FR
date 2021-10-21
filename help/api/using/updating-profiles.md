---
title: Mise à jour des profils
description: Découvrez comment mettre à jour les profils à l’aide des API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: ht
source-wordcount: '94'
ht-degree: 100%

---

# Mise à jour des profils {#updating-profiles}

La mise à jour des profils est effectuée avec une requête **PATCH** .

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. La première étape consiste à **récupérer le profil**.

1. Dans une seconde requête, nous allons exécuter une **requête PATCH** sur le profil, avec les informations complétées dans la payload.

1. Pour vérifier si la requête PATCH a mis à jour le profil, nous pouvons exécuter une requête GET finale.

<br/>

***Exemple de requête***

Exemple de requête GET pour récupérer un profil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Réponse à la requête.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

Requête PATCH pour mettre à jour l’attribut « phone ».

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

Elle renvoie la clé PKEY et l’URL pour récupérer le profil mis à jour.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
