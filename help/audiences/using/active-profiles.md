---
solution: Campaign Standard
product: campaign
title: Profils Principaux
description: Découvrez comment accéder aux mesures et aux profils principaux des clients
feature: Profils
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d2fcf2ca22bb5fe3632280f922dfed0972f6eb09
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 26%

---

# Mesures des clients {#customer-metrics}

Les administrateurs fonctionnels de Campaign peuvent accéder au rapport **[!UICONTROL Mesures du client]** à partir de **[!UICONTROL Administration > Mesures du client]**.

![](assets/audience_active_profiles1.png)

Ce rapport affiche :

* l’ID d’Experience Cloud
* ID d’organisation IMS
* le nombre de **profils principaux**
* liste des dimensions de ciblage disponibles dans l&#39;instance

Ce rapport est généré chaque mois par le workflow technique de **[!UICONTROL facturation.]**

## Profils actifs{#active-profiles}

Conformément à votre contrat, chacune de vos instances Campaign est configurée avec un nombre spécifique de profils principaux. Veuillez consulter votre contrat de licence pour connaître le nombre de profils principaux achetés.

>[!NOTE]
>
>En tant qu’utilisateur administrateur, vous pouvez également surveiller le nombre de profils principaux utilisés sur vos instances directement à partir du Panneau de Contrôle. Pour plus d’informations à ce sujet, consultez la [documentation du panneau de contrôle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=fr).


Un &quot;Profil&quot; est un enregistrement d’informations représentant un client final, une prospect ou un prospect. Les profils sont considérés comme **principaux** s&#39;ils ont été ciblés par une diffusion de Campaign au cours des 12 derniers mois par un canal quelconque. Les profils qui ont été exclus pendant la préparation de la diffusion (par règle de typologie ou mécanisme de quarantaine, par exemple) ne sont pas pris en compte. Un profil qui a été ciblé par plusieurs diffusions n’est comptabilisé qu’une seule fois. Ce rapport est fourni uniquement à titre d’information ; il n’a aucune incidence directe sur la facturation.

![](assets/audience_active_profiles2.png)

La partie inférieure du rapport contient la liste des profils actifs pour chaque dimension de ciblage. Il indique le nombre de principaux profils ciblés au cours de la période variable des 12 derniers mois.

* La source **[!UICONTROL NmsRecipient]** comprend tous les profils qui ont été contactés à l&#39;aide de l&#39;information provenant de leur profil Campaign Standard.

* La source **[!UICONTROL anonyme]** des clients indique le nombre de profils ciblés à l’aide d’une information spécifique uniquement (adresse électronique, numéro de téléphone), sans rapport avec leur profil Campaign.
