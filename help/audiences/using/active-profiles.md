---
title: Profils actifs
description: Vous pouvez accéder à un rapport dédié sur les mesures des clients et visualiser les profils actifs dans la base de données de Campaign.
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c1147c4512b1485ae5d927a32970adcd41b540e7
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 43%

---


# Profils actifs{#active-profiles}

Adobe Campaign contient un rapport qui indique le nombre de profils actifs. Ce rapport est fourni uniquement à titre d’information ; il n’a aucune incidence directe sur la facturation. Seuls les administrateurs y ont accès, sous **[!UICONTROL Administration > Mesures des clients]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Si vous êtes hébergé sur AWS et que vous utilisez Campaign Standard à partir du build 10368, vous pouvez également surveiller le nombre de profils actifs utilisés sur vos instances directement depuis le panneau de contrôle. Pour plus d’informations à ce sujet, consultez la [documentation du Panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>Notez que la mesure profils Principaux est disponible et n’est utile que pour les instances **de** marketing. Il n&#39;est ni applicable ni disponible pour les Instances d&#39;exécution, c&#39;est-à-dire les instances MID (mid-sourcing) et RT (Message Center / Real-time messaging).


Les profils qui ont été exclus pendant la préparation de la diffusion (règles de typologie, quarantaines, Populations témoins) ne sont pas pris en compte. Un profil qui a été ciblé par plusieurs diffusions n&#39;est comptabilisé qu&#39;une seule fois. La partie inférieure du rapport contient la liste des profils actifs pour chaque dimension de ciblage.

Ce rapport est généré chaque mois par le processus technique de **[!UICONTROL facturation]** . Il contient le nombre de principaux profils ciblés au cours de la période variable des 12 derniers mois.

Il convient de noter que les profils qui ont été exclus pendant la préparation de la diffusion (règles de typologie, quarantaines) ne sont pas pris en compte. En outre, un profil ciblé par plusieurs diffusions ne sera comptabilisé qu&#39;une seule fois.

![](assets/audience_active_profiles2.png)

Au bas du rapport se trouve la liste des profils principaux traités par le processus de facturation :

* La source **[!UICONTROL NmsRecipient]** comprend tous les clients qui ont été contactés à l&#39;aide des informations de leur profil Campaign Standard.

* D&#39;un autre côté, les clients ciblés à l&#39;aide d&#39;un élément d&#39;information spécifique uniquement (adresse électronique, numéro de téléphone), sans rapport avec leur profil Campaign, tomberont sous la source **[!UICONTROL anonyme]** .
