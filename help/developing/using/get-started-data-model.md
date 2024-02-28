---
title: Prise en main du modèle de données de Campaign Standard
description: Enrichissez le modèle de données Campaign Standard avec des ressources et des champs personnalisés et étendez les API REST pour exposer les champs étendus.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '334'
ht-degree: 100%

---

# Prise en main du modèle de données de Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modèle de données</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Ressources personnalisées</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Utilisation des API</a></p></td></tr>
</table>

Étendez le modèle de données de Campaign Standard en y incorporant vos propres champs et ressources et surveillez toutes les modifications qui lui sont apportées à l’aide d&#39;une vue unique.

## Modèle de données {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Les données utilisées par Campaign sont définies au moyen de différentes ressources renseignées dans un **modèle de données prédéfini**. Le modèle de données affiche une structure SQL d’usine pour un ensemble de ressources liées au marketing : diffusion, audience, landing pages, profil, etc. Chaque ressource est associée à des filtres pour pouvoir parcourir les ressources

Le menu **Diagnostic** permet de répertorier les objets techniques générés par Campaign Standard (schémas de données, pages web, filtres, etc.). Il est ainsi possible de surveiller le modèle de données et les modifications dont il fait l’objet.

En savoir plus :

* [Notions de modèle de données](../../developing/using/data-model-concepts.md)
* [Bonnes pratiques relatives au modèle de données](../../developing/using/data-model-best-practices.md)
* [Description du modèle de données](../../developing/using/datamodel-introduction.md)
* [Contrôle des modifications du modèle de données](../../developing/using/monitoring-data-model-changes.md)

## Ressources personnalisées {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard permet d’**enrichir le modèle de données prédéfini** afin de créer vos propres ressources (par exemple pour ajouter des tables d’achats ou de produits) ou d’étendre les ressources existantes avec de nouveaux champs. Vous pouvez également configurer les écrans de Campaign pour optimiser la navigation dans les ressources et les champs créés.

De plus, vous avez la possibilité d’**étendre les API REST de Campaign Standard** afin de donner accès aux champs étendus des API pour les profils de ressources personnalisées. Il est ainsi possible, par exemple, de mettre à jour instantanément le profil d’un client avec un code promotion généré à partir d’un système de facturation.

En savoir plus :

* [Ajouter ou étendre une ressource](../../developing/using/key-steps-to-add-a-resource.md)
* [Étendre l’API](../../developing/using/about-extending-the-api.md)
* [Cas pratique : extension de la ressource Profil avec un nouveau champ](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Cas pratique : extension des abonnements à une ressource d’application](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Utilisation des API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Avec les API de Campaign Standard, vous pouvez créer des intégrations pour Adobe Campaign Standard et construire votre propre écosystème en interfaçant l’application avec l’ensemble des technologies que vous utilisez. [Prise en main des API REST de Campaign Standard](../../api/using/get-started-apis.md)

## Autres ressources

* [Export / import de ressources personnalisées](https://helpx.adobe.com/fr/campaign/kb/acs-get-started-with-cusres.html)
* [Exporter des données de Campaign vers Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
