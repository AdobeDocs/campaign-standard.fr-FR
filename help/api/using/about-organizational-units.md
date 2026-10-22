---
title: À propos des entités organisationnelles
description: Découvrez les entités organisationnelles et les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 100%
---

# À propos des entités organisationnelles {#about-organizational-units}

Le point d’entrée **orgUnitBase** vous permet d’interagir avec les entités organisationnelles, par exemple pour mettre à jour leurs attributs ou l’entité organisationnelle d’un profil. Pour plus d’informations sur les entités organisationnelles de Campaign, consultez la [documentation Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=fr#administrating).

Le champ **Entité organisationnelle** est ajouté à un profil lors de l’extension de la ressource de profil. Par conséquent, n’oubliez pas d’utiliser systématiquement le point d’entrée **profileAndServicesExt** pour interagir avec les entités géographiques. Pour plus d’informations sur l’extension de ressource du profil, consultez la [documentation Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=fr#partitioning-profiles).
