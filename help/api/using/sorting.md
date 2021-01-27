---
solution: Campaign Standard
product: campaign
title: Tri
description: En savoir plus sur les opérations de tri
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 100%

---


# Tri

Le tri est disponible par ordre croissant ou décroissant. Pour ce faire, utilisez le paramètre **%20desc** ou **%20asc** dans votre requête.

Pour savoir s’il est possible de trier un champ, vérifiez le paramètre « sortable » dans les métadonnées de la ressource. Voir à ce propos [cette section](../../api/using/metadata-mechanism.md).

<br/>

***Exemples de requêtes***

* Exemple de requête GET pour récupérer des emails dans la base de données par ordre alphabétique.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Réponse à la requête.

   ```
   {
   "content": [
       "adam@email.com",
       "allison.durance@example.com",
       "amy.dakota@mail.com",
       "andrea.johnson@mail.com",
       ...
   ]
   ...
   }
   ```

* Exemple de requête GET pour récupérer des emails dans la base de données par ordre alphabétique décroissant.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Réponse à la requête.

   ```
   {
   "content": [
       "tombinder@example.com",
       "tombinder@example.com",
       "timross@example.com",
       "john.smith@example.com",
       ...
   ]
   }
   ```
