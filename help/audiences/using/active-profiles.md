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
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 72%

---


# Profils actifs{#active-profiles}

Adobe Campaign contient un rapport qui indique le nombre de profils actifs. Ce rapport est fourni uniquement à titre d&#39;information ; il n&#39;a aucune incidence directe sur la facturation. Seuls les administrateurs y ont accès, sous **[!UICONTROL Administration > Mesures des clients]**.

![](assets/audience_active_profiles1.png)

Le workflow technique **[!UICONTROL Facturation]** génère chaque mois un rapport contenant le nombre de profils actifs qui ont été ciblés pendant la dernière période glissante de 12 mois.

Les profils exclus lors de la préparation de la diffusion (règles de typologie, quarantaines) ne sont pas pris en compte. Un profil qui a été ciblé par plusieurs diffusions ne sera comptabilisé qu&#39;une seule fois. La partie inférieure du rapport contient la liste des profils actifs pour chaque dimension de ciblage.

![](assets/audience_active_profiles2.png)

Si vous êtes hébergé sur AWS et que vous utilisez Campaign Standard à partir de la version 10368, vous pouvez également surveiller le nombre de profils actifs utilisés sur vos instances directement à partir du Panneau de configuration. For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
