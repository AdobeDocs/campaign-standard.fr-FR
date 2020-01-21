---
title: Recommandations techniques de délivrabilité pour Adobe Campaign Standard
description: Découvrez quelques recommandations techniques pour améliorer la délivrabilité avec Adobe Campaign Standard.
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


# Recommandations techniques{#technical-recommendations}

En complément, plusieurs techniques, paramétrages et outils pour améliorer votre taux de délivrabilité sont présentés ci-dessous.

Voici quelques définitions des principaux termes techniques.

**Reverse DNS**
Adobe Campaign vérifie qu’un reverse DNS est bien renseigné pour une adresse IP et que celui-ci reboucle bien sur l’IP.

**Règles MX**
Les règles MX servent à contrôler la vitesse d’envoi des emails par le MTA (Message Transfer Agent) de Campaign à chaque domaine d’email ou de FAI (par exemple, hotmail.com, comcast.net). Ces règles sont généralement basées sur les limites publiées par les FAI (par exemple, ne pas inclure plus de 20 messages par connexion SMTP).

**TLS**
(Transport Layer Security) est un protocole de cryptage qui peut être utilisé pour sécuriser la connexion entre deux serveurs de messagerie et empêcher la lecture du contenu d’un email par une autre personne que le destinataire prévu.

**SPF**
SPF (Sender Policy Framework) est une norme d’authentification d’email qui permet au propriétaire d’un domaine de spécifier les serveurs de messagerie autorisés à envoyer des emails pour le compte de ce domaine. Cette norme utilise le domaine indiqué dans l’en-tête « Return-Path » de l’email (également appelé adresse « Envelope From »).

**DKIM**
L’authentification DKIM (Domain Keys Identified Mail) est un successeur de SPF. Elle utilise la cryptographie à clé publique qui permet au serveur de messagerie de réception de vérifier qu’un message a bien été envoyé par la personne ou l’entité revendiquant l’envoi et si le contenu du message a été modifié ou non entre le moment où il a été envoyé (et « signé » par DKIM) et celui où il a été reçu. Cette norme utilise généralement le domaine dans l’en-tête « From » ou « Sender ».

**DMARC** DMARC (Domain-based Message Authentication, Reporting and Conformance) est la forme la plus récente d’authentification des emails. Le processus s’appuie simultanément sur l’authentification SPF et DKIM pour déterminer si un email sera diffusé avec succès ou non. DMARC est sans équivalent et puissant pour deux raisons très importantes :
* Conformité : il permet à l’expéditeur de donner aux FAI des instructions sur les actions à exécuter sur les messages qui ne parviennent pas à s’authentifier (par exemple, ne pas l’accepter).
* Reporting : il fournit à l’expéditeur un rapport détaillé indiquant tous les messages ayant échoué lors de l’authentification DMARC, ainsi que le domaine &quot;From&quot; et l’adresse IP utilisée pour chacun. Une entreprise peut ainsi identifier un email légitime qui ne réussit pas l’authentification et qui a besoin d’une correction (par exemple, ajouter des adresses IP à son enregistrement SPF), ainsi que les sources et la prévalence des tentatives de phishing sur ses domaines de messagerie.

DMARC peut utiliser les rapports générés par 250ok.

**SMTP**
SMTP (Simple mail transfer protocol) est une norme Internet pour la transmission des emails.

**Adresses IP dédiées**
Adobe fournit une stratégie IP dédiée pour chaque client avec une adresse IP en phase de montée (ramp-up) afin d’établir une réputation et optimiser les performances de diffusion.
