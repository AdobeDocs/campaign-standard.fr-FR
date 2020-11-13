---
title: Barrières de sécurité de l’intégration de Microsoft Dynamics 365
description: Barrières de sécurité de l’intégration Microsoft Dynamics 365 avec Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '585'
ht-degree: 100%

---


# Barrières de sécurité et limites de l’intégration

## Barrières de sécurité de l’intégration

Les barrières de sécurité suivantes doivent être prises en compte lors de la planification de l’utilisation de cette intégration. Consultez votre représentant technique Adobe si vous pensez que vous ne respectez pas ces barrières de sécurité.

* Vous devez activer la licence du package Campaign approprié pour prendre en charge le volume d’appels au moteur ACS généré par l’intégration. Le dépassement du volume d’appels du moteur sous licence peut entraîner une baisse des performances de Campaign.

   Utilisez les éléments suivants pour estimer le volume d’appels au moteur à partir de l’intégration :

   * Insertions d’enregistrements (c’est-à-dire, nouvel enregistrement) : 1 appel au moteur
   * Suppressions d’enregistrements : 1 appel au moteur
   * Mises à jour d’enregistrement : 2 appels au moteur (un seul appel si l’enregistrement de destination est identique à l’enregistrement source, c’est-à-dire si aucun changement n’est apporté à l’enregistrement ACS)

   Lors de l’estimation du volume global des appels au moteur ACS, il est important de prendre en compte d’autres sources d’appels au moteur, notamment les landing pages, les WebApps, les JSSP, les API, les inscriptions aux applications mobiles, etc.

   Consultez des informations sur le package Campaign à cette adresse : https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html

* L’intégration prend en charge un maximum de 30 millions de contacts.

* L’offre d’intégration standard comprend la prise en charge de cinq entités personnalisées au maximum.

* Les entités personnalisées de plus de 500 000 enregistrements nécessiteront des heures de consulting supplémentaires pour effectuer un import unique initial basé sur des fichiers (par entité personnalisée) via le workflow Campaign (ce qui entraîne un coût supplémentaire).

* L’offre d’intégration standard prend en charge les entités personnalisées jusqu’à 50 colonnes en taille.

* Vous devez créer et publier vos ressources personnalisées avant de mettre en œuvre l’intégration.

* La profondeur maximale de table lors de la liaison des tables est de deux (c’est-à-dire., table1->table2->table3).

* La prise en charge des types de données Dynamics 365 est limitée. Si votre modèle de données contient un type de données autre que des types de données simples (par exemple, chaînes, entiers, décimales, etc.), vous devrez peut-être mettre à jour votre modèle de données avant d’utiliser l’intégration.

* La conservation des données existantes dans les entités personnalisées Campaign peut entraîner des coûts de consulting supplémentaires pour préparer les données à l’intégration.

* Il peut être nécessaire d’établir des fenêtres de maintenance entre Adobe et le client, car l’ingestion initiale peut provoquer un ralentissement de Campaign.

* Nous vous encourageons à communiquer les cas connus d’augmentation ou de « pic » de l’utilisation de l’intégration (p. ex., forte augmentation des enregistrements nouveaux ou mis à jour), car cela peut entraîner un ralentissement de la synchronisation des données.

* Dans le cadre de l’intégration, vous devrez exécuter les étapes de configuration préalable à l’intégration dans Microsoft Azure et Dynamics 365. Voir les étapes de configuration [sur cette page](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* Il est attendu que vous importerez vos modèles de données Dynamics 365 et Campaign dans l’intégration et que vous les gérerez.

## Limites de l’intégration

L’intégration a été conçue pour résoudre le cas pratique général du mouvement de données communes entre Dynamics 365 et Campaign, mais elle n’est pas destinée à traiter chaque cas pratique spécifique à chaque client :

* L’intégration n’émet aucune suppression de confidentialité (ex. : RGPD). La responsabilité de répondre aux demandes d’accès à des informations personnelles des utilisateurs finaux incombe au client ; de telles demandes doivent être effectuées indépendamment à la fois dans Campaign (via Adobe Experience Platform Privacy Service) et dans Dynamics 365. L’intégration peut générer des suppressions régulières pour faciliter la synchronisation des données, si nécessaire.

* Aucune donnée de profil ou d’entité personnalisée ne sera synchronisée de Campaign vers Dynamics 365, à l’exception des informations d’opt-out (si elles sont configurées par le client).

* La gestion des abonnements Campaign (c’est-à-dire les abonnements/désabonnements) n’est pas prise en charge de manière native.

* La composition et le déclenchement de campagnes email Campaign à partir de Dynamics 365 ne sont pas pris en charge.

* L’intégration ne prend pas en charge la réorganisation des données entre les modèles de données Dynamics 365 et Campaign. Il est prévu que l’intégration synchronise une table Dynamics 365 avec une table Campaign.

* Il n’existe aucune interface utilisateur en libre-service avec la version actuelle de l’intégration.
