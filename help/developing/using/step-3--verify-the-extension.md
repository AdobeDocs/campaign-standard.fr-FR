---
solution: Campaign Standard
product: campaign
title: '"Etape 3 : Vérifier l''extension"'
description: Apprenez à accéder au champ étendu avec l'API REST.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Modèle de données
role: Développeur
level: Expérience
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 96%

---


# Etape 3 : Vérifier l&#39;extension{#step-verify-the-extension}

1. Effectuez une opération GET sur les métadonnées de l&#39;API Profiles &amp; Services Extension afin de vérifier la disponibilité du champ ajouté à la ressource personnalisée Profiles.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Elle renvoie :

   ![](assets/extendpandsapiview.png)

   Le champ est désormais disponible pour d&#39;autres développements et intégrations éventuels.

