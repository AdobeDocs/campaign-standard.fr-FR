---
solution: Campaign Standard
product: campaign
title: Synthèse des bounces
description: Grâce au rapport d’usine Synthèse des bounces, découvrez le statut des campagnes envoyées et les erreurs qu’elles ont peut-être rencontrées.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Directeur
level: Intermédiaire
translation-type: ht
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: ht
source-wordcount: '292'
ht-degree: 100%

---


# Synthèse des bounces{#bounce-summary}

Ce rapport présente l’ensemble des statistiques d’erreurs hard et soft survenues lors des diffusions ainsi que le traitement automatique des retours (voir la section [Compréhension des échecs de diffusion](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Chaque tableau est représenté par des nombres et des graphiques de synthèse. Les paramètres de visualisation des détails vous permettent de modifier leur affichage.

**Flop 5 des répartitions** liste les cinq diffusions présentant le plus grand nombre de mises en quarantaine :

Le tableau **Raisons de bounce** contient les données disponibles pour les types d’erreur ayant causé des bounces pour chaque diffusion :

* **[!UICONTROL Utilisateur inconnu]** : type d’erreur générée lors de l’envoi d’une diffusion indiquant que l’adresse email est invalide.
* **[!UICONTROL Domaine invalide]** : type d’erreur générée lors de l’envoi d’une diffusion indiquant que le domaine de l’adresse email est erroné ou n’existe plus.
* **[!UICONTROL Inatteignable]** : type d’erreur rencontrée dans la chaîne de diffusion des messages, par exemple en cas de domaine temporairement inatteignable.
* **[!UICONTROL Compte désactivé]** : type d’erreur générée lors de l’envoi d’une diffusion indiquant que l’adresse n’existe plus.
* **[!UICONTROL Boîte pleine]** : type d’erreur générée lorsque la boîte de réception du destinataire est pleine. Il y a cinq tentatives d’envoi du message avant que cette erreur soit générée.
* **[!UICONTROL Non connecté]** : type d’erreur générée lorsque le téléphone portable du destinataire est éteint ou n’est pas connecté au réseau au moment de l’envoi du message.

   >[!NOTE]
   >
   >Ce type d’envoi ne concerne que les diffusions sur les canaux mobiles.

* **[!UICONTROL Refusé]** : type d’erreur générée lorsqu’une adresse est refusée par le fournisseur d’accès Internet (FAI). Par exemple, lorsqu’une règle de sécurité a été appliquée par un logiciel anti-spam.

Le tableau **Répartition des domaines** affiche les problèmes généraux survenus au cours des diffusions, en fonction du domaine du destinataire.
