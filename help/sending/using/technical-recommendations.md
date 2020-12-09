---
solution: Campaign Standard
product: campaign
title: Recommandations techniques de délivrabilité pour Adobe Campaign Standard
description: Découvrez quelques recommandations techniques pour améliorer la délivrabilité avec Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '465'
ht-degree: 100%

---


# Recommandations techniques{#technical-recommendations}

Un certain nombre de techniques, paramétrages et outils pour améliorer votre taux de délivrabilité sont présentés ci-dessous. Voici quelques définitions des principaux termes techniques.

**Reverse DNS** : Adobe Campaign vérifie qu&#39;un reverse DNS est bien renseigné pour une adresse IP et que celui-ci reboucle bien sur l&#39;IP.

Les **règles MX** sont utilisées pour contrôler la vitesse à laquelle le MTA (Message Transfer Agent) Campaign envoie les emails à chaque domaine d&#39;email ou FAI (ex : hotmail.com, comcast.net). Ces règles sont généralement basées sur les limites publiées par les FAI (ne pas inclure plus de 20 messages par connexion SMTP, par exemple).

**TLS** (Transport Layer Security) est un protocole de cryptage qui peut être utilisé pour sécuriser la connexion entre deux serveurs de messagerie et empêcher la lecture du contenu d&#39;un email par une autre personne que le destinataire prévu.

**SPF** (Sender Policy Framework) est une norme d&#39;authentification email qui permet au propriétaire d&#39;un domaine de spécifier quels serveurs de messagerie sont autorisés à envoyer des emails pour le compte de ce domaine. Cette norme utilise le domaine dans l&#39;en-tête &quot;Return-Path&quot; de l&#39;email (également appelé &quot;Envelope From&quot;).

L&#39;authentification **DKIM** (Domain Keys Identified Mail) est un successeur de SPF. Elle utilise la cryptographie à clé publique qui permet au serveur de messagerie de réception de vérifier qu&#39;un message a bien été envoyé par la personne ou l&#39;entité revendiquant l&#39;envoi et si le contenu du message a été modifié ou non entre le moment où il a été envoyé (et &quot;signé&quot; par DKIM) et celui où il a été reçu. Cette norme utilise généralement le domaine dans l&#39;en-tête &quot;From&quot; ou &quot;Sender&quot;.

**DMARC** (Domain-based Message Authentication, Reporting and Conformance) est la forme la plus récente d&#39;authentification email. Elle repose sur l&#39;authentification SPF et DKIM pour déterminer si un email réussit ou non l&#39;authentification. DMARC est unique et puissant pour deux raisons très importantes :
* Conformité : il permet à l’expéditeur de donner aux FAI des instructions sur les actions à exécuter sur les messages qui ne parviennent pas à s’authentifier (par exemple, ne pas l’accepter).
* Reporting : il fournit à l’expéditeur un rapport détaillé indiquant tous les messages ayant échoué lors de l’authentification DMARC, ainsi que le domaine &quot;From&quot; et l’adresse IP utilisée pour chacun. Une entreprise peut ainsi identifier un email légitime qui ne réussit pas l’authentification et qui a besoin d’une correction (par exemple, ajouter des adresses IP à son enregistrement SPF), ainsi que les sources et la prévalence des tentatives de phishing sur ses domaines de messagerie.

DMARC peut utiliser les rapports générés par 250ok.

**SMTP** (Simple mail transfer protocol) est une norme Internet pour la transmission des emails.

**Adresses IP dédiées** : Adobe fournit une stratégie IP dédiée pour chaque client avec une adresse IP en phase de montée (ramp-up) afin d’établir une réputation et d’optimiser les performances de diffusion.
