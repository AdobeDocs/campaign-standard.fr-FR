---
title: Vérification avant envoi
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: true
description: Une fois que votre message est prêt, découvrez comment effectuer toutes les vérifications avant de l’envoyer.
feature: Deliverability
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
TQID: https://experienceleague.adobe.com/3qM5opRzD4u8HV5PALkfERzsLnWx1AsLuaDs8frG-Ic
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 413
ht-degree: 100%

---

# Effectuer toutes les vérifications avant d’envoyer {#perform-all-checks}

Une fois que votre message est prêt, vérifiez que le contenu s&#39;affiche correctement sur tous les appareils et qu&#39;il ne contient aucune erreur, comme des liens rompus ou une personnalisation incorrecte.

Avant d’envoyer votre message, vérifiez également que les paramètres et la configuration sont cohérents par rapport à la diffusion.

## Pourquoi la validation est-elle essentielle ? {#validation-is-key}

Avant d’envoyer une diffusion, vous devez vous assurer que vos destinataires recevront le message que vous souhaitez réellement leur envoyer. Pour cela, vous devez valider le contenu du message et les paramètres de diffusion.

Cette étape vous permet de détecter les éventuelles erreurs et de les corriger avant l’envoi à la cible principale.

Les étapes de validation d&#39;une diffusion sont présentées [dans cette section](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Rendu des e-mails {#email-rendering}

Avant d&#39;appuyer sur le bouton **[!UICONTROL Envoyer]**, vérifiez que l&#39;affichage de votre message sera optimal sur divers clients web, webmails et appareils.

Pour permettre cette opération, Adobe Campaign capture le rendu et le rend disponible dans un rapport dédié. Vous pouvez ainsi prévisualiser le message envoyé dans les différents contextes de réception.

**Conseils** :

* Vous pouvez visualiser l&#39;affichage du message envoyé dans les différents contextes de réception : webmail, service de messagerie, mobile, etc.

* Les fonctionnalités de rendu des e-mails sont essentielles pour déterminer si vos campagnes par e-mail réussissent à passer les filtres des principaux FAI (fournisseurs d’accès Internet) et services de messagerie web. Ces outils envoient une copie de pré-contrôle d’un e-mail à un réseau de boîtes de réception de test, afin de vérifier comment le message s’affichera, ou sera rendu, sur ces services. Ils peuvent également inclure des rapports et des options de correction de code qui vous aident à identifier et à corriger rapidement les erreurs, afin d’améliorer la délivrabilité.

En savoir plus [dans cette section](../../sending/using/email-rendering.md).

## Messages de BAT {#proof-messages}

L’envoi de BAT permet de vérifier le lien d’exclusion, la page miroir et d’autres liens, de valider le message, de vérifier le bon affichage des images, de détecter les erreurs possibles, etc. Vous souhaiterez peut-être également vérifier votre conception et le rendu sur différents appareils.

En savoir plus à ce sujet dans [cette section](../../sending/using/sending-proofs.md).

## Configurer des diffusions avec test A/B {#a-b-testing-deliveries}

Si vous disposez de plusieurs contenus pour une diffusion email, vous pouvez utiliser des tests A/B pour déterminer quelle version aura le plus d&#39;impact sur la population ciblée.

**Conseils** :

* Envoyez les différentes versions à une partie de vos destinataires.

* Choisissez la version qui a eu le plus de succès et envoyez-la au reste de vos destinataires.

En savoir plus dans [cette section](../../channels/using/designing-an-a-b-test-email.md).
