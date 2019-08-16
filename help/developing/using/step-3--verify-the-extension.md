---
title: '"Etape 3 : Vérifier l''extension"'
seo-title: '"Etape 3 : Vérifier l''extension"'
description: '"Etape 3 : Vérifier l''extension"'
seo-description: Apprenez à accéder au champ étendu avec l'API REST.
page-status-flag: never-activated
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Etape 3 : Vérifier l'extension{#step-verify-the-extension}

1. Effectuez une opération GET sur les métadonnées de l'API Profiles &amp; Services Extension afin de vérifier la disponibilité du champ ajouté à la ressource personnalisée Profiles.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Elle renvoie :

   ![](assets/extendpandsapiview.png)

   Le champ est désormais disponible pour d'autres développements et intégrations éventuels.

