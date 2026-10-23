---
title: À propos des processus d’opt-in et d’opt-out dans Campaign
description: L’opt-out entraîne la fin du ciblage d’un profil par n’importe quelle diffusion ou des diffusions d’un canal spécifique.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
TQID: 'https://experienceleague.adobe.com/9fzQiPrBRAFlTxX5EKo-Qvph3nYZYoA29kMrm6cXVLs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 100%
---
# À propos des processus d’opt-in et d’opt-out dans Campaign{#about-opt-in-and-opt-out-in-campaign}

L’opt-out entraîne la fin du ciblage d’un profil par n’importe quelle diffusion ou des diffusions d’un canal spécifique.

Pour que les utilisateurs et utilisatrices puissent donner leur opt-in ou opt-out, vous devez créer une page de destination dédiée. Pour en savoir plus à ce sujet, consultez [Configuration des landing pages d&#39;opt-in et d’opt-out](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Les profils peuvent également être inclus ou exclus manuellement par un opérateur. Pour en savoir plus à ce sujet, consultez [Gestion des opt-in et opt-out dans un profil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Les profils exclus sont automatiquement exclus pendant l&#39;analyse des diffusions afin d&#39;accélérer ces dernières (le taux d&#39;erreur a un effet non négligeable sur la vitesse de diffusion).

>[!NOTE]
>
>L’opt-out s&#39;applique aux **Profils**, contrairement à la quarantaine qui est liée à une **adresse email** ou un **numéro de téléphone**. Si un profil est exclu, toutes les adresses qui y sont liées sont donc exclues des diffusions. Cependant, si un utilisateur possède deux profils dans la base de données, il sera toujours ciblé par les diffusions, car seul un de ses profils est exclu. Pour s’assurer que toutes ses adresses sont exclues, ajoutez-les aux adresses mises en quarantaine. Pour plus d’informations, consultez [cette page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Pour plus d&#39;informations sur les abonnements aux services, consultez [cette page](../../audiences/using/about-subscriptions.md).
