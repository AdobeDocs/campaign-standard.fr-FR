---
title: Contrôle des modifications du modèle de données
description: Découvrez comment diagnostiquer le modèle de données Adobe Campaign.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
TQID: 'https://experienceleague.adobe.com/XWMP0LlTRgqEJujGETPzVXOCUvkm-Q9OXC-RvaWd-58'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 100%
---
# Contrôle des modifications du modèle de données{#monitoring-data-model-changes}

Le menu **[!UICONTROL Diagnostics]** vous permet de consulter les différents objets techniques générés par l’application, afin de les analyser.

>[!NOTE]
>
>Les écrans de ce menu sont en lecture seule.

![](assets/diagnostic.png)

Vous pouvez visualiser les types d&#39;objets suivants :

* Schémas de données
* Pages web
* Filtres
* Navigation
* Composants
* Traitements par lot

Vous pouvez modifier la configuration de la liste :

* Vous pouvez ajouter et supprimer des colonnes.
* Vous pouvez définir des noms de colonne.
* Vous pouvez définir l’ordre d’affichage des colonnes dans la liste.
* Vous pouvez choisir l’ordre de tri des valeurs dans la liste.

Vous pouvez filtrer la liste :

* Vous pouvez inclure ou exclure des schémas de données natifs, des pages Web, des filtres et des objets de navigation.
* Vous pouvez rechercher des objets par leur nom.
* Vous pouvez filtrer les traitements par lots selon leur statut, leur date de début et leur date de fin.

Vous pouvez télécharger la liste affichée dans un fichier au format TXT avec des valeurs séparées par des virgules.

Vous pouvez consulter les détails de l’objet sélectionné.

Vous pouvez, par exemple, utiliser cette fonction pour consulter les critères de filtrage des filtres d’usine. Cet exemple illustre le code affiché pour les critères de filtrage d’un filtre d’usine :

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)