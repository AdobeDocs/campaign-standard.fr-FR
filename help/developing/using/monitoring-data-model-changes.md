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
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 21%

---

# Contrôle des modifications du modèle de données{#monitoring-data-model-changes}

Dans la **[!UICONTROL Diagnostic]** , vous pouvez visualiser les objets techniques générés par l&#39;application, afin de les analyser.

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
* Traitements batch

Vous pouvez modifier la configuration de la liste :

* Vous pouvez ajouter et supprimer des colonnes.
* Vous pouvez définir des noms de colonne.
* Vous pouvez définir l&#39;ordre d&#39;affichage des colonnes de la liste.
* Vous pouvez choisir l’ordre de tri des valeurs dans la liste.

Vous pouvez filtrer la liste :

* Vous pouvez inclure ou exclure des schémas de données natifs, des pages web, des filtres et des objets de navigation.
* Vous pouvez rechercher des objets par leur nom.
* Vous pouvez filtrer les tâches par lots selon leur état, leur date de début et leur date de fin.

Vous pouvez télécharger la liste affichée dans un fichier au format TXT avec des valeurs séparées par des virgules.

Vous pouvez afficher les détails de l’objet sélectionné.

Vous pouvez, par exemple, utiliser cette fonction pour afficher les critères de filtrage des filtres d’usine. Cet exemple illustre le code affiché pour les critères de filtrage d&#39;un filtre d&#39;usine :

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)