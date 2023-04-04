---
title: Autorisation pour les messages transactionnels
description: Découvrez les autorisations liées aux événements transactionnels.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
hide: true
hidefromtoc: true
feature: Transactional Messaging
role: User
level: Intermediate
source-git-commit: d7e0912dd7d19a1f5dd2172235f28a40e130cac1
workflow-type: ht
source-wordcount: '467'
ht-degree: 100%

---

# Autorisation pour les messages transactionnels {#transactional-message-permission}

Actuellement, dans Adobe Campaign Standard, les utilisateurs et les utilisatrices qui ne font pas partie du groupe de sécurité Administrateur ne peuvent pas accéder aux événements, en créer ou en publier. Cela entraîne des problèmes pour les utilisateurs et utilisatrices professionnels qui doivent configurer et publier des événements, mais ne disposent pas des droits d’administration.

Nous avons apporté les améliorations suivantes au contrôle d’accès des messages transactionnels :

* ajout d’un nouveau **[!UICONTROL Rôle]**, appelé **Utilisateur/utilisatrice MC** afin de permettre aux personnes qui ne disposent pas du rôle d’administration de gérer les événements transactionnels. Le rôle **Utilisateur/utilisatrice MC** permet aux utilisateurs et utilisatrices d’accéder aux événements et messages transactionnels, de les créer, de les publier et de les dépublier.

* Les diffusions enfants sont désormais définies sur l’**[!UICONTROL Entité organisationnelle]** du groupe de sécurité auquel appartient l’utilisateur ou l’utilisatrice qui crée le modèle de message, au lieu d’être limitées à l’**[!UICONTROL Entité organisationnelle]** du groupe de sécurité **Agent Message Center (mcExec)**.

* La campagne par défaut **Exécution Message Center (mcExec)**, qui rassemble les diffusions enfants des messages transactionnels, est maintenant définie sur l’entité organisationnelle **Tous**, ce qui permet à tous les utilisateurs et toutes les utilisatrices de consulter les rapports sur les diffusions enfants.

Pour affecter le rôle **Utilisateur/utilisatrice MC**, procédez comme suit :

1. Créez un **[!UICONTROL Groupe de sécurité]** ou modifiez un groupe existant. [En savoir plus](../../administration/using/managing-groups-and-users.md).

1. Cliquez sur **[!UICONTROL Créer un élément]** pour affecter des rôles à votre groupe de sécurité.

   ![](assets/event_access_1.png)

1. Sélectionner le **[!UICONTROL Rôle]** Utilisateur/utilisatrice MC et cliquez sur **[!UICONTROL Confirmer]**.

   >[!IMPORTANT]
   >
   > Procédez avec précaution lorsque vous attribuez le rôle Utilisateur/utilisatrice MC aux opérateurs, car cela leur permet de dépublier des événements.

   ![](assets/event_access_2.png)

1. Une fois la configuration effectuée, cliquez sur **[!UICONTROL Enregistrer]**.

Les personnes appartenant à ce **[!UICONTROL Groupe de sécurité]** peuvent maintenant accéder aux événements et messages transactionnels, en créer et en publier.

Le tableau ci-dessous décrit l’impact de cette fonctionnalité sur le contrôle d’accès :

| Objets | Avant cette modification | Après cette modification |
|:-: | :--: | :-:|
| Campagne Exécution Message Center (mcExec) | La campagne **Exécution Message Center (mcExec)** est définie sur l’entité organisationnelle du groupe de sécurité **Agent Message Center (mcExec)**. | La campagne **Exécution Message Center (mcExec)** est définie sur l’entité organisationnelle **Tous** pour permettre l’association de toutes les diffusions enfants à cette campagne.</br> Tous les utilisateurs et toutes les utilisatrices pourront visualiser les rapports des diffusions enfants, mais n’auront accès qu’en lecture seule au contenu de la diffusion. |
| Diffusions enfants | Les diffusions enfants sont définies sur l’**Entité organisationnelle** du groupe de sécurité **Agent Message Center (mcExec)**. | Les diffusions enfants sont définies sur l’**Entité organisationnelle** du groupe de sécurité auquel appartient la personne qui crée le modèle de message. |
| Modèle de message | Les modèles de message sont définis sur l’**Entité organisationnelle** du groupe de sécurité **Agent Message Center (mcExec)**. | Les modèles de message sont définis sur l’**Entité organisationnelle** du groupe de sécurité auquel appartient la personne qui crée le modèle de message. |
| Événements transactionnels | Seules les personnes membres du groupe de sécurité **Administrateur** peuvent créer et publier des événements. | Le rôle **Utilisateur/utilisatrice MC** permet de créer et de publier des événements. |
| Modèles de message transactionnel | Les modèles de message transactionnel sont définis sur l’entité organisationnelle **Tous**. | Le modèle de message transactionnel est défini sur l’**Entité organisationnelle** du groupe de sécurité auquel appartient la personne qui crée le modèle de message. |