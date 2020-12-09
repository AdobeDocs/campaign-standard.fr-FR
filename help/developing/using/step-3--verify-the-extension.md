---
solution: Campaign Standard
product: campaign
title: '"Etape 3 : Vérifier l''extension"'
description: Apprenez à accéder au champ étendu avec l'API REST.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '59'
ht-degree: 100%

---


# Etape 3 : Vérifier l&#39;extension{#step-verify-the-extension}

1. Effectuez une opération GET sur les métadonnées de l&#39;API Profiles &amp; Services Extension afin de vérifier la disponibilité du champ ajouté à la ressource personnalisée Profiles.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Elle renvoie :

   ![](assets/extendpandsapiview.png)

   Le champ est désormais disponible pour d&#39;autres développements et intégrations éventuels.

