---
title: Synthèse des rebonds
description: Grâce au rapport prêt à l’emploi Synthèse des rebonds, découvrez le statut des campagnes envoyées et les erreurs qu’elles ont peut-être rencontrées.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
TQID: https://experienceleague.adobe.com/ggB-q-6kJyPF4GgJJzJGtsOqg6-7MeBhEfiGVY0M7sQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 294
ht-degree: 100%

---

# Synthèse des rebonds{#bounce-summary}

Ce rapport présente l’ensemble des erreurs relatives aux rebonds définitifs et temporaires survenues lors des diffusions ainsi que le traitement automatique des rebonds (voir la section [Compréhension des échecs de diffusion](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Chaque tableau est représenté par des nombres et des graphiques de synthèse. Les paramètres de visualisation des détails vous permettent de modifier leur affichage.

**Flop 5 des répartitions** liste les cinq diffusions présentant le plus grand nombre de mises en quarantaine :

Le tableau **Raisons des rebonds** contient les données disponibles pour les types d’erreur ayant causé des rebonds pour chaque diffusion :

* **[!UICONTROL Utilisateur inconnu]** : type d’erreur générée lors de l’envoi d’une diffusion indiquant que l’adresse email est invalide.
* **[!UICONTROL Domaine invalide]** : type d’erreur générée lors de l’envoi d’une diffusion indiquant que le domaine de l’adresse email est erroné ou n’existe plus.
* **[!UICONTROL Inatteignable]** : type d’erreur rencontrée dans la chaîne de diffusion des messages, par exemple en cas de domaine temporairement inatteignable.
* **[!UICONTROL Compte désactivé]** : type d’erreur générée lors de l’envoi d’une diffusion indiquant que l’adresse n’existe plus.
* **[!UICONTROL Boîte pleine]** : type d’erreur générée lorsque la boîte de réception du destinataire est pleine. Il y a cinq tentatives d’envoi du message avant que cette erreur soit générée.
* **[!UICONTROL Non connecté]** : type d’erreur générée lorsque le téléphone portable du destinataire est éteint ou n’est pas connecté au réseau au moment de l’envoi du message.

  >[!NOTE]
  >
  >Ce type d’erreur ne concerne que les diffusions sur les canaux mobiles.

* **[!UICONTROL Refusé]** : type d’erreur générée lorsqu’une adresse est refusée par le fournisseur d’accès Internet (FAI). Par exemple, lorsqu’une règle de sécurité a été appliquée par un logiciel anti-spam.

Le tableau **Répartition des domaines** affiche les problèmes généraux survenus au cours des diffusions, en fonction du domaine du destinataire.
