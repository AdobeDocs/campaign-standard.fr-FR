---
title: Profils actifs de Campaign
description: Découvrez comment accéder aux mesures et aux profils actifs des clients
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
TQID: 'https://experienceleague.adobe.com/XKRIP6jfP3ROPWTN4moJKsBLQcRqmR3gSWZ-hi5P8I4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 100%
---
# Profils actifs{#active-profiles}

Vous pouvez accéder aux détails des profils actifs à partir du rapport **[!UICONTROL Mesures des clients]**. Ce rapport est disponible uniquement pour les administrateurs fonctionnels et les administratrices fonctionnelles de Campaign. Pour accéder à ce rapport, cliquez sur l’icône Adobe Campaign en haut à gauche de l’[interface utilisateur](../../start/using/interface-description.md#advanced-menu) et accédez à **[!UICONTROL Administration > Mesures des clients]**.

![](assets/audience_customer_metrics.png)

Ce rapport est généré tous les mois par le workflow technique **[!UICONTROL Facturation]** et affiche le nombre de **profils actifs**. Découvrez-en plus sur les workflows techniques en accédant à [cette page](../../administration/using/technical-workflows.md).

Un &quot;Profil&quot; est un enregistrement d&#39;informations représentant un client final ou un prospect. Les profils sont considérés comme **actifs** s&#39;ils ont été ciblés par une diffusion de Campaign au cours des 12 derniers mois via un canal quelconque.

Conformément à votre contrat, chacune de vos instances Campaign est dotée d&#39;un nombre spécifique de profils actifs. Consultez votre Accord de licence pour connaître le nombre de profils actifs achetés.

![](assets/audience_active_profiles_list.png)



* Les profils qui ont été exclus pendant la préparation de la diffusion (en raison de règles de typologie ou d&#39;un mécanisme de quarantaine, par exemple) ne sont pas pris en compte.

* Les destinataires des messages transactionnels sont comptabilisés dans les profils actifs.

* Un profil qui a été ciblé par plusieurs diffusions n&#39;est comptabilisé qu&#39;une seule fois.

* Ce rapport est fourni uniquement à titre d&#39;information. Il n&#39;a aucune incidence directe sur la facturation.

Au bas de la page, les dimensions de ciblage sont répertoriées avec le nombre de profils pour chacune d’elles. Les destinataires des messages transactionnels sont associés à la dimension **Anonyme** .

>[!NOTE]
>
>En tant qu&#39;utilisateur administrateur, vous pouvez également surveiller le nombre de profils actifs utilisés sur vos instances directement depuis le Panneau de contrôle. Pour plus d’informations, consultez la [documentation du Panneau de contrôle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=fr).
>
