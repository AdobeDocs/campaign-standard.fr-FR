---
title: Utiliser les données de workflow
seo-title: Utiliser les données de workflow
description: Utiliser les données de workflow
seo-description: Découvrez les différentes possibilités d'utilisation des données importées ou ciblées.
page-status-flag: never-activated
uuid: 3dd66aeb-3a26-4214-b6a0-242c2b7fbc49
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 90b250f1-f32d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Utiliser les données de workflow{#using-workflow-data}

Une fois les données identifiées et préparées, elles peuvent être utilisées dans les contextes suivants :

* L'activité **[!UICONTROL Mise à jour de données]** permet de mettre à jour en masse les champs de la base de données.
* L'activité **[!UICONTROL Sauvegarde d'audience]** permet de mettre à jour une audience existante ou de créer une nouvelle audience à partir de la population calculée en amont dans un workflow. Les audiences créées ou pouvant être mises à jour à partir de cette activité sont de type **Liste** ou **Fichier**. Cette activité permet également d'exporter des profils en tant qu'audience/segment Adobe Experience Cloud.
* L'activité **[!UICONTROL Services d'inscription]** permet d'inscrire ou de désinscrire des profils en masse à un service.
* L'activité **[!UICONTROL Extraction de fichier]** permet d'exporter des données présentes dans Adobe Campaign sous la forme d'un fichier externe.

Après avoir défini une cible de profil, vous pouvez utiliser plusieurs activités pour créer et envoyer des diffusions :

* L'activité **[!UICONTROL Diffusion Email]** permet de paramétrer l'envoi d'un email dans un workflow. Cet email peut être **unique** et n'être envoyé qu'une seule fois ou être **récurrent**.
* L'activité **[!UICONTROL Diffusion SMS]** permet de paramétrer l'envoi d'un SMS dans un workflow. Ce SMS peut être **unique** et n'être envoyé qu'une seule fois ou être **récurrent**.
* L'activité **[!UICONTROL Diffusion sur des applications mobiles]** permet de paramétrer l'envoi d'une notification push dans un workflow. Cette notification peut être **unique** et n'être envoyée qu'une seule fois ou être **récurrente**.

