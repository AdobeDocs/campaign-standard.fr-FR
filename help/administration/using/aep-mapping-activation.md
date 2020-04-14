---
title: Activation du mapping
description: Découvrez comment activer le mapping de données
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 57b87896281efa7dd1e6a612926f59061a0fdcb8

---


# Activation du mapping {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.

Une fois la définition du mapping terminée, vous pouvez le publier. Après l’étape de déploiement, la réplication des données entre Campaign Standard et Adobe Experience Platform démarre automatiquement. At any time, you can stop the replication by clicking on the **[!UICONTROL Stop]** button.

Selon les modifications apportées au mapping, vous pouvez choisir de renvoyer tous vos enregistrements vers Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Dans la vignette de déploiement, vous pouvez accéder aux logs de publication et d’export.

![](assets/aep_publog.png)

In the **[!UICONTROL Export jobs]** tab, you can monitor the export job for the published mapping.

![](assets/aep_jobstatus.png)

Si vous souhaitez surveiller toutes les tâches d’exportation de données, accédez au **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** menu.

![](assets/aep_statusmapping.png)

Statuts du traitement d’ingestion des données :

* **[!UICONTROL Created]**: Une tâche d’importation de données est créée et l’assimilation des données est en cours.
* **[!UICONTROL Failed]**: Une tâche d&#39;importation de données a échoué. Le champ Raison décrit la cause de l’échec. Il peut être temporaire ou permanent. En cas d’échec temporaire, un nouveau traitement d’ingestion est créé après un intervalle configuré. Dans un premier temps, l’utilisateur peut vérifier la raison de l’échec pour résoudre le problème. Si la raison le renvoie vers l’interface utilisateur d’Adobe Experience Platform, il peut se connecter à cette plateforme et vérifier l’état du lot du jeu de données pour déterminer le motif exact de l’échec.
* **[!UICONTROL Uploaded]**: Un lot est d’abord créé dans Adobe Experience Platform, puis les données sont assimilées au lot. Le champ ID de lot indique l’identifiant du lot dans Adobe Experience Platform. Adobe Experience Platform effectue également une post-validation du lot. Ce lot est d’abord marqué comme transféré jusqu’à ce qu’Adobe Experience Platform ait effectué l’étape de post-validation. Un traitement continue d’interroger Adobe Experience Platform pour connaître l’état du lot après transfert. Dans Adobe Experience Platform, un lot peut se trouver dans l’état Échec ou Succès après validation.
* **[!UICONTROL Success]**: Une fois qu’un lot est téléchargé sur Adobe Experience Platform, l’état de la tâche (post validation in platform) est vérifié après un intervalle configuré. Un état « Succès » indique une ingestion réussie des données dans Adobe Experience Platform.
