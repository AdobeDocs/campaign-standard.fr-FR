---
title: Activation de mappage
description: Découvrez comment activer votre mappage de données
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
source-git-commit: 5f3bf4c2d0bba095182194ac28b3107eae2c54a6

---


# Activation de mappage {#mapping-activation}

>[!IMPORTANT]
>
>Le service de données de Campaign Standard est actuellement en version bêta, qui peut faire l’objet de fréquentes mises à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta pour l&#39;Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez le service à la clientèle d’Adobe si vous souhaitez y accéder.

Une fois la définition de mappage terminée, vous pouvez publier le mappage. Après l’étape de déploiement, la réplication des données entre Campaign Standard et Adobe Experience Platform démarre automatiquement. Vous pouvez à tout moment arrêter la réplication en cliquant sur le bouton **[!UICONTROL Arrêter]**.

Selon les modifications apportées à votre mappage, vous pouvez choisir de renvoyer tous vos enregistrements vers Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Depuis la mosaïque de déploiement, vous pouvez accéder au journal des publications et exporter les journaux.

![](assets/aep_publog.png)

Dans l’onglet Tâches **[!UICONTROL d’]**exportation, vous pouvez surveiller la tâche d’exportation pour le mappage publié.

![](assets/aep_jobstatus.png)

Si vous souhaitez surveiller toutes les tâches d’exportation de données, accédez au menu **[!UICONTROL Administration]**>**[!UICONTROL  Développement]** > **[!UICONTROL Plateforme]**>**[!UICONTROL &#x200B;État de l’exportation des données vers la plateforme.]**

![](assets/aep_statusmapping.png)

Etat de la tâche d’importation de données :

* **[!UICONTROL Créé]**: Une tâche d’importation de données est créée et l’assimilation des données est en cours.
* **[!UICONTROL Échec]**: Une tâche d&#39;importation de données a échoué. Le champ Raison décrit la raison de l’échec. L’échec peut être temporaire ou permanent. En cas d’échec temporaire, une nouvelle tâche d’assimilation est créée après un intervalle configuré. Dans un premier temps, l’utilisateur peut vérifier la raison de l’échec. Si le motif redirige un utilisateur vers l’interface utilisateur d’Adobe Experience Platform, il peut se connecter à Adobe Experience Platform et vérifier l’état du lot dans le jeu de données afin de déterminer le motif exact de l’échec.
* **[!UICONTROL Téléchargé]**: Un lot est d’abord créé dans Adobe Experience Platform, puis les données sont assimilées au lot. Le champ ID du lot indique l’ID du lot dans Adobe Experience Platform. Adobe Experience Platform effectue également une validation après validation sur le lot. Le lot est d’abord marqué comme chargé jusqu’à ce qu’Adobe Experience Platform termine l’étape de post-validation. Une tâche continue d’interroger Adobe Experience Platform pour connaître l’état du lot après le téléchargement. Un lot peut être envoyé soit dans Échec, soit dans la validation de l’état de réussite dans Adobe Experience Platform.
* **[!UICONTROL Succès]**: Une fois qu’un lot est téléchargé sur Adobe Experience Platform, l’état de la tâche (post validation in platform) est vérifié après un intervalle configuré. Un état &quot;Succès&quot; a identifié une assimilation réussie des données dans Adobe Experience Platform.
