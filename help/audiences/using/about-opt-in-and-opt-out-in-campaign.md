---
solution: Campaign Standard
product: campaign
title: À propos des processus d’opt-in et d’opt-out dans Campaign
description: L’opt-out entraîne la fin du ciblage d’un profil par n’importe quelle diffusion ou des diffusions d’un canal spécifique.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 100%

---


# À propos des processus d’opt-in et d’opt-out dans Campaign{#about-opt-in-and-opt-out-in-campaign}

L’opt-out entraîne la fin du ciblage d’un profil par n’importe quelle diffusion ou des diffusions d’un canal spécifique.

Pour que les profils puissent être inclus ou exclus, vous devez créer une landing page dédiée. Pour en savoir plus à ce sujet, consultez [Configuration des landing pages d&#39;opt-in et d’opt-out](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Les profils peuvent également être inclus ou exclus manuellement par un opérateur. Pour en savoir plus à ce sujet, consultez [Gestion des opt-in et opt-out dans un profil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Les profils exclus sont automatiquement exclus pendant l&#39;analyse des diffusions afin d&#39;accélérer ces dernières (le taux d&#39;erreur a un effet non négligeable sur la vitesse de diffusion).

>[!NOTE]
>
>L’opt-out s&#39;applique aux **Profils**, contrairement à la quarantaine qui est liée à une **adresse email** ou un **numéro de téléphone**. Si un profil est exclu, toutes les adresses qui y sont liées sont donc exclues des diffusions. Si un utilisateur possède deux profils dans la base de données, il sera toujours ciblé par les diffusions, car seul un de ses profils est exclu. Pour s&#39;assurer que toutes ses adresses sont exclues, ajoutez-les aux adresses mises en quarantaine. Voir à ce propos [cette page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Pour plus d&#39;informations sur les abonnements aux services, consultez [cette page](../../audiences/using/about-subscriptions.md).
