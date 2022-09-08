---
title: Conservation des données
description: Découvrez les valeurs de conservation par défaut pour les tableaux standard
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: ede4bd97ffddca4a5e24f1e4114d50ca5140a01d
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 88%

---

# Conservation des données{#data-retention}

Dans Campaign, les tables de logs standard comportent des périodes de conservation prédéfinies qui limitent leur durée de stockage des données.

Vous trouverez ci-dessous les valeurs de conservation par défaut pour les tables standards. Notez que la configuration de la conservation des données est définie par les administrateurs techniques Adobe au cours du déploiement et que les valeurs peuvent varier selon les besoins du client.

+++[!DNL Campaign Standard] 22.3 ou version ultérieure

* **Tracking consolidé** : 1 mois
* **Logs de diffusion** : 1 mois
* **Logs de tracking** : 1 mois
* **Événements** : 1 mois
* **Statistiques du traitement des événements** : 1 mois
* **Événements historisés** : 1 mois
* **Entités temporaires** : 7 jours
* **Événements Pipeline ignorés** : 1 mois
* **Alertes de diffusion** : 1 mois
* **Audits des exports** : 1 mois
+++

+++ Précédent [!DNL Campaign Standard] builds

* **Tracking consolidé** : 6 mois
* **Logs de diffusion** : 6 mois
* **Logs de tracking** : 6 mois
* **Événements** : 1 mois
* **Statistiques du traitement des événements** : 6 mois
* **Événements historisés** : 6 mois
* **Entités temporaires** : 7 jours
* **Événements Pipeline ignorés** : 1 mois
* **Alertes de diffusion** : 1 mois
* **Audits des exports** : 6 mois
+++

La fonctionnalité de workflow standard permet de configurer des périodes de conservation pour n&#39;importe quelle table personnalisée.

Pour en savoir plus sur la conservation des données ou pour définir une rétention pour les tables personnalisées, contactez les consultants ou les administrateurs techniques d’Adobe.
