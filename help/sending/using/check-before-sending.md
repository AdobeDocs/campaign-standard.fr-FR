---
title: Vérification avant envoi
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Une fois votre message prêt, apprenez à effectuer toutes les vérifications avant l’envoi
feature: Deliverability
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 96%

---

# Effectuer toutes les vérifications avant d’envoyer {#perform-all-checks}

Une fois que votre message est prêt, vérifiez que le contenu s&#39;affiche correctement sur tous les appareils et qu&#39;il ne contient aucune erreur, comme des liens rompus ou une personnalisation incorrecte.

Avant d’envoyer votre message, vérifiez également que les paramètres et la configuration sont cohérents par rapport à la diffusion.

## Pourquoi la validation est-elle essentielle ?  {#validation-is-key}

Avant d&#39;envoyer une diffusion, vous devez vous assurer que vos destinataires recevront le message que vous souhaitez réellement leur envoyer. Pour cela, vous devez valider le contenu du message et les paramètres de diffusion.

Cette étape vous permet de détecter les éventuelles erreurs et de les corriger avant l’envoi à la cible principale.

Les étapes de validation d&#39;une diffusion sont présentées [dans cette section](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Rendu des e-mails {#email-rendering}

Avant d&#39;appuyer sur le bouton **[!UICONTROL Envoyer]**, vérifiez que l&#39;affichage de votre message sera optimal sur divers clients web, webmails et appareils.

Pour vous aider, Adobe Campaign capture le rendu et le rend disponible dans un rapport dédié. Vous pouvez visualiser l&#39;affichage du message envoyé dans les différents contextes de réception.

**Conseils** :

* Vous pouvez visualiser l&#39;affichage du message envoyé dans les différents contextes de réception : webmail, service de messagerie, mobile, etc.

* Les fonctionnalités de rendu des e-mails sont essentielles pour déterminer si vos campagnes par e-mail réussissent à passer les filtres des principaux FAI et des services webmail. Les outils de ce type envoient une copie de vérification d’un e-mail à un réseau de boîtes de réception de test pour que vous puissiez voir comment le message s’affichera à travers ces différents services. Ils peuvent également inclure des rapports et des options de correction de code qui vous permettent d’identifier rapidement les problèmes et de les corriger afin d’améliorer la délivrabilité.

En savoir plus [dans cette section](../../sending/using/email-rendering.md).

## Messages de BAT {#proof-messages}

L’envoi de BAT permet de vérifier le lien d’exclusion, la page miroir et d’autres liens, de valider le message, de vérifier le bon affichage des images, de détecter les erreurs possibles, etc. Vous souhaiterez peut-être également vérifier votre conception et le rendu sur différents appareils.

En savoir plus à ce sujet dans [cette section](../../sending/using/sending-proofs.md).

## Configurer des diffusions avec test A/B {#a-b-testing-deliveries}

Si vous disposez de plusieurs contenus pour une diffusion email, vous pouvez utiliser des tests A/B pour déterminer quelle version aura le plus d&#39;impact sur la population ciblée.

**Conseils** :

* Envoyez les différentes versions à une partie de vos destinataires.

* Choisissez la version qui a eu le plus de succès et envoyez-la au reste de vos destinataires.

En savoir plus à ce sujet dans [cette section](../../channels/using/designing-an-a-b-test-email.md).
