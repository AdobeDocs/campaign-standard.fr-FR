---
title: Recommandations techniques de délivrabilité pour Adobe Campaign Standard
description: Découvrez quelques recommandations techniques pour améliorer la délivrabilité avec Adobe Campaign Standard.
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


# Recommandations techniques{#technical-recommendations}

En outre, plusieurs techniques, configurations et outils que vous pouvez utiliser pour améliorer le taux de délivrabilité sont répertoriés ci-dessous.

Voici quelques définitions des principaux termes techniques.

**Inverser DNS** Adobe Campaign vérifie si un DNS inversé est donné pour une adresse IP et si cela renvoie correctement à l’adresse IP.

**Règles** MX Les règles MX permettent de contrôler la vitesse à laquelle l’agent de transfert de messages de la campagne envoie des courriers électroniques à chaque domaine de courriel ou FAI (par exemple, hotmail.com, comcast.net). Ces règles sont généralement basées sur les limites publiées par les FAI (par exemple, ne pas inclure plus de 20 messages par connexion SMTP).

**TLS** TLS (Transport Layer Security) est un protocole de chiffrement qui permet de sécuriser la connexion entre deux serveurs de messagerie et de protéger le contenu d'un courrier électronique contre toute lecture par un tiers que les destinataires prévus.

**SPF** SPF (Sender Policy Framework) est une norme d’authentification de courriel qui permet au propriétaire d’un domaine de spécifier les serveurs de messagerie autorisés à envoyer du courrier électronique pour le compte de ce domaine. Cette norme utilise le domaine dans l’en-tête "Chemin de retour" du courrier électronique (également appelé adresse "Enveloppe de").

**L’authentification DKIM** DKIM (Domain Keys Identified Mail) est un successeur de SPF et utilise la cryptographie à clé publique qui permet au serveur de messagerie de réception de vérifier qu’un message a bien été envoyé par la personne ou l’entité qui prétend l’avoir envoyé, et si le contenu du message a été modifié entre le moment où il a été envoyé (et celui où DKIM a été "signé") et le moment où il a été reçu. Cette norme utilise généralement le domaine dans l’en-tête "De" ou "Expéditeur".

**DMARC** DMARC (Authentification, création de rapports et conformité des messages basés sur le domaine) est la forme la plus récente d’authentification par courrier électronique. Il s’appuie sur l’authentification SPF et DKIM pour déterminer si un courrier électronique réussit ou échoue. DMARC est unique et puissant de deux manières très importantes :
* Conformité - permet à l'expéditeur d'indiquer aux FAI ce qu'il doit faire de tout message qui ne s'authentifie pas (par exemple, ne l'accepte pas).
* Création de rapports : fournit à l’expéditeur un rapport détaillé montrant tous les messages qui ont échoué à l’authentification DMARC, ainsi que le domaine "De" et l’adresse IP utilisés pour chacun d’eux. Cela permet à une entreprise d’identifier les courriers électroniques légitimes qui échouent à l’authentification et qui nécessitent un certain type de "correctif" (par exemple l’ajout d’adresses IP à leur enregistrement SPF), ainsi que les sources et la prévalence des tentatives d’hameçonnage sur leurs domaines de courriel.

DMARC peut exploiter les rapports générés par 250ok.

**SMTP** SMTP (Simple Mail Transfer Protocol) est une norme Internet pour la transmission des e-mails.

**Les adresses IP** dédiées Adobe fournit une stratégie IP dédiée à chaque client disposant d’une adresse IP commutée afin de construire une réputation et d’optimiser les performances de livraison.
