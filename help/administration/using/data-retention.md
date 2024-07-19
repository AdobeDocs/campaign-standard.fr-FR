---
title: Conservation des données
description: Découvrez les valeurs de conservation par défaut pour les tableaux standard
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 100%

---

# Conservation des données{#data-retention}

Dans Campaign, les tables de journaux standard comportent des périodes de conservation prédéfinies qui limitent la durée de stockage des données afin d’éviter de surcharger le système.

La configuration de la conservation des données est définie par les administrateurs et administratrices techniques Adobe lors de la mise en œuvre et les valeurs peuvent varier pour chaque mise en œuvre, selon les exigences du client ou de la cliente.

Contactez les consultants et consultantes Adobe ou les administrateurs et administratrices techniques pour en savoir plus sur les périodes de conservation qui s’appliquent à votre environnement ou pour définir des périodes de conservation personnalisées.

Notez que la fonctionnalité de workflow standard permet de configurer des périodes de conservation pour n&#39;importe quelle table personnalisée.

Vous trouverez ci-dessous les périodes de conservation par défaut pour les tables standard. Dans la mesure du possible, et en fonction de l’utilisation de vos données, Adobe vous suggère de passer aux périodes de conservation recommandées afin d’améliorer les performances de votre instance Campaign.

* **Tracking consolidé** : 6 mois (recommandé : 1 mois)
* **Logs de diffusion** : 6 mois (recommandé : 1 mois)
* **Logs de tracking** : 6 mois (recommandé : 1 mois)
* **Événements** : 1 mois
* **Statistiques sur le traitement des événements** : 6 mois (recommandé : 1 mois)
* **Événements archivés** : 6 mois (recommandé : 1 mois)
* **Entités temporaires** : 7 jours
* **Événements Pipeline ignorés** : 1 mois
* **Alertes de diffusion** : 1 mois
* **Audit des exports** : 6 mois (recommandé : 1 mois)

## Période de conservation des diffusions {#deliveries}

Par défaut, la période de conservation des diffusions est illimitée.

Cependant, si votre instance contient un volume élevé de diffusions, vous pouvez mettre à jour l’option **NmsCleanup_DeliveryPurgeDelay** disponible à partir du menu **[!UICONTROL Administration]** > **[!UICONTROL Paramètres de l’application]**.

Chaque fois que le workflow **[!UICONTROL Nettoyage de la base de données]** est exécuté, les diffusions répondant aux conditions définies pour cette option sont supprimées.

Cette action peut contribuer à accélérer les processus tels que le workflow **[!UICONTROL Copie d’en-têtes à partir de modèles de diffusion]**.

>[!NOTE]
>
>En savoir plus sur les workflows techniques dans [cette section](technical-workflows.md).


La valeur par défaut de l’option **NmsCleanup_DeliveryPurgeDelay** est `-1`. Dans ce cas, aucune diffusion n’est supprimée.

Par exemple, si vous la définissez sur `180`, toutes les diffusions qui ne sont pas des modèles et qui n’ont pas été mises à jour au cours des 180 derniers jours seront supprimées lorsque le workflow **[!UICONTROL Nettoyage de la base de données]** est exécuté.

>[!NOTE]
>
>* Les modèles de diffusion marketing ou transactionnelle ne seront pas supprimés.
>
>* Pour les diffusions récurrentes, les diffusions enfant avec une période d’agrégation définie en mois ou années ne seront pas supprimées.

Lors de la mise à jour de l’option **NmsCleanup_DeliveryPurgeDelay**, il est recommandé de procéder progressivement à plusieurs itérations. Par exemple, vous pouvez commencer en définissant la valeur sur 300 jours, puis 180 jours, puis 120 jours, etc., en vous assurant que les itérations sont séparées d’au moins 2 jours. Sinon, le workflow **[!UICONTROL Nettoyage de la base de données]** peut prendre beaucoup plus de temps en raison d’un grand nombre de diffusions à supprimer.

