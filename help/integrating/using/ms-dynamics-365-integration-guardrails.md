---
title: Gardiens d'intégration Microsoft Dynamics 365
description: Microsoft Dynamics 365 avec garde-fous d'intégration Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e90f878814e65a9a61ee4013d94fd0bf3b1f7875
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# Gardiens et limites d’intégration

## Gardrails d’intégration

Les gardiens suivants doivent être pris en considération lors de la planification de l&#39;utilisation de cette intégration. Consultez votre représentant technique Adobe si vous pensez que vous dépassez ces garde-fous.

* Vous devez activer la licence du package Campaign approprié pour prendre en charge le volume d&#39;appel du moteur ACS généré par l&#39;intégration. Le dépassement du volume d&#39;appel du moteur sous licence peut entraîner une dégradation des performances de Campaign.

   Utilisez ce qui suit pour vous aider à estimer le volume d&#39;appel du moteur à partir de l&#39;intégration :

   * Ensembles d&#39;enregistrements (c.-à-d. nouvel enregistrement) : 1 appel au moteur
   * L&#39;enregistrement supprime : 1 appel au moteur
   * Enregistrer les mises à jour : 2 appels au moteur (un seul appel si l&#39;enregistrement de destination est identique à l&#39;enregistrement source, c&#39;est-à-dire si aucun changement n&#39;est apporté à l&#39;enregistrement ACS)

   Lors de l&#39;estimation du volume global des appels au moteur ACS, il est important de prendre en compte d&#39;autres sources d&#39;appels au moteur, notamment les landings page, les applications WebApps, les JSSP, les API, les inscriptions aux applications mobiles, etc.

   Informations sur le package Campaign de vue ici : https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* L&#39;intégration prend en charge un maximum de 30 millions de contacts.

* L’offre d’intégration standard comprend la prise en charge de cinq entités personnalisées au maximum.

* Les entités personnalisées de plus de 500 000 enregistrements nécessiteront des heures de conseil supplémentaires pour effectuer une importation initiale basée sur des fichiers ponctuelle (par entité personnalisée) via le processus Campaign (ce qui entraîne un coût supplémentaire).

* L’offre d’intégration standard prend en charge les entités personnalisées jusqu’à 50 colonnes de taille.

* Vous devez créer et publier vos ressources personnalisées avant de mettre en oeuvre l’intégration.

* La profondeur maximale de table lors de la liaison des tables est de deux (c.-à-d., tableau1->tableau2->tableau3).

* La prise en charge des types de données dynamiques 365 est limitée. Si votre modèle de données contient un type de données autre que des types de données simples (par exemple, chaînes, entiers, décimales, etc.), vous devrez peut-être mettre à jour votre modèle de données avant d’utiliser l’intégration.

* La conservation des données existantes dans les entités personnalisées Campaign peut entraîner des coûts de consultation supplémentaires pour préparer les données à l’intégration.

* Il peut être nécessaire d&#39;établir des fenêtres de maintenance à l&#39;intégration entre l&#39;Adobe et le client, car l&#39;assimilation initiale peut provoquer un ralentissement de Campaign.

* Nous vous encourageons à communiquer les cas connus d’augmentation ou de &quot;pic&quot; de l’utilisation de l’intégration (p. ex., forte augmentation des enregistrements nouveaux ou mis à jour), car cela pourrait entraîner un ralentissement de la synchronisation des données.

* Dans le cadre de l&#39;intégration, vous devrez exécuter les étapes de configuration préalable à l&#39;intégration dans Microsoft Azure et Dynamics 365. Voir les étapes de configuration [sur cette page](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* Il est prévu que vous apporterez vos modèles de données Dynamics 365 et Campaign à l&#39;intégration et que vous les conserverez.

## Limites d’intégration

L&#39;intégration a été conçue pour résoudre le cas d&#39;utilisation générale du mouvement de données commun entre Dynamics 365 et Campaign, mais elle n&#39;est pas destinée à traiter chaque cas d&#39;utilisation spécifique à chaque client :

* L’intégration n’émet aucune suppression de confidentialité (ex. : RMGD). La responsabilité de répondre aux demandes de confidentialité des utilisateurs finaux incombe au client ; de telles demandes doivent être effectuées indépendamment à la fois dans Campaign (via l&#39;Adobe Experience Platform Privacy Service) et dans Dynamics 365. L’intégration peut générer des suppressions régulières pour faciliter la synchronisation des données, si nécessaire.

* Aucune donnée d&#39;profil ou d&#39;entité personnalisée ne sera synchronisée de Campaign à Dynamics 365, à l&#39;exception des informations d&#39;exclusion (si elles sont configurées par le client).

* La gestion des abonnements Campaign (c’est-à-dire les abonnements/désabonnements) n’est pas prise en charge de manière native.

* La composition et le déclenchement de campagnes par courrier électronique Campaign à partir de Dynamics 365 ne sont pas pris en charge.

* L&#39;intégration ne prend pas en charge la réorganisation des données entre les modèles de données Dynamics 365 et Campaign. Il est prévu que l&#39;intégration synchronise une table Dynamics 365 avec une table Campaign.

* Il n’existe aucune interface en libre-service avec la version actuelle de l’intégration.
