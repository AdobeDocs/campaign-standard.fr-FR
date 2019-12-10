---
title: Liste blanche dans Adobe Campaign Standard
description: Découvrez comment optimiser les listes blanches avec Adobe Campaign Standard.
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


# Listes blanches{#whitelists}

Les principaux fournisseurs de services Internet (FAI) et les fournisseurs de messagerie Web gèrent les listes blanches des expéditeurs de messages électroniques reconnus. Adobe Campaign vous aide à obtenir la certification sur les meilleures listes blanches.

Une liste blanche d’adresses électroniques est une liste d’adresses électroniques ou de noms de domaine à partir desquels un programme de blocage d’adresses électroniques permet de recevoir des messages.

Il existe deux types de listes blanches :
* Liste blanche non commerciale
* Liste blanche commerciale

## Liste blanche non commerciale {#non-commercial-whitelists}

Pour être accepté par ces listes blanches, l'expéditeur doit passer une série de tests basés sur une vérification technique (son serveur de messagerie ne doit pas être un relais ouvert mais doit avoir une adresse IP statique) de l'infrastructure ou de son activité (fréquence de remise, volume, nombre de plaintes).

Si l'expéditeur ne suit pas l'une de ces règles, il peut être supprimé de la liste blanche. Dans son pack **Adobe Campaign Email Deliverability** , Adobe Campaign propose un service de conseil d’experts associé pour le processus de certification des listes blanches non commerciales.

## Liste blanche commerciale {#commercial-whitelists}

Les listes blanches commerciales sont basées sur un système qui permet à l'expéditeur de contourner complètement les filtres anti-spam ou de se voir attribuer des points incrémentiels lorsqu'ils entrent dans le système. Ces listes blanches payantes (CPT ou sur une base annuelle) sont offertes par des systèmes tels que le Retour Path Sender Score.

Les FAI sont libres d'utiliser ces services et le nombre de FAI peut varier selon la liste blanche. Un expéditeur peut donc être plus confiant lors de l'envoi de ses messages en ayant une garantie de livraison. Certaines listes blanches permettent également d’ouvrir des images et d’activer des liens.

L’affichage dans une liste blanche est un atout indéniable pour toute campagne par courrier électronique. Dans son pack **Adobe Campaign Email Deliverability** , Adobe Campaign propose un service commercial de certification de liste blanche, tel que CSA et Retour Path Sender Score.