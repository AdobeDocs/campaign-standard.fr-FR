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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 100%

---


# Activation du mapping {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.

Une fois la définition du mapping terminée, vous pouvez le publier. Après l’étape de déploiement, la réplication des données entre Campaign Standard et Adobe Experience Platform démarre automatiquement. Vous pouvez arrêter la réplication à tout moment en cliquant sur le bouton **[!UICONTROL Arrêter]**.

Selon les modifications apportées au mapping, vous pouvez choisir de renvoyer tous vos enregistrements vers Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Dans la vignette de déploiement, vous pouvez accéder aux logs de publication et d’export.

![](assets/aep_publog.png)

Dans l’onglet **[!UICONTROL Traitements d’exportation]**, vous pouvez surveiller le traitement d’export pour le mapping publié.

![](assets/aep_jobstatus.png)

Si vous souhaitez surveiller tous les traitements d’export de données, accédez au menu **[!UICONTROL Administration]** > **[!UICONTROL Développement]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Statut de l’export des données vers Platform.]**

![](assets/aep_statusmapping.png)

Statuts du traitement d’ingestion des données :

* **[!UICONTROL Créé]** : un traitement d’ingestion des données est créé et l’ingestion des données est en cours.
* **[!UICONTROL Échec]** : un traitement d’ingestion des données a échoué. Le champ Raison décrit la cause de l’échec. Il peut être temporaire ou permanent. En cas d’échec temporaire, un nouveau traitement d’ingestion est créé après un intervalle configuré. Dans un premier temps, l’utilisateur peut vérifier la raison de l’échec pour résoudre le problème. Si la raison le renvoie vers l’interface utilisateur d’Adobe Experience Platform, il peut se connecter à cette plateforme et vérifier l’état du lot du jeu de données pour déterminer le motif exact de l’échec.
* **[!UICONTROL Transfert terminé]** : un lot est tout d’abord créé dans Adobe Experience Platform, puis les données sont ingérées dans le lot. Le champ ID de lot indique l’identifiant du lot dans Adobe Experience Platform. Adobe Experience Platform effectue également une post-validation du lot. Ce lot est d’abord marqué comme transféré jusqu’à ce qu’Adobe Experience Platform ait effectué l’étape de post-validation. Un traitement continue d’interroger Adobe Experience Platform pour connaître l’état du lot après transfert. Dans Adobe Experience Platform, un lot peut se trouver dans l’état Échec ou Succès après validation.
* **[!UICONTROL Succès]** : une fois un lot transféré vers Adobe Experience Platform, l’état du traitement (post-validation sur la plateforme) est vérifié après un intervalle configuré. Un état « Succès » indique une ingestion réussie des données dans Adobe Experience Platform.
