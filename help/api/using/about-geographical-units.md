---
title: À propos des entités géographiques
description: Découvrez les entités géographiques et les API.
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
source-wordcount: '145'
ht-degree: 100%
---

# À propos des entités géographiques {#about-geographical-units}

>[!CAUTION]
>
>La fonctionnalité d’entité géographique a été abandonnée dans la version 18.7 de Campaign Standard.
>
>Par conséquent, les nouvelles instances de Campaign Standard, ainsi que les instances existantes sans entités géographiques, ne peuvent pas bénéficier de cette fonctionnalité à partir de la version 18.7.
>
>Pour plus d’informations à ce sujet, consultez la page <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=fr">Fonctionnalités obsolètes</a>.

Le point d’entrée **geoUnitBase** vous permet d’interagir avec les entités géographiques, par exemple pour mettre à jour leurs attributs ou l’entité d’un profil.

Le champ **Entité géographique** est ajouté à un profil lors de l’extension de la ressource de profil. Par conséquent, n’oubliez pas d’utiliser systématiquement le point d’entrée **profileAndServicesExt** pour interagir avec les entités géographiques. Pour plus d’informations sur l’extension de ressource du profil, consultez la [documentation Campaign](https://helpx.adobe.com/fr/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
