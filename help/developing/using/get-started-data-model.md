---
title: Prise en main du modèle de données de Campaign Standard
description: Enrichissez le modèle de données du Campaign Standard avec des champs et des ressources personnalisés et étendez les API REST pour exposer les champs étendus.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 94%

---


# Prise en main du modèle de données de Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modèle de données</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Ressources personnalisées</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Utilisation des API</a></p></td></tr>
</table>

Étendez le modèle de données de Campaign Standard en y incorporant vos propres champs et ressources et surveillez toutes les modifications qui lui sont apportées à l’aide d&#39;une vue unique.

## Modèle de données {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Les données utilisées par Campaign sont définies au moyen de différentes ressources renseignées dans un **modèle de données prédéfini**. Le modèle de données affiche une structure SQL d’usine pour un ensemble de ressources liées au marketing : diffusion, audience, landing pages, profil, etc. Chaque ressource est associée à des filtres pour pouvoir les parcourir.

Le menu **Diagnostic** permet de répertorier les objets techniques générés par Campaign Standard (schémas de données, pages web, filtres, etc.). Il est ainsi possible de surveiller le modèle de données et les modifications dont il fait l’objet.

En savoir plus :

* [Notions de modèle de données](../../developing/using/data-model-concepts.md)
* [Bonnes pratiques relatives au modèle de données](../../developing/using/data-model-best-practices.md)
* [Description du modèle de données](../../developing/using/datamodel-introduction.md)
* [Contrôle des modifications du modèle de données](../../developing/using/monitoring-data-model-changes.md)

## Ressources personnalisées {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard permet d’**enrichir le modèle de données prédéfini** afin de créer vos propres ressources (par exemple pour ajouter des tables d’achats ou de produits) ou d’étendre les ressources existantes avec de nouveaux champs. Vous pouvez également configurer les écrans de Campaign pour optimiser la navigation dans les ressources et les champs créés.

De plus, vous avez la possibilité d’**étendre les API REST de Campaign Standard** afin de donner accès aux champs étendus des API pour les profils de ressources personnalisées. Il est ainsi possible, par exemple, de mettre à jour instantanément le profil d’un client avec un code promotion généré à partir d’un système de facturation.

En savoir plus :

* [Ajouter ou étendre une ressource](../../developing/using/key-steps-to-add-a-resource.md)
* [Étendre l’API](../../developing/using/about-extending-the-api.md)
* [Cas pratique : extension de la ressource Profil avec un nouveau champ](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Cas pratique : extension des abonnements à une ressource d’application](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Utilisation des API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Avec les API de Campaign Standard, vous pouvez créer des intégrations pour Adobe Campaign Standard et construire votre propre écosystème en interfaçant l’application avec l’ensemble des technologies que vous utilisez. [Prise en main des API REST de Campaign Standard](../../api/using/get-started-apis.md)

## Autres ressources

* [À propos d’Adobe Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md)
* [Création de ressources personnalisées (vidéo)](https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [Export/import de ressources personnalisées](https://helpx.adobe.com/fr/campaign/kb/acs-get-started-with-cusres.html)
