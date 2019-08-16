---
title: Liste des rôles
seo-title: Liste des rôles
description: Liste des rôles
seo-description: Obtenez des informations sur la liste des rôles que vous pouvez affecter à vos utilisateurs.
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
translation-type: ht
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Liste des rôles{#list-of-roles}

Par défaut, Adobe Campaign propose un ensemble de rôles qui permettent de définir les autorisations unitaires attribuées aux utilisateurs et groupes d'utilisateurs. Combinés avec les entités organisationnelles, les rôles donnent aux utilisateurs une vue filtrée de l'interface et définissent leur accès aux différentes fonctionnalités. Voir à ce propos le [tableau des rôles et des permissions](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

![](assets/user_management_3.png)

Les rôles peuvent être gérés depuis le menu **[!UICONTROL Administration &gt; Utilisateurs &amp; sécurité &gt; Rôles]**.

Les droits par défaut sont les suivants :

* **[!UICONTROL Administration]** : droit d'administration générique.
* **[!UICONTROL Datamodel]** : droit pour l'exécution des publications et de créer des ressources personnalisées.
* **[!UICONTROL Export]** : droit pour l'export des données.
* **[!UICONTROL Import générique]** : droit pour l'exécution d'un import générique sur les données. Pour que cela fonctionne, vous devez associer le rôle **[!UICONTROL Import générique]** au rôle **[!UICONTROL Workflow]**.
* **[!UICONTROL Préparer des diffusions]** : droit pour la création, l'édition et le démarrage d'une préparation de diffusion, et l'envoi des bons à tirer.
* **[!UICONTROL Démarrer des diffusions]** : droit pour la validation des diffusions préalablement préparées.
* **[!UICONTROL Workflow]** : droit pour l'utilisation des workflows.

>[!CAUTION]
>
>Le rôle DELIVRABILITE est réservé uniquement aux administrateurs Adobe. Il ne doit pas être accordé à un utilisateur.

**Rubriques connexes :**

* [Gestion des accès](../../administration/using/about-access-management.md)
* [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md)

