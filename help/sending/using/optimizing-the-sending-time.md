---
title: Optimiser l'heure d'envoi
description: Découvrez comment configurer l'heure d'envoi et accroître le taux d'ouverture de vos messages.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: f35b46c6-de88-4efa-b3b7-8bb9024e40a8
TQID: 'https://experienceleague.adobe.com/FjL5t1ohvrgDdqLiCr03z1Nbq6IukIBysKkmXJ7561c'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: 0d3d7867-163e-5570-9cfc-7132e55fb049
    internal-label: Send Time Optimization
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 73%
---
# Optimiser l&#39;heure d&#39;envoi{#optimizing-the-sending-time}

Pour améliorer le taux d&#39;ouverture de vos messages, vous pouvez définir manuellement une heure d&#39;envoi par destinataire. Dans la mesure du possible, chaque profil recevra le message à la date et à l’heure spécifiées.

La définition d&#39;une heure d&#39;envoi est possible au niveau de la diffusion ou à l&#39;aide d&#39;un workflow.

Pour les emails, en fonction de la charge du serveur et du nombre de reprises, le message sera envoyé dans la mesure du possible à la date et à l&#39;heure planifiées pour chaque destinataire.

* Les reprises dépendent de votre fournisseur d&#39;accès Internet et de votre réputation. Il se peut que le message ne soit pas accepté lors de la première tentative et que plusieurs reprises aient lieu. Voir [Liste des paramètres du canal Email](../../administration/using/configuring-email-channel.md).
* Un débit insuffisant peut retarder la réception de l&#39;email.

Les [Envois](../../sending/using/monitoring-a-delivery.md#sending-logs) indiquent l&#39;heure d&#39;envoi du message à chaque destinataire.

Plusieurs options sont disponibles :

* **[!UICONTROL Pas d&#39;optimisation]** : les messages sont envoyés à l&#39;heure de l&#39;utilisateur.

  Par exemple, si votre fuseau horaire est GMT+1 et que vous saisissez 9 h 00 dans le champ **[!UICONTROL Démarrer l’envoi depuis]**, un destinataire situé dans le fuseau horaire GMT+3 recevra le message à 11 h 00, heure locale, pour ce destinataire.

* **[!UICONTROL Envoyer en fonction du fuseau horaire du destinataire]** : tous les destinataires recevront le message en fonction de leur fuseau horaire.

  Par exemple, si vous saisissez 9 h 00 dans le champ **[!UICONTROL Démarrer l’envoi depuis]**, un destinataire situé dans le fuseau horaire GMT+3 recevra le message à 9 h 00, heure locale, pour ce destinataire.

  Voir [Envoi des messages au fuseau horaire du destinataire](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Envoyer à une date personnalisée définie en fonction d&#39;une formule]** : chaque destinataire recevra le message à une date et une heure calculée en fonction d&#39;une formule spécifiée.

  Voir [Calcul de la date d&#39;envoi](../../sending/using/computing-the-sending-date.md).
