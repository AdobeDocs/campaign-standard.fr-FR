---
title: Les processus d’inscription et de désinscription dans Campaign
seo-title: Les processus d’inscription et de désinscription dans Campaign
description: Les processus d’inscription et de désinscription dans Campaign
seo-description: Le blacklistage (opt-out) entraîne la fin du ciblage d’un profil par n’importe quelle diffusion ou des diffusions d’un canal spécifique.
page-status-flag: never-activated
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Les processus d’inscription et de désinscription dans Campaign{#about-opt-in-and-opt-out-in-campaign}

Le blacklistage (opt-out) entraîne la fin du ciblage d’un profil par n’importe quelle diffusion ou des diffusions d’un canal spécifique.

Pour que les profils puissent être inscrits ou désinscrits, vous devez créer une landing page dédiée. Pour en savoir plus à ce sujet, consultez [Configuration des landing pages d’inscription et de désinscription](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Les profils peuvent également être inscrits ou désinscrits manuellement par un opérateur. Pour en savoir plus à ce sujet, consultez [Gestion des inscriptions et désinscriptions dans un profil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Les profils blacklistés sont automatiquement exclus pendant l’analyse des diffusions afin d’accélérer ces dernières (le taux d’erreur a un effet non négligeable sur la vitesse de diffusion).

>[!NOTE]
>
>Le blacklistage s’applique aux **Profils**, contrairement à la quarantaine qui est liée à une **adresse email** ou un **numéro de téléphone**. Si un profil est blacklisté, toutes les adresses qui y sont liées sont donc exclues des diffusions. Si un utilisateur possède deux profils dans la base de données, il sera toujours ciblé par les diffusions, car seul un de ses profils est blacklisté. Pour s'assurer que toutes ses adresses sont exclues, ajoutez-les aux adresses mises en quarantaine. Voir à ce propos [cette page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Pour plus d’informations sur les abonnements aux services, consultez [cette page](../../audiences/using/about-subscriptions.md).
