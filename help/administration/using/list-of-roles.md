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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 88d0f67683c5209ccf25d1ceae1ab23b3ac14e06

---


# Liste des rôles{#list-of-roles}

Par défaut, Adobe Campaign propose un ensemble de rôles qui permettent de définir les autorisations unitaires attribuées aux utilisateurs et groupes d&#39;utilisateurs.

Combinés avec les entités organisationnelles, les rôles donnent aux utilisateurs une vue filtrée de l&#39;interface et définissent leur accès aux différentes fonctionnalités.

Pour plus d’informations, reportez-vous au tableau [](/help/administration/using/assets/acs_rights.pdf)Rôles et autorisations, qui détaille les fonctions disponibles dans l’interface en fonction des autorisations sélectionnées.

![](assets/user_management_3.png)

Les rôles peuvent être gérés à partir du **[!UICONTROL Administration > Users & Security > Roles]** menu.

Les droits par défaut sont les suivants :

* **[!UICONTROL Administration]**: Une administration générique juste.
* **[!UICONTROL Datamodel]** : droit pour l&#39;exécution des publications et de créer des ressources personnalisées.
* **[!UICONTROL Export]**: Droit d’exporter des données.
* **[!UICONTROL Generic import]**: Droit d’exécuter une importation générique sur des données. For this to work, you need to link the **[!UICONTROL Generic import]** role to the **[!UICONTROL Workflow]** role.
* **[!UICONTROL Prepare deliveries]**: Droit de créer, modifier, préparer et supprimer des livraisons. Les utilisateurs dotés de ce rôle peuvent préparer la diffusion, mais pas l&#39;envoyer.
* **[!UICONTROL Start deliveries]**: Droit de créer, modifier, préparer, envoyer et supprimer des livraisons.
* **[!UICONTROL Workflow]**: Droit de gérer l’exécution des processus (démarrage, arrêt, pause, etc.). Les utilisateurs dotés de ce rôle ne peuvent pas envoyer de diffusion, même dans un workflow.

>[!IMPORTANT]
>
>Les rôles **[!UICONTROL Deliverability]**, **[!UICONTROL Command execution]**, **[!UICONTROL Export]**, **[!UICONTROL File access]** et **[!UICONTROL Message Center push]** sont réservés aux administrateurs d’Adobe à des fins internes. Ils ne doivent pas être accordés à un utilisateur.

**Rubriques connexes :**

* [Gestion des accès](../../administration/using/about-access-management.md)
* [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md)
