---
title: A propos de l’envoi de messages avec Campaign
description: Découvrez les différentes étapes pour tester et envoyer un message.
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: ht
source-git-commit: c49fcd793cbb13d26ccf3a47af145de7acd697e7

---


# À propos de l’envoi de messages avec Campaign{#about-sending-messages-with-campaign}

Une fois que vous avez défini la cible et créé le contenu d’un message, vous devez tester et approuver le contenu, la personnalisation, le rendu et la configuration, et vous assurer que tout est correct avant d’envoyer le message à la cible principale.

Pour ce faire, les bonnes pratiques sont les suivantes :

* Préparez l’envoi : cette étape permet de procéder à l’analyse et à la préparation des messages à envoyer. La préparation analyse la cible, la personnalisation et la validité du message. Les erreurs détectées pendant cette étape doivent être corrigées avant de poursuivre. Vous pouvez effectuer la préparation autant de fois que nécessaire. Pour plus d’information sur la préparation des messages, consultez [cette section](../../sending/using/preparing-the-send.md).

   >[!NOTE]
   >
   >Vous pouvez définir des règles de fatigue cross-canal globales qui excluront automatiquement les profils sur-sollicités des campagnes. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

* Prévisualisez les messages à l’aide d’un profil de test. Pour plus d’information sur la prévisualisation des messages, consultez [cette section](../../sending/using/previewing-messages.md).
* Envoyez des BAT pour tester les messages. Pour plus d’informations sur les BAT, consultez [cette section](../../sending/using/sending-proofs.md).
* Vérifiez le rendu des messages : vérifiez que l’affichage de votre message sera optimal sur divers clients web, webmails et appareils (vivement recommandé. En savoir plus sur le rendu des emails dans [cette section](../../sending/using/email-rendering.md).

Vous pouvez alors :

* Planifier l’envoi : vous pouvez définir le moment où les messages seront envoyés. Vous pouvez, par exemple, adapter l’envoi au fuseau horaire du destinataire, optimiser l’heure d’envoi ou calculer la date d’envoi. En savoir plus dans [cette section](../../sending/using/about-scheduling-messages.md).
* Envoyez le message : une fois que le message est prêt, vous pouvez commencer l’envoi. Accédez aux logs et aux rapports disponibles pour contrôler la diffusion de votre message et mesurer le succès de votre campagne. Adobe Campaign propose également un système d’alerte par email pour tracker les succès et les échecs des diffusions. En savoir plus sur [cette page](../../sending/using/confirming-the-send.md).

## Rubriques connexes :

| Pages utiles | Autres ressources |
|---|---|
| [Optimiser votre délivrabilité](../../sending/using/about-deliverability.md) | [Gestion de la fatigue](../../sending/using/fatigue-rules.md) |
| [Contrôle du débit des diffusions](../../reporting/using/delivery-throughput.md) | [Conception d’emails de test A/B](../../channels/using/designing-an-a-b-test-email.md) |
| [Réception d’une notification en cas d’échec](../../sending/using/receiving-alerts-when-failures-happen.md) | [Contrôler une diffusion](../../sending/using/monitoring-a-delivery.md) |
| [Création d’un groupe témoin](../../automating/using/workflow-control-group.md) | [Envoi de messages de relance](../../channels/using/follow-up-messages.md) |