---
title: Conservation des données
description: Découvrez les valeurs de conservation par défaut pour les tableaux standard
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 0079a924db522de8afc628ef50aa2c861e5a12ee
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 69%

---

# Conservation des données{#data-retention}

>[!NOTE]
>
>Les rapports de données ne sont disponibles que pour les trois dernières années. Pour plus d’informations sur les périodes de conservation des données, contactez les consultantes et consultants Adobe ou vos administrateurs ou administratrices techniques.

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
* **Diffusions** : 2 ans

## Période de conservation des diffusions {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

À compter du 1er juin 2025, seules les diffusions des deux dernières années resteront disponibles dans le système. Vous trouverez plus de détails ci-dessous :

* Toutes les diffusions de plus de deux ans seront définitivement supprimées et ne seront plus accessibles.
* Ce nettoyage inclut uniquement les diffusions envoyées et en échec ; les diffusions récurrentes, les brouillons de diffusion et les modèles ne seront pas affectés.
* Une fois qu’une diffusion est supprimée, toutes les informations de suivi ou d’envoi liées sont également supprimées définitivement.
* Les modèles de diffusion marketing ou transactionnelle ne seront pas supprimés.
* Pour les diffusions récurrentes, les diffusions enfant avec une période d’agrégation définie en mois ou années ne seront pas supprimées.

Si vous souhaitez accélérer des processus tels que le workflow **[!UICONTROL Copier les en-têtes des modèles de diffusion]** , la période de conservation des diffusions peut être réduite. Pour ce faire, contactez votre représentant ou représentante Adobe.

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->


