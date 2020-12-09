---
solution: Campaign Standard
product: campaign
title: Optimiser l'heure d'envoi
description: Découvrez comment configurer l'heure d'envoi et accroître le taux d'ouverture de vos messages.
audience: sending
content-type: reference
topic-tags: sheduling-messages
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '295'
ht-degree: 100%

---


# Optimiser l&#39;heure d&#39;envoi{#optimizing-the-sending-time}

Pour améliorer le taux d&#39;ouverture de vos messages, vous pouvez définir manuellement une heure d&#39;envoi par destinataire. Dans la mesure du possible, chaque profil recevra le message à la date et à l&#39;heure spécifiées.

La définition d&#39;une heure d&#39;envoi est possible au niveau de la diffusion ou à l&#39;aide d&#39;un workflow.

Pour les emails, en fonction de la charge du serveur et du nombre de reprises, le message sera envoyé dans la mesure du possible à la date et à l&#39;heure planifiées pour chaque destinataire.

* Les reprises dépendent de votre fournisseur d&#39;accès Internet et de votre réputation. Il se peut que le message ne soit pas accepté lors de la première tentative et que plusieurs reprises aient lieu. Voir [Liste des paramètres du canal Email](../../administration/using/configuring-email-channel.md).
* Un débit insuffisant peut retarder la réception de l&#39;email.

Les [Envois](../../sending/using/monitoring-a-delivery.md#sending-logs) indiquent l&#39;heure d&#39;envoi du message à chaque destinataire.

Plusieurs options sont disponibles :

* **[!UICONTROL Pas d&#39;optimisation]** : les messages sont envoyés à l&#39;heure de l&#39;utilisateur.

   Par exemple, si votre fuseau horaire est GMT+1 et que vous tapez 9 heures dans le champ **[!UICONTROL Démarrer l&#39;envoi le]**, un destinataire se trouvant dans le fuseau horaire GMT+3 recevra le message à 11 heures (heure locale du destinataire).

* **[!UICONTROL Envoyer en fonction du fuseau horaire du destinataire]** : tous les destinataires recevront le message en fonction de leur fuseau horaire.

   Par exemple, si vous tapez 9 heures dans le champ **[!UICONTROL Démarrer l&#39;envoi le]**, un destinataire se trouvant dans le fuseau horaire GMT+3 recevra le message à 9 heures (heure locale du destinataire).

   Voir [Envoi des messages au fuseau horaire du destinataire](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Envoyer à une date personnalisée définie en fonction d&#39;une formule]** : chaque destinataire recevra le message à une date et une heure calculée en fonction d&#39;une formule spécifiée.

   Voir [Calcul de la date d&#39;envoi](../../sending/using/computing-the-sending-date.md).

