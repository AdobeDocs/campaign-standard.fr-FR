---
title: Amélioration de votre réputation avec Adobe Campaign Standard
description: Découvrez comment améliorer votre réputation avec Adobe Campaign Standard en gérant les adresses électroniques en double et les mises en quarantaine.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Améliorer votre réputation{#improving-reputation}

Pour éviter d’épuiser vos destinataires, supprimez les adresses électroniques en double de votre cible. Cette étape protège votre réputation d'envoi et assure une bonne gestion de la quarantaine. Adobe Campaign offre les outils nécessaires pour mettre en oeuvre ces recommandations et éviter le risque d’être mis sur liste noire par le fournisseur de services Internet.

Vous trouverez ci-dessous des informations sur la gestion des doublons et de la quarantaine.

## Dupliquer {#duplicates}

Le fait d’avoir des adresses électroniques en double peut avoir plusieurs conséquences :
* Le même message est envoyé plusieurs fois. Même si Campaign effectue une procédure de déduplication par défaut avant l’envoi, rien n’empêche l’envoi du même message par des actions différentes ayant le même contenu lorsqu’une cible est fractionnée.
* Demandes de désabonnement non honorées. Si un destinataire se désabonne après avoir reçu un message, son profil dupliqué sera toujours éligible pour les messages futurs.

En plus de cette étape parallèle des procédures d'inclusion, cette situation conduira probablement les utilisateurs à considérer les messages comme du spam et à déclencher une procédure de liste noire au FAI.

Soyez particulièrement prudent lorsque vous effectuez des opérations sur la base de données. Pour éviter les doublons autant que possible, les actions suivantes doivent être menées:
* **Les importations doivent être soigneusement configurées.** Ceci est particulièrement important lors du choix de la clé de réconciliation.
* **Soyez attentif lors de la modification des adresses électroniques.** Les adresses électroniques modifiées peuvent également être une source de doublons. En particulier, deux adresses avec des domaines différents peuvent être acheminées vers la même boîte aux lettres, par exemple dans le cas d’une société qui a changé de nom et qui a conservé l’ancien domaine pendant une certaine période : joe.doe@amce-co.com et joe.doe@acme-rebranded.com.
* **Faites attention pendant les importations automatiques.** Qu'il s'agisse de listes ou d'autres bases de données, ce sont des éléments à prendre en compte lors de la gestion des profils. Que se passe-t-il lorsque vous supprimez ou déplacez un profil dans une autre partition ? Il peut être recréé dans la partition initiale par une importation automatique, par exemple, lorsqu’un bon de commande est placé.
* **Les profils doivent être triés dans différents dossiers.**

Il y a tous les mêmes cas où les doublons entre les différentes partitions sont normaux. Par exemple, lors d’un envoi pour des tiers ou des entités d’entreprise différentes, il est logique qu’une même personne soit un destinataire pour des raisons différentes. Il est toutefois rare de trouver des doublons dans la même partition.

## Quarantaines {#quarantines}

Adobe Campaign gère une liste d’adresses mises en quarantaine. Les destinataires dont les adresses sont mises en quarantaine sont exclus par défaut lors de l’analyse de remise : ils ne sont pas visés.

La gestion de la quarantaine est détaillée dans [cette section](../../sending/using/understanding-quarantine-management.md).

Une adresse électronique peut être mise en quarantaine, par exemple lorsque la boîte de réception est pleine ou si l’adresse n’existe pas. Dans tous les cas, la mise en quarantaine correspond aux règles spécifiques présentées dans [cette section](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
