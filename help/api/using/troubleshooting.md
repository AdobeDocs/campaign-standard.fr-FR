---
title: Résolution des problèmes
description: En savoir plus sur les problèmes courants liés aux API Campaign Standard.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Résolution des problèmes {#troubleshooting}

* **Lorsque vous accédez à Adobe.io Console, vous obtenez l’erreur suivante : "La console d’E/S Adobe est uniquement disponible pour sélectionner les membres des comptes d’entreprise. Si vous pensez que vous devriez avoir accès, contactez votre administrateur système."**

Vous pouvez uniquement créer des clés d’API pour les organisations IMS dont vous êtes administrateur. Si ce message s’affiche et que vous souhaitez créer des clés d’API, demandez à l’un des administrateurs de l’organisation IMS.

* **Lors de l’exécution d’une requête à Adobe.io, vous obtenez {"error_code":"403023","message":"Profil non valide"}**

Cela signifie qu’il existe un problème avec l’approvisionnement IMS de votre produit Campaign spécifique : l'équipe IMS doit le réparer.

Pour plus de détails, vous pouvez appeler l’API IMS avec votre jeton pour voir à quoi ressemble votre profil IMS : Vous devez disposer d’un prodCtx dont l’id_organisation est identique à celui que vous avez inséré dans l’URL pour qu’Adobe.io puisse acheminer votre requête.
S’il lui manque, l’approvisionnement IMS doit être corrigé.

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie l’erreur suivante.

```
{"error_code":"403023","message":"Profile is not valid"}
```

Vérifiez votre profil IMS avec cette requête.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Dans la réponse, la valeur ORGANIZATION_ID doit être la même dans votre première requête GET.

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **Lors d’une requête à Adobe.io, vous obtenez {"code":500, "message":"Oups. Quelque chose s'est mal passé. Vérifiez votre URI et réessayez."}**

Adobe.io déclare votre URI non valide : l'URI que vous demandez n'est probablement pas valide. Sur Adobe.io, lorsque vous sélectionnez le service Campaign, vous obtenez un sélecteur avec une liste des ID d’organisation possibles. Vous devez vérifier que celui que vous choisissez est celui que vous avez mis dans votre URL.

* **Lors de l’exécution d’une requête à Adobe.io, vous obtenez {"error_code":"401013","message":"Le jeton Oauth n’est pas valide"}**

Votre jeton n’est pas valide (appel IMS incorrect utilisé pour générer un jeton) ou votre jeton a expiré.

* **Je ne vois pas mon profil après la création**

Selon la configuration de l’instance, le profil créé doit être associé à une **orgUnit**. Pour comprendre comment ajouter ce champ à votre création, consultez [cette section](../../api/using/creating-profiles.md).

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu’un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
