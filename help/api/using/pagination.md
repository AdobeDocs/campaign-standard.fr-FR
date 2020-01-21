---
title: Pagination
description: Découvrez comment effectuer des opérations de pagination.
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
translation-type: ht
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Pagination

Par défaut, 25 ressources sont chargées dans une liste.

Le paramètre **_lineCount** permet de limiter le nombre de ressources répertoriées dans la réponse. Vous pouvez ensuite utiliser le nœud **suivant** pour afficher les résultats suivants.

>[!NOTE]>
>
>Utilisez toujours la valeur d’URL renvoyée dans le nœud **suivant** pour effectuer une requête de pagination.
>
>La requête **_lineStart** est calculée et doit toujours être utilisée dans l’URL renvoyée dans le nœud **suivant**.

<!-- serverside pagination. quand table très longue (au delà de 100.000), on peut plus faire de next. doit utiliser à la place les trucs type lineStart etc. si false: voudra dirre que ça a atteint la limite-->

<br/>

***Exemple de requête ***

Exemple de requête GET pour afficher 1 enregistrement de la ressource de profil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- dans l'exemple, avoir le node "next"-->

Réponse à la requête.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    ...
}
```
