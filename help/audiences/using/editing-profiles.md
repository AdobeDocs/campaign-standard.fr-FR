---
solution: Campaign Standard
product: campaign
title: Editer des profils
description: Découvrez comment éditer des profils existants et accéder aux informations sur les contacts, les préférences en matière de canaux, le tracking, les abonnements, etc.
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '330'
ht-degree: 100%

---


# Editer des profils{#editing-profiles}

## Accès aux propriétés des profils {#accessing-profile-properties}

Pour éditer un profil existant et consulter les données qui lui sont associées, ou pour le modifier, les étapes sont les suivantes :

1. Depuis la page d&#39;accueil d&#39;Adobe Campaign, cliquez sur la vignette **[!UICONTROL Profils clients]** ou l&#39;onglet **[!UICONTROL Profils]**.
1. Sélectionnez un contact.
1. Cliquez sur l&#39;icône **[!UICONTROL Editer les propriétés du profil]** pour accéder aux informations détaillées du profil.

   ![](assets/profile_creation2.png)

   La fenêtre des propriétés du profil propose plusieurs onglets qui permettent d&#39;accéder à toutes les informations du profil :

   D&#39;autres onglets peuvent être disponibles en fonction des ressources personnalisées créées ou étendues dans Adobe Campaign. Pour plus d&#39;informations sur les ressources personnalisées, voir la section [Ressources personnalisées](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >Vous pouvez uniquement modifier les informations dans l&#39;onglet **[!UICONTROL Général]**, à l&#39;exception de la section **[!UICONTROL Traçabilité]**.

L&#39;édition des profils est également possible à l&#39;aide de l&#39;API Adobe Campaign Standard. Consultez à ce sujet la [documentation dédiée](../../api/using/updating-profiles.md) .

Rubrique connexe :

* [Profil client intégré](../../audiences/using/integrated-customer-profile.md)
* [Envoi au fuseau horaire du destinataire](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Données de profil générales    {#general-profile-data}

L&#39;onglet **[!UICONTROL Général]** regroupe les informations suivantes concernant le profil :

* les informations de contact, telles que le prénom, le nom, la date de naissance, la photo, la préférence linguistique du destinataire (pour les [emails multilingues](../../channels/using/creating-a-multilingual-email.md)), etc. ;
* les canaux sur lesquels le profil peut être contacté, incluant son adresse email, son numéro de téléphone mobile et ses informations d&#39;opt-out ;
* l&#39;adresse postale (pour le [courrier](../../channels/using/about-direct-mail.md)) et le fuseau horaire du contact (pour [planifier les messages dans son fuseau horaire](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)) ;
* l&#39;autorisation d&#39;accès qui indique l&#39;entité organisationnelle du destinataire (pour [gérer les permissions](../../administration/using/about-access-management.md)). Voir également [Partitionnement des profils](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Logs d&#39;envoi et tracking    {#sending-and-tracking-logs}

Les onglets **[!UICONTROL Envois]** et **[!UICONTROL Tracking]** répertorient les diffusions envoyées au profil, ainsi que toutes les données de tracking associées.

Pour plus d&#39;informations sur les envois et le tracking, consultez les sections [Logs de diffusion](../../sending/using/monitoring-a-delivery.md#delivery-logs) et [Tracker les messages](../../sending/using/tracking-messages.md).

## Abonnements    {#subscriptions}

Les abonnements du contact sont répertoriés dans l&#39;onglet correspondant. Pour plus d&#39;informations sur l&#39;abonnement à un service, voir [cette section](../../audiences/using/about-subscriptions.md).

L&#39;onglet **[!UICONTROL Abonnements à des applications mobiles]** concernent les notifications push. Pour plus d&#39;informations, voir la section [Notification push](../../channels/using/about-push-notifications.md).
