---
solution: Campaign Standard
product: campaign
title: Comptage
description: Découvrez comment effectuer des opérations de comptage.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d6354249-3b0d-4532-951f-b0fae953f7e1
translation-type: ht
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: ht
source-wordcount: '88'
ht-degree: 100%

---

# Comptage

L’API REST d’Adobe Campaign permet de comptabiliser le nombre d’enregistrements contenus dans une requête. Pour ce faire, utilisez l’URL renvoyée dans le nœud **count** .

<br/>

***Exemple de requête***

Pour compter tous les services dont la valeur **messageType** est égale à « sms », exécutez une requête GET avec le filtre **byChannel**.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=sms \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie les services correspondant au filtre.

```
{
    "content": [
        {
            ...
            "messageType": "sms",
            "mode": "newsletter",
            "name": "SVC6",
            ...
        },
        ...
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy"
    },
    "serverSidePagination": true
}
```

Exécutez une requête GET sur l’URL du nœud **count** pour récupérer le nombre de résultats.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie le nombre d’enregistrements.

```
{
    "count": 26
}
```
