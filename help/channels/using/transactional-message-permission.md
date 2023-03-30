---
title: Permission des messages transactionnels
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
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 1%

---

# Permission des messages transactionnels {#transactional-message-permission}

Actuellement, dans Adobe Campaign Standard, les utilisateurs sans le groupe de sécurité Administrateur ne peuvent pas accéder aux événements, les créer ou les publier, ce qui entraîne des problèmes pour les utilisateurs professionnels qui doivent configurer et publier des événements mais ne disposent pas des droits d’administrateur.

Nous avons mis en oeuvre les améliorations suivantes au contrôle d’accès des messages transactionnels :

* Une nouvelle **[!UICONTROL Rôle]**, appelé **Utilisateur MC**, a été ajouté pour permettre aux utilisateurs non administrateurs de gérer les événements transactionnels. Le **Utilisateur MC** Ce rôle permet à ces utilisateurs d’accéder aux événements et messages transactionnels, de les créer, de les publier et de les dépublier.

* Les diffusions enfants sont désormais définies sur la variable **[!UICONTROL Entité organisationnelle]** du groupe de sécurité auquel appartient l&#39;utilisateur créant le modèle de message, plutôt que d&#39;être limité au **[!UICONTROL Entité organisationnelle]** de **Agent Message Center (mcExec)** groupe de sécurité.

* La valeur par défaut **Exécution Message Center (mcExec)** campaign, qui rassemble les diffusions enfants des messages transactionnels, est maintenant défini sur l’entité organisationnelle. **Tous** permettant à tous les utilisateurs d’afficher des rapports sur les diffusions enfants.

Pour affecter la variable **Utilisateur MC** role:

1. Créer **[!UICONTROL Groupe de sécurité]** ou mettre à jour une version existante. [En savoir plus](../../administration/using/managing-groups-and-users.md).

1. Cliquez sur **[!UICONTROL Créer un élément]** pour affecter des rôles à votre groupe de sécurité.

   ![](assets/event_access_1.png)

1. Sélectionner l’utilisateur MC **[!UICONTROL Rôle]** et cliquez sur **[!UICONTROL Confirmer]**.

   >[!IMPORTANT]
   >
   > Procédez avec précaution lorsque vous attribuez le rôle Utilisateur MC aux opérateurs, car cela leur permet d’annuler la publication d’événements.

   ![](assets/event_access_2.png)

1. Une fois la configuration effectuée, cliquez sur **[!UICONTROL Enregistrer]**.

Utilisateurs liés à ceci **[!UICONTROL Groupe de sécurité]** peut désormais accéder aux événements et messages transactionnels, les créer et les publier.

Le tableau ci-dessous décrit l’impact de cette fonctionnalité sur le contrôle d’accès :

| Objets | Avant cette modification | Après cette modification |
|:-: | :--: | :-:|
| Campagne Message Center Execution (mcExec) | **Exécution Message Center (mcExec)** La campagne est définie sur l’entité organisationnelle de la variable **Agent Message Center (mcExec)** groupe de sécurité. | **Exécution Message Center (mcExec)** La campagne est définie sur l’entité organisationnelle **Tous** pour permettre l’association de toutes les diffusions enfants à cette campagne.</br> Tous les utilisateurs pourront visualiser les rapports des diffusions enfants, mais n&#39;auront accès qu&#39;en lecture seule au contenu de la diffusion. |
| Diffusions d’enfants | Les diffusions enfants sont définies sur la variable **Entité organisationnelle** de **Agent Message Center (mcExec)** groupe de sécurité. | Les diffusions enfants seront définies sur la variable **Entité organisationnelle** du groupe de sécurité auquel appartient l&#39;utilisateur créant le modèle de message. |
| Modèle de message | Les modèles de message sont définis sur la variable **Entité organisationnelle** de **Agent Message Center (mcExec)** groupe de sécurité. | Les modèles de message seront définis sur la variable **Entité organisationnelle** du groupe de sécurité auquel appartient l&#39;utilisateur créant le modèle de message. |
| Événements transactionnels | Uniquement les utilisateurs dans la variable **Administrateur** groupe de sécurité peut créer et publier des événements. | Le **Utilisateur MC** rôle permet aux utilisateurs de créer et de publier des événements. |
| Modèles de message transactionnel | Les modèles de message transactionnel sont définis sur l’entité organisationnelle. **Tous**. | Le modèle de message de transaction sera défini sur **Entité organisationnelle** du groupe de sécurité auquel appartient l&#39;utilisateur créant le modèle de message. |