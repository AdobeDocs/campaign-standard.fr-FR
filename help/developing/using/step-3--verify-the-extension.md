---
title: '"Etape 3 : Vérifier l''extension"'
seo-title: '"Etape 3 : Vérifier l''extension"'
description: '"Etape 3 : Vérifier l''extension"'
seo-description: Apprenez à accéder au champ étendu avec l'API REST.
page-status-flag: jamais activé
uuid: 35 ba 89 a 5-a 354-466 f -91 a 0-50 de 111 a 2 e 00
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: développement
content-type: référence
topic-tags: use-case—extend-the-api
discoiquuid: 21 bad 242-5921-445 c -8 df 9-3 d 57 dbe 35197
internal: n
snippet: y
translation-type: tm+mt
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

