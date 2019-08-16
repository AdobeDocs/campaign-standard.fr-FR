---
title: Optimiser l'heure d'envoi
seo-title: Optimiser l'heure d'envoi
description: Optimiser l'heure d'envoi
seo-description: Découvrez comment configurer l'heure d'envoi et accroître le taux d'ouverture de vos messages.
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: ht
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Optimiser l'heure d'envoi{#optimizing-the-sending-time}

Pour améliorer le taux d'ouverture de vos messages, vous pouvez définir manuellement une heure d'envoi par destinataire. Dans la mesure du possible, chaque profil recevra le message à la date et à l'heure spécifiées.

La définition d'une heure d'envoi est possible au niveau de la diffusion ou à l'aide d'un workflow.

Pour les emails, en fonction de la charge du serveur et du nombre de reprises, le message sera envoyé dans la mesure du possible à la date et à l'heure planifiées pour chaque destinataire.

* Les reprises dépendent de votre fournisseur d'accès Internet et de votre réputation. Il se peut que le message ne soit pas accepté lors de la première tentative et que plusieurs reprises aient lieu. Voir [Liste des paramètres du canal Email](../../administration/using/configuring-email-channel.md).
* Un débit insuffisant peut retarder la réception de l'email.

Les [Envois](../../sending/using/monitoring-a-delivery.md#sending-logs) indiquent l'heure d'envoi du message à chaque destinataire.

Plusieurs options sont disponibles :

* **[!UICONTROL Pas d'optimisation]** : les messages sont envoyés à l'heure de l'utilisateur.

   Par exemple, si votre fuseau horaire est GMT+1 et que vous tapez 9 heures dans le champ **[!UICONTROL Démarrer l'envoi le]**, un destinataire se trouvant dans le fuseau horaire GMT+3 recevra le message à 11 heures (heure locale du destinataire).

* **[!UICONTROL Envoyer en fonction du fuseau horaire du destinataire]** : tous les destinataires recevront le message en fonction de leur fuseau horaire.

   Par exemple, si vous tapez 9 heures dans le champ **[!UICONTROL Démarrer l'envoi le]**, un destinataire se trouvant dans le fuseau horaire GMT+3 recevra le message à 9 heures (heure locale du destinataire).

   Voir [Envoi des messages au fuseau horaire du destinataire](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Envoyer à une date personnalisée définie en fonction d'une formule]** : chaque destinataire recevra le message à une date et une heure calculée en fonction d'une formule spécifiée.

   Voir [Calcul de la date d'envoi](../../sending/using/computing-the-sending-date.md).

