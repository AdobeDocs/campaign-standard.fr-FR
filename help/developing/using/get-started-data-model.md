---
title: Commencer avec le modèle de données Campaign Standard
description: Etendez le modèle de données Campaign Standard à l’aide de vos propres champs et ressources et surveillez toutes les modifications apportées au modèle de données en une seule vue.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aeaddca2188e2bdeda71bd35299ccd14398f3c52

---


# Commencer avec le modèle de données Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modèle de données</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Ressources personnalisées</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Utilisation des API</a></p></td></tr>
</table>

Etendez le modèle de données Campaign Standard à l’aide de vos propres champs et ressources et surveillez toutes les modifications apportées au modèle de données en une seule vue.

## Modèle de données {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Les données utilisées par Campaign sont définies au moyen de différentes ressources définies dans un modèle **de données** prédéfini. Le modèle de données affiche une structure SQL prête à l’emploi pour un ensemble de ressources liées au marketing : diffusion, audience, landings page, profil, etc. Chaque ressource est associée à des filtres, ce qui vous permet de naviguer dans les ressources.

Le menu **Diagnostic** vous permet de liste des objets techniques générés par Campaign Standard : schémas de données, pages Web, filtres, etc., vous permettant de surveiller le modèle de données et toute modification apportée à celui-ci.

En savoir plus:

* [Notions de modèle de données](../../developing/using/data-model-concepts.md)
* [Bonnes pratiques relatives au modèle de données](../../developing/using/data-model-best-practices.md)
* [Description du modèle de données](../../developing/using/datamodel-introduction.md)
* [Contrôle des modifications du modèle de données](../../developing/using/monitoring-data-model-changes.md)

## Ressources personnalisées {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard vous permet d’ **enrichir le modèle** de données prédéfini afin de créer vos propres ressources (par exemple pour ajouter des tables d’achats ou de produits) ou d’étendre les ressources existantes à de nouveaux champs. Vous pouvez également configurer des écrans Campaign pour optimiser la navigation dans les nouveaux champs et ressources créés.

De plus, vous pouvez **étendre les API** REST de Campaign Standard afin d’exposer dans les champs étendus des API les Profils de ressources personnalisées. Cela vous permet, par exemple, de mettre à jour le profil d’un client avec un code promotionnel généré à partir d’un système de facturation.

En savoir plus:

* [Ajouter ou étendre une ressource](../../developing/using/key-steps-to-add-a-resource.md)
* [Étendre l’API](../../developing/using/about-extending-the-api.md)
* [Cas d’utilisation : Extension de la ressource profil avec un nouveau champ](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Cas d’utilisation : Extension des abonnements à une ressource d&#39;application](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Utilisation des API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Avec les API Campaign Standard, créez des intégrations pour Adobe Campaign Standard et construisez votre propre écosystème en interfacant Campaign avec le panel de technologies que vous utilisez. [Commencer avec les API Campaign Standard REST](../../api/using/about-campaign-standard-apis.md)

## Autres ressources

* [À propos d’Adobe Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md)
* [Création de ressources personnalisées (vidéo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [Export/import de ressources personnalisées](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
