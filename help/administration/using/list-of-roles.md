---
title: Liste des rôles
description: Obtenez des informations sur la liste des rôles que vous pouvez affecter à vos utilisateurs.
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Liste des rôles{#list-of-roles}

Par défaut, Adobe Campaign propose un ensemble de rôles qui permettent de définir les autorisations unitaires attribuées aux utilisateurs et groupes d&#39;utilisateurs.

Combinés avec les entités organisationnelles, les rôles donnent aux utilisateurs une vue filtrée de l&#39;interface et définissent leur accès aux différentes fonctionnalités.

Pour plus d’informations, reportez-vous au [tableau Rôles et permissions](/help/administration/using/assets/acs_rights.pdf), qui présente les fonctions disponibles dans l’interface en fonction des autorisations sélectionnées.

[![image](assets/user_management_3.png)](https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/administrating/users-and-security/assets/acs_rights.pdf)

Les rôles peuvent être gérés depuis le menu **[!UICONTROL Administration > Utilisateurs &amp; sécurité > Rôles]**.

Les droits par défaut sont les suivants :

* **[!UICONTROL Administration]** : droit d&#39;administration générique.
* **[!UICONTROL Datamodel]** : droit pour l&#39;exécution des publications et de créer des ressources personnalisées.
* **[!UICONTROL Import générique]** : droit pour l&#39;exécution d&#39;un import générique sur les données. Pour que cela fonctionne, vous devez associer le rôle **[!UICONTROL Import générique]** au rôle **[!UICONTROL Workflow]**.
* **[!UICONTROL Préparer des diffusions]** : droit pour la création, la modification, la préparation et la suppression des diffusions. Les utilisateurs dotés de ce rôle peuvent préparer la diffusion, mais pas l&#39;envoyer.
* **[!UICONTROL Démarrer des diffusions]** : droit pour la création, la modification, la préparation, l&#39;envoi et la suppression des diffusions.
* **[!UICONTROL Workflow]** : droit de gérer l’exécution des workflows (démarrage, arrêt, pause, etc.). Les utilisateurs dotés de ce rôle ne peuvent pas envoyer de diffusion, même dans un workflow.

**Rubriques connexes :**

* [Gestion des accès](../../administration/using/about-access-management.md)
* [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md)
