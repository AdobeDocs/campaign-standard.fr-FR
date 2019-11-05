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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Profils actifs{#active-profiles}

Adobe Campaign contient un rapport qui indique le nombre de profils actifs. Ce rapport est fourni uniquement à titre d'information ; il n'a aucune incidence directe sur la facturation. Seuls les administrateurs y ont accès, sous **[!UICONTROL Administration &gt; Mesures des clients]**.

![](assets/audience_active_profiles1.png)

Le workflow technique **[!UICONTROL Facturation]** génère chaque mois un rapport contenant le nombre de profils actifs qui ont été ciblés pendant la dernière période glissante de 12 mois.

Les profils exclus lors de la préparation de la diffusion (règles de typologie, quarantaines) ne sont pas pris en compte. Un profil qui a été ciblé par plusieurs diffusions ne sera comptabilisé qu'une seule fois. La partie inférieure du rapport contient la liste des profils actifs pour chaque dimension de ciblage.

![](assets/audience_active_profiles2.png)

