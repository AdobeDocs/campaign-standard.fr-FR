---
title: Amélioration de votre réputation avec Adobe Campaign Standard
description: Découvrez comment améliorer votre réputation avec Adobe Campaign Standard en gérant les adresses email en double et les mises en quarantaine.
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
translation-type: ht
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: ht
source-wordcount: '458'
ht-degree: 100%

---


# Amélioration de votre réputation{#improving-reputation}

Pour éviter d’excéder vos destinataires, supprimez les adresses email dupliquées de votre cible. Cette étape protège votre réputation d’expéditeur et assure une bonne gestion des quarantaines. Adobe Campaign dispose des outils nécessaires pour mettre en œuvre ces recommandations et éviter le risque d’être ajouté à une liste bloquée par les FAI.

Vous trouverez ci-dessous des informations sur la gestion des doublons et des quarantaines.

## Doublons {#duplicates}

L’existence de doublons pour une adresse email peut avoir plusieurs conséquences :
* Envois multiples du même message. Même si Adobe Campaign applique par défaut une déduplication sur l’adresse email avant chaque envoi, rien n’empêche d’envoyer plusieurs fois le même message par des actions différentes qui ont un même contenu lorsqu’on effectue un partage de cible.
* Non-respect de la désinscription. Si une personne se désinscrit suite à la réception d’un message, son profil en doublon sera quant à lui toujours éligible aux envois.

Outre le non-respect de l’opt-in, cette situation amènera probablement les utilisateurs à considérer les messages comme du spam et déclencher une action de placement sur liste bloquée de la part du FAI.

Il faut être particulièrement prudent lors d’opérations sur la base de données. Pour éviter le plus possible l’existence de doublons, les éléments suivants doivent être impérativement vérifiés :
* **Les imports doivent être soigneusement configurés.** Cet aspect est particulièrement important lors du choix de la clé de réconciliation.
* **Attention aux modifications d’adresses email.** Les modifications d’adresses email peuvent être source de doublons. En particulier, il peut arriver que deux adresses qui ne diffèrent que par le domaine soient routées vers la même boîte mail, par exemple dans le cas d’une société qui change de nom et qui garde un certain temps le fonctionnement des deux types d’adresse : marie.dupont@anciennesociete.com et marie.dupont@nouvellesociete.com.
* **Attention aux imports automatiques.** Les imports automatiques, qu’ils soient issus de fichiers ou d’autres bases de données, sont des éléments à prendre en compte dans les manipulations de profils. Que se passe-t-il si on supprime ou on déplace un profil dans une autre partition ? Il risque d’être recréé dans la partition initiale par un import automatique, par exemple suite au passage d’une commande.
* **Le rangement des profils dans des dossiers différents.**

Il existe tout de même des cas où la présence de doublons entre différentes partitions est normale. Par exemple, lorsqu’on opère des envois pour le compte de sociétés ou d’entités différentes, il est logique qu’une même personne puisse être adressée à des titres différents. Il est cependant rarement normal de trouver des doublons dans une même partition.

## Les quarantaines {#quarantines}

Adobe Campaign gère une liste d’adresses en quarantaine. Les destinataires dont l’adresse est en quarantaine sont par défaut exclus lors de l’analyse d’une diffusion : ils ne seront pas ciblés.

La gestion des quarantaines est présentée dans [cette section](../../sending/using/understanding-quarantine-management.md).

Une adresse email peut être mise en quarantaine par exemple lorsque la boîte de messagerie est pleine ou si l’adresse n’existe pas. Dans tous les cas, la mise en quarantaine correspond aux règles spécifiques présentées dans [cette section](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
