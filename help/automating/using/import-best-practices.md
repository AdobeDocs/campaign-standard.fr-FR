---
solution: Campaign Standard
product: campaign
title: Bonnes pratiques d’import
description: Découvrez les meilleures pratiques à appliquer lors de l’import de données dans la base de données.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '581'
ht-degree: 100%

---


# Bonnes pratiques d’import {#import-best-practices}

>[!CAUTION]
>
>Lorsque vous utilisez cette fonctionnalité, gardez à l’esprit les limites du stockage SFTP, du stockage en base de données et des profils actifs en fonction de votre contrat Adobe Campaign.

Pour garantir la cohérence des données au sein de la base de données et éviter les erreurs fréquentes lors de la mise à jour de la base de données ou de l’export de données, faites preuve de précaution et suivez les quelques règles simples détaillées ci-dessous.

## Utiliser les modèles d’import           {#using-import-templates}

La plupart des workflows d’import doivent contenir les activités suivantes : **[!UICONTROL Chargement de fichier]**, **[!UICONTROL Réconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Déduplication]**, **[!UICONTROL Mise à jour de données]**.

L’utilisation de modèles d’import facilite la préparation d’imports similaires et garantit la cohérence des données au sein de la base de données.

Pour de nombreux projets, les imports sont construits sans activité de **[!UICONTROL Déduplication]** car les fichiers utilisés n’ont pas de doublon. Des doublons apparaissent parfois suite à l’import d’autres fichiers. La déduplication est alors difficile. C’est pourquoi l’ajout d’une étape de déduplication est une précaution utile pour tous les workflows d’import.

Ne partez pas de l’hypothèse selon laquelle les données entrantes sont cohérentes et justes ou que le département informatique ou le responsable Adobe Campaign s’en occupera. Gardez la normalisation des données à l’esprit tout au long du projet. Veillez à dédupliquer, à réconcilier et à maintenir la cohérence des données lors des imports.

Un exemple de modèle de workflow générique conçu pour importer des données est disponible dans la section [Exemple : modèle de workflow d’import](../../automating/using/creating-import-workflow-templates.md).

>[!NOTE]
>
>Vous pouvez également utiliser des [modèles d’import](../../automating/using/importing-data-with-import-templates.md). Il existe des modèles de workflow définis par un administrateur qui, lorsqu’ils sont activés, permettent uniquement de spécifier le fichier contenant les données à importer.

**Rubriques connexes :**

* [Activité Chargement de fichier](../../automating/using/load-file.md)
* [Activité Réconciliation](../../automating/using/reconciliation.md)
* [Activité Segmentation](../../automating/using/segmentation.md)
* [Activité Déduplication](../../automating/using/deduplication.md)
* [Activité Mise à jour de données](../../automating/using/update-data.md)

## Utiliser des formats de fichiers plats        {#using-flat-file-formats}

Le format le plus efficace pour les imports est le fichier plat. Les fichiers plats peuvent être importés en masse au niveau de la base de données.

Par exemple :

* Séparateur : onglet ou point virgule
* Première ligne avec en-têtes
* Pas de délimiteur de chaîne
* Format de date : AAAA/MM/JJ HH:mm:SS

Voici un exemple de fichier à importer :

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## Utiliser la compression        {#using-compression}

Lorsque cela est possible, utilisez des fichiers compressés pour les imports et les exports. GZIP est pris en charge par défaut. Vous pouvez ajouter une étape de prétraitement lors de l’import des fichiers ou de post-traitement lors de l’extraction des données dans les activités de workflow **[!UICONTROL Chargement de fichier]** et **[!UICONTROL Extraction de fichier]**.

**Rubriques connexes :**

* [Activité Chargement de fichier](../../automating/using/load-file.md)
* [Activité Extraction de fichier](../../automating/using/extract-file.md)

## Importer en mode Delta {#importing-in-delta-mode}

Les imports standard doivent être effectués en mode delta. Cela signifie qu’au lieu d’envoyer le tableau entier à chaque fois, seules les données modifiées ou nouvelles sont envoyée à Adobe Campaign.

Les imports complets sont réservés au chargement initial.

## Maintenir la cohérence        {#maintaining-consistency}

Pour maintenir la cohérence des données dans la base de données Adobe Campaign, veuillez appliquer les principes suivants :

* Si les données importées correspondent à une table de référence dans Adobe Campaign, elles doivent être réconciliées avec ce tableau dans le workflow. Les enregistrements sans correspondance doivent être rejetés.
* Assurez-vous que les données importées soient toujours **« normalisées »** (email, numéro de téléphone, adresse postale) et que cette normalisation soit fiable et ne risque pas de changer pas au fil des années. Si ce n’est pas le cas, des doublons risquent d’apparaître dans la base de données, et dans la mesure où Adobe Campaign ne fournit pas d’outils de « correspondance approximative », leur suppression sera très difficile.
* Les données transactionnelles doivent être dotées d’une clé de réconciliation et être réconciliées avec les données existantes afin d’éviter la création de doublons.
* **Les fichiers liés doivent être importés dans l’ordre**. Si l’import est composé de fichiers multiples et interdépendants, le workflow doit vérifier que les fichiers sont importés dans l’ordre. Si un fichier échoue, les autres fichiers ne sont pas importés.
* **Dédupliquez**, réconciliez et maintenez la cohérence lorsque vous importez des données.
