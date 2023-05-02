---
title: Autorisation pour les messages transactionnels
description: Découvrez les autorisations liées aux événements transactionnels.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 7247fe596494690ac0676196fbb72c6139aeb0c7
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 18%

---

# Améliorations des événements transactionnels {#transactional-event-improvements}

>[!AVAILABILITY]
>
>Actuellement, ces fonctionnalités ne sont disponibles que pour un ensemble d’organisations (disponibilité limitée). Pour plus d’informations, contactez votre représentant Adobe.

Actuellement, dans Adobe Campaign Standard, les utilisateurs ne disposant pas du groupe de sécurité Administrateur ne peuvent pas accéder aux événements transactionnels, ni les créer, ni les publier, ce qui entraîne des problèmes pour les utilisateurs professionnels qui doivent configurer et publier des événements, mais ne disposent pas des droits d’administrateur. En outre, il n’est pas possible de dupliquer des événements transactionnels.

Nous avons apporté les améliorations suivantes au contrôle d’accès des messages transactionnels :

* Une nouvelle **[!UICONTROL Rôle]**, appelé **Utilisateur MC**, a été ajouté pour permettre aux utilisateurs non-administrateurs de gérer la configuration des événements transactionnels. Le rôle **Utilisateur/utilisatrice MC** permet aux utilisateurs et utilisatrices d’accéder aux événements et messages transactionnels, de les créer, de les publier et de les dépublier.

* Les diffusions d’exécution (c’est-à-dire les messages techniques créés chaque fois qu’un message transactionnel est édité et publié de nouveau, ou une fois par mois par défaut) sont désormais définies sur la valeur **[!UICONTROL Entité organisationnelle]** du groupe de sécurité auquel appartient l’utilisateur créant l’événement, plutôt que d’être limité au **[!UICONTROL Entité organisationnelle]** de **Agent Message Center (mcExec)** groupe de sécurité.

* **Administrateurs** peut désormais dupliquer les événements transactionnels publiés, ainsi que les utilisateurs avec la variable **Utilisateur MC** rôle pourvu qu’ils soient dans le même **Entité organisationnelle** hiérarchie en tant qu’utilisateur ayant créé l’événement.

## Attribution du rôle utilisateur MC {#assign-role}

Pour affecter la variable **Utilisateur MC** rôle de votre groupe de sécurité :

1. Créez un **[!UICONTROL Groupe de sécurité]** ou modifiez un groupe existant. [En savoir plus](../../administration/using/managing-groups-and-users.md).

1. Cliquez sur **[!UICONTROL Créer un élément]** pour affecter des rôles à votre groupe de sécurité.

   ![](assets/event_access_1.png)

1. Sélectionner le **[!UICONTROL Rôle]** Utilisateur/utilisatrice MC et cliquez sur **[!UICONTROL Confirmer]**.

   >[!IMPORTANT]
   >
   > Procédez avec précaution lorsque vous attribuez le rôle Utilisateur/utilisatrice MC aux opérateurs, car cela leur permet de dépublier des événements.

   ![](assets/event_access_2.png)

1. Une fois la configuration effectuée, cliquez sur **[!UICONTROL Enregistrer]**.

Utilisateurs liés à ceci **[!UICONTROL Groupe de sécurité]** peut désormais accéder aux événements et messages transactionnels, les créer et les publier.

## Affectation du groupe de sécurité utilisateur MC {#assign-group}

1. Dans le Admin Console, sélectionnez la variable **Produits** .

1. Sélectionner **Adobe Campaign Standard** choisissez ensuite votre instance.

1. Dans la **Profils de produit** , sélectionnez la variable **Utilisateur MC** groupe.

1. Cliquez sur **Ajouter un utilisateur** et saisissez le nom, le groupe d’utilisateurs ou l’adresse électronique du profil que vous souhaitez ajouter à ce profil de produit.

1. Une fois l’ajout effectué, cliquez sur **Enregistrer**.

Utilisateurs ajoutés à cette liste **[!UICONTROL Groupe de sécurité]** peut désormais accéder aux événements et messages transactionnels, les créer et les publier.

## Duplication d’événements transactionnels {#duplicate-transactional-events}

Un utilisateur avec la variable **Administrateur** groupe de sécurité<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> peut désormais dupliquer une configuration d’événement si l’événement a été **publié**.

