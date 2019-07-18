---
title: Utiliser les données de workflow
seo-title: Utiliser les données de workflow
description: Utiliser les données de workflow
seo-description: Découvrez les différentes possibilités d'utilisation des données importées ou ciblées.
page-status-flag: jamais activé
uuid: 3 dd 66 aeb -3 a 26-4214-b 6 a 0-242 c 2 b 7 fbc 49
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatisation
content-type: référence
topic-tags: workflow-general-operation
discoiquuid: 90 b 250 f 1-f 32 d -4256-83 ea -4 c 0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Utiliser les données de workflow{#using-workflow-data}

Une fois les données identifiées et préparées, elles peuvent être utilisées dans les contextes suivants :

* L'activité **[!UICONTROL Mise à jour de données]permet de mettre à jour en masse les champs de la base de données.**
* L'activité **[!UICONTROL Sauvegarde d'audience]permet de mettre à jour une audience existante ou de créer une nouvelle audience à partir de la population calculée en amont dans un workflow.** Les audiences créées ou pouvant être mises à jour à partir de cette activité sont de type **Liste** ou **Fichier.** Cette activité permet également d'exporter des profils en tant qu'audience/segment Adobe Experience Cloud.
* L'activité **[!UICONTROL Services d'inscription]permet d'inscrire ou de désinscrire des profils en masse à un service.**
* L'activité **[!UICONTROL Extraction de fichier]permet d'exporter des données présentes dans Adobe Campaign sous la forme d'un fichier externe.**

Après avoir défini une cible de profil, vous pouvez utiliser plusieurs activités pour créer et envoyer des diffusions :

* L'activité **[!UICONTROL Diffusion Email]permet de paramétrer l'envoi d'un email dans un workflow.** Cet email peut être **unique** et n'être envoyé qu'une seule fois ou être **récurrent**.
* L'activité **[!UICONTROL Diffusion SMS]permet de paramétrer l'envoi d'un SMS dans un workflow.** Ce SMS peut être **unique** et n'être envoyé qu'une seule fois ou être **récurrent**.
* L'activité **[!UICONTROL Diffusion sur des applications mobiles]permet de paramétrer l'envoi d'une notification push dans un workflow.** Cette notification peut être **unique** et n'être envoyée qu'une seule fois ou être **récurrente**.

