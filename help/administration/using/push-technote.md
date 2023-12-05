---
title: Modifications à venir du canal de notification push
description: Modifications à venir du canal de notification push
audience: channels
feature: Push
role: Admin
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: 9b7b127d92628169249c64ce85147d530b32a2cc
workflow-type: ht
source-wordcount: '325'
ht-degree: 100%

---

# Modifications à venir du canal de notification push {#push-upgrade}

Vous pouvez utiliser Campaign pour envoyer des notifications push sur les appareils Android et iOS. Pour ce faire, Campaign repose sur des services d’abonnement spécifiques. Certaines modifications importantes apportées au service Android FCM (Firebase Cloud Messaging) seront publiées en 2024 et auront une incidence sur votre mise en œuvre d’Adobe Campaign. En outre, pour les applications iOS, Adobe modifie la manière dont les administrateurs ou administratrices peuvent configurer les certificats.

## Qu’est-ce qui a changé ? {#push-changes}

### Android {#push-android}

Dans le cadre des efforts constants de Google pour améliorer ses services, les API FCM héritées seront abandonnées le **20 juin 2024**. Pour en savoir plus sur le protocole HTTP Firebase Cloud Messaging, consultez la [documentation de Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Actuellement, Adobe Campaign Standard utilise des API héritées HTTP pour envoyer des messages de notification push Android. Des modifications seront toutefois apportées dans les prochains mois pour effectuer une mise à niveau vers les API HTTP v1.

### iOS {#push-ios}

Adobe mettra également à niveau Adobe Campaign Standard pour le canal de notification push iOS et modifiera la manière dont les administrateurs et les administratrices pourront configurer les certificats pour leurs applications iOS. Les administrateurs et administratrices devront dorénavant charger les certificats iOS via l’interface utilisateur d’Adobe Campaign Standard.

## Cela vous concerne-t-il ? {#push-impact}

En tant qu’utilisateur ou utilisatrice de Campaign Standard, si vous envoyez des messages de notification push à vos audiences, cela vous concerne.

## Migrer vers Adobe Developer Console {#push-migration}

Ces mises à jour nécessitent une mise à niveau de la version de Campaign Standard, car elles ont un impact sur la configuration du canal mobile et la gestion des autorisations.

Des instructions détaillées seront fournies sous peu afin de faciliter le processus de transition.

Notre équipe d’assistance clientèle sera à votre disposition pour vous aider tout au long de cette transition. Nous pouvons également animer des webinaires et des sessions d&#39;activation pour couvrir les aspects techniques et les bonnes pratiques de la transition.

Avant cela, prenez le temps de passer en revue votre configuration et votre personnalisation actuelles dans Adobe Campaign Standard, afin de pouvoir apporter les modifications nécessaires, le cas échéant.

Si vous avez des questions ou des préoccupations dès maintenant, n’hésitez pas à contacter notre équipe d’assistance.