En outre, les utilisateurs non administrateurs avec la variable **Utilisateur MC** Le rôle peut désormais accéder aux configurations d’événement, mais son autorisation de duplication est déterminée par la fonction **Entité organisationnelle** à qui ils appartiennent. Si l’utilisateur actuel et l’utilisateur qui a créé l’événement appartiennent à la même hiérarchie d’entités organisationnelles, la duplication est autorisée.

Par exemple, si un utilisateur appartenant à l&#39;entité organisationnelle &quot;Ventes de France&quot; crée une configuration d&#39;événement :

* Un autre utilisateur dont l&#39;entité organisationnelle est &quot;Ventes Paris&quot; pourra dupliquer cet événement, car &quot;Ventes Paris&quot; fait partie de l&#39;entité organisationnelle &quot;Ventes France&quot;.

* Cependant, un utilisateur dont l’entité organisationnelle est &quot;Ventes de San Francisco&quot; ne pourra pas le faire, car &quot;Ventes de San Francisco&quot; se trouve sous l’entité organisationnelle &quot;Ventes des États-Unis&quot;, qui est distincte de l’entité organisationnelle &quot;Ventes de France&quot;.

Pour dupliquer une configuration d’événement, procédez comme suit.

1. Cliquez sur le logo **Adobe**, en haut à gauche, puis sélectionnez **[!UICONTROL Plans marketing]** > **[!UICONTROL Messages transactionnels]** > **[!UICONTROL Configuration d’événements]**.

1. Passez la souris sur la configuration de l’événement publié de votre choix et sélectionnez l’événement **[!UICONTROL Dupliquer l’élément]** bouton .

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >Vous ne pouvez pas dupliquer une configuration d’événement qui n’est pas publiée. [En savoir plus](publishing-transactional-event.md)

1. L’événement dupliqué s’affiche automatiquement. Elle contient la même configuration que celle que vous avez définie pour l’événement d’origine, mais elle contient la variable **[!UICONTROL Version préliminaire]** statut.

   ![](assets/message-center_duplicated-draft-event.png)

1. Le message transactionnel correspondant est automatiquement créé. Pour y accéder, accédez à **[!UICONTROL Messages transactionnels]** > **[!UICONTROL Messages transactionnels]**.

   ![](assets/message-center_duplicated-message.png)

1. Ouvrez le message nouvellement dupliqué. Il contient la même conception que celle que vous avez définie pour le message d’origine, mais il comporte la propriété **[!UICONTROL Version préliminaire]** même si le message transactionnel d’origine a été publié.

   ![](assets/message-center_duplicated-draft-message.png)

1. Vous pouvez maintenant modifier et personnaliser ce message. Voir [Modifier des messages transactionnels](../../channels/using/editing-transactional-message.md).

## Impacts {#impacts}

Le tableau ci-dessous décrit l’impact de ces améliorations :

| Objets | Avant cette modification | Après cette modification |
|:-: | :--: | :-:|
| Événements transactionnels | Seules les personnes membres du groupe de sécurité **Administrateur** peuvent créer et publier des événements. | Le rôle **Utilisateur/utilisatrice MC** permet de créer et de publier des événements. |
| Messages transactionnels | Les messages transactionnels sont définis sur la variable **Entité organisationnelle** de **Agent Message Center (mcExec)** groupe de sécurité. | Les messages transactionnels sont définis sur la variable **Entité organisationnelle** du groupe de sécurité auquel appartient l’utilisateur créant l’événement/le message transactionnel. |
| Diffusions d&#39;exécution | Les diffusions d’exécution sont définies sur la variable **Entité organisationnelle** de **Agent Message Center (mcExec)** groupe de sécurité. | Les diffusions d’exécution sont définies sur la variable **Entité organisationnelle** du groupe de sécurité auquel appartient l’utilisateur créant l’événement/le message transactionnel. |
| Événements transactionnels publiés | La duplication n’est possible pour aucun utilisateur. | <ul><li>Utilisateurs avec la variable **Administrateur** Le groupe de sécurité peut dupliquer les événements publiés.</li> <li>Utilisateurs avec la variable **Utilisateur MC** Le rôle peut dupliquer des événements publiés s’ils se trouvent dans le même **Entité organisationnelle** hiérarchie en tant qu’utilisateur ayant créé l’événement.</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->