---
title: 'Étape 3 : vérifier l''extension'
description: Apprenez à accéder au champ étendu avec l'API REST.
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '61'
ht-degree: 100%

---

# Étape 3 : vérifier l&#39;extension{#step-verify-the-extension}

1. Effectuez une opération GET sur les métadonnées de l&#39;API Profiles &amp; Services Extension afin de vérifier la disponibilité du champ ajouté à la ressource personnalisée Profiles.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Elle renvoie :

   ![](assets/extendpandsapiview.png)

   Le champ est désormais disponible pour d&#39;autres développements et intégrations éventuels.
