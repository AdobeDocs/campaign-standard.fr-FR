---
title: Profils actifs de Campaign
description: Découvrez comment accéder aux mesures et aux profils actifs des clients
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 100%

---

# Profils actifs{#active-profiles}

Les administrateurs fonctionnels de Campaign peuvent accéder au rapport **[!UICONTROL Mesures des clients]** à partir de **[!UICONTROL Administration > Mesures des clients]**.

![](assets/audience_customer_metrics.png)

Ce rapport est généré tous les mois par le workflow technique **[!UICONTROL Facturation]** et affiche le nombre de **profils actifs**.

Un &quot;Profil&quot; est un enregistrement d&#39;informations représentant un client final ou un prospect. Les profils sont considérés comme **actifs** s&#39;ils ont été ciblés par une diffusion de Campaign au cours des 12 derniers mois via un canal quelconque.

Conformément à votre contrat, chacune de vos instances Campaign est dotée d&#39;un nombre spécifique de profils actifs. Consultez votre Accord de licence pour connaître le nombre de profils actifs achetés.

![](assets/audience_active_profiles_list.png)



* Les profils qui ont été exclus pendant la préparation de la diffusion (en raison de règles de typologie ou d&#39;un mécanisme de quarantaine, par exemple) ne sont pas pris en compte.

* Les destinataires des messages transactionnels sont comptabilisés dans les profils actifs.

* Un profil qui a été ciblé par plusieurs diffusions n&#39;est comptabilisé qu&#39;une seule fois.

* Ce rapport est fourni uniquement à titre d&#39;information. Il n&#39;a aucune incidence directe sur la facturation.

Au bas de la page, les dimensions de ciblage sont répertoriées avec le nombre de profils pour chacune d&#39;elles. Les destinataires des messages transactionnels sont associés à la dimension **Anonyme** .

>[!NOTE]
>
>En tant qu&#39;utilisateur administrateur, vous pouvez également surveiller le nombre de profils actifs utilisés sur vos instances directement depuis le panneau de contrôle. Pour plus d’informations, consultez la [documentation du panneau de contrôle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=fr).
