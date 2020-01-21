---
title: Listes blanches dans Adobe Campaign Standard
description: Découvrez comment optimiser les listes blanches avec Adobe Campaign Standard.
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
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Listes blanches{#whitelists}

Les principaux fournisseurs d’accès internet (FAI) et gestionnaires de Web mails gèrent des listes blanches (whitelists) d’expéditeurs reconnus de messages emails. Adobe Campaign vous accompagne dans le processus de certification auprès des meilleures listes blanches.

Une liste blanche d’emails est une liste d’adresses email ou de noms de domaine à partir de laquelle un programme de blocage d’emails permettra la réception des messages.

Deux types de listes blanches existent :
* Listes blanches non commerciales
* Listes blanches commerciales

## Listes blanches non commerciales {#non-commercial-whitelists}

Pour être accepté sur ces listes blanches, l’expéditeur doit passer une série de tests basés sur une vérification technique de l’infrastructure (son serveur d’email ne doit pas être un relais ouvert et avoir un IP statique) ou bien de son activité (fréquence d’envoi, volume, nombre de plaintes).

Si l’expéditeur déroge à l’une de ces règles, il peut être supprimé de la liste blanche. Dans le cadre de son offre **Adobe Campaign Email Deliverability**, Adobe Campaign propose un service de conseil et d’accompagnement dans le processus de certification pour les listes blanches non commerciales.

## Listes blanches commerciales {#commercial-whitelists}

Les listes blanches commerciales sont basées sur un système qui permet à un expéditeur de passer les filtres anti-spam ou d’avoir un bonus en entrant dans le système antispam. Ces listes blanches payantes (CPT ou sur une base annuelle) sont offertes par des systèmes tels que le Return Path Sender Score.

Les FAI sont libres d’utiliser ces services et le nombre de FAI est variable selon la liste blanche. Un expéditeur peut alors être plus confiant lors de l’envoi de ses messages en ayant une garantie de livraison. Certaines listes blanches offrent également l’ouverture des images et l’activation des liens.

Le fait de figurer sur une liste blanche est un atout indéniable dans le cadre de toute campagne email. Dans son offre **Adobe Campaign Email Deliverability**, Adobe Campaign propose un service de certification pour les listes blanches commerciales, telles que CSA et Return Path Sender Score.