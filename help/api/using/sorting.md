---
title: Tri
description: En savoir plus sur les opérations de tri
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 13fc1b011f61d67dda128e77b854032801bda263
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 100%

---

# Tri

Le tri est disponible par défaut dans l’ordre croissant. Pour trier par ordre décroissant, ajoutez **%20desc** à la valeur du paramètre **_order**.

Pour savoir s’il est possible de trier un champ, vérifiez le paramètre « sortable » dans les métadonnées de la ressource. Voir à ce propos [cette section](../../api/using/metadata-mechanism.md).

<br/>

***Exemples de demande***

* Exemple de requête GET pour récupérer des emails dans la base de données par ordre alphabétique.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
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
