---
title: Modifications à venir du canal de notification push
description: Modifications à venir du canal de notification push
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: 6d1a5cb1d467d7d74fe41e66125fe0fcbf2e3d9b
workflow-type: ht
source-wordcount: '427'
ht-degree: 100%

---

# Modifications à venir du canal de notification push {#push-upgrade}

Il existe d’importantes mises à jour concernant les modifications à venir du canal de notification push sur les appareils Android et iOS. Notez que ces dernières sont susceptibles d’avoir un impact sur votre mise en œuvre d’Adobe Campaign Standard.

## Android {#push-android}

Dans le cadre des efforts continus de Google pour améliorer ses services, des modifications ont été apportées au [protocole HTTP Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/http-server-ref). Par conséquent, les API héritées HTTP de Firebase Cloud Messaging, obsolètes depuis le 20 juin 2023, seront remplacées par des API HTTP v1 en juin 2024.

Actuellement, Adobe Campaign Standard utilise des API héritées HTTP pour envoyer des messages de notification push Android. Des modifications seront toutefois apportées dans les prochains mois pour effectuer une mise à niveau vers les API HTTP v1. Des informations supplémentaires sur ces modifications seront fournies au fur et à mesure qu’Adobe effectuera ces mises à jour.

## iOS {#push-ios}

Adobe mettra également à niveau Adobe Campaign Standard pour le canal de notification push iOS et modifiera la manière dont les administrateurs et les administratrices pourront configurer les certificats pour leurs applications iOS. Les administrateurs et administratrices devront dorénavant charger les certificats iOS via l’interface utilisateur d’Adobe Campaign Standard.

Nous comprenons que vous, notre clientèle, comptez sur ces services pour vos campagnes marketing et vos besoins en communication. C’est pourquoi nous voulons nous assurer que vous disposez des bonnes informations sur nos plans et sur notre assistance en cours.

## Que faisons-nous ?

* **Modifications du produit** : nous travaillons sur les modifications du produit afin de prendre en charge les mises à niveau techniques de la pile dans le canal de notification push Android/iOS.

* **Instructions détaillées** : nous fournissons des guides détaillés et d’autres ressources pour faciliter le processus de transition.

* **Assistance** : notre équipe d’assistance clientèle sera à votre disposition pour vous aider tout au long de cette transition. Nous pouvons également animer des webinaires et des sessions d&#39;activation pour couvrir les aspects techniques et les bonnes pratiques de la transition.

## En quoi nos actions vous affectent-elles ?

* **Restez informé** : gardez un œil sur votre boîte de réception pour toute communication supplémentaire de notre part, y compris le plan de transition détaillé.

* **Vérification de votre configuration actuelle** : prenez le temps de passer en revue votre configuration et votre personnalisation actuelles dans Adobe Campaign Standard, afin de pouvoir apporter les modifications nécessaires, le cas échéant.

* **Contactez-nous** : si vous avez des questions ou des préoccupations immédiates, n’hésitez pas à contacter notre équipe d’assistance.

## Étapes suivantes

Au cours des prochaines semaines, nous partagerons plus de détails sur les modifications prévues pour le canal push pour Android/iOS, y compris le calendrier et les éléments d’action. Notre principal objectif est de rendre cette transition aussi transparente que possible pour vous et votre équipe.

Nous vous remercions de votre compréhension, à mesure que nous nous adaptons à ces changements. Votre succès est notre priorité, et nous nous engageons à vous soutenir à chaque étape.