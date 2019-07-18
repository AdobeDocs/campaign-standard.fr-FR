---
title: Réconciliation et stockage des données
seo-title: Réconciliation et stockage des données
description: Réconciliation et stockage des données
seo-description: Adobe Campaign permet de définir la gestion des données entrées dans la landing page lors de sa validation par un visiteur.
page-status-flag: jamais activé
uuid: 5 b 222 ea 2-6628-457 f-a 618-bfc 0 e 5 eb 93 dd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canaux
content-type: référence
topic-tags: landing-pages
discoiquuid: 899 c 7152-f 415-4 df 9-b 4 b 4-5 ff 3470 a 4 e 32
context-tags: Landingpage, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Réconciliation et stockage des données{#data-storage-and-reconciliation}

Les paramètres de réconciliation permettent de définir le mode de gestion des données entrées dans la landing page lors de sa validation par un visiteur.

Pour cela :

1. Editez les propriétés de la landing page accessibles via l'icône ![](assets/edit_darkgrey-24px.png) dans le tableau de bord de la landing page, puis affichez les paramètres **Traitement[!UICONTROL .]**

   ![](assets/lp_parameters_4.png)

1. Select the **[!UICONTROL Reconciliation key]**: these database fields (for example: email, first name, last name) are used to determine whether the visitor has a profile that is already known in the Adobe Campaign database. Cela permet de mettre à jour ou de créer un profil, en fonction des paramètres de stratégie de mise à jour définis.
1. Define the **[!UICONTROL Form parameter mapping]**: this section allows you to map the landing page field parameters and those used in the reconciliation key.
1. Select the **[!UICONTROL Update strategy]**: if the reconciliation key recovers an existing database profile, you can choose for this profile to be updated with the data entered in the form or instead prevent this update.

