---
title: A propos des messages transactionnels
seo-title: A propos des messages transactionnels
description: A propos des messages transactionnels
seo-description: Découvrez les différents types de messages transactionnels que vous pouvez envoyer et leur utilisation dans Adobe Campaign.
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: ht
source-git-commit: d93c2600299a8d2ec3672b3d82222f423878034c

---


# A propos des messages transactionnels{#about-transactional-messaging}

Vous pouvez créer et gérer des messages transactionnels personnalisés dans Adobe Campaign.

Un message transactionnel est une communication individuelle et unique transmise à un utilisateur par un prestataire tel qu'un site web.

* Ce type de message est particulièrement attendu, car il est porteur d'une information que son destinataire souhaite vérifier ou confirmer. Il peut s'agir par exemple d'un message de bienvenue à l'ouverture d'un compte, d'une confirmation d'expédition de commande, d'une facture ou d'un message de confirmation de changement de mot de passe.
* Il s'agit d'un message important qui définit la relation client : l'utilisateur s'attend à un envoi en temps réel. Le délai entre le déclenchement de l'événement et l'arrivée du message doit donc être très court.
* Les messages transactionnels bénéficient en général d'un taux d'ouverture élevé.

Adobe Campaign permet d'intégrer cette fonctionnalité à un système d'information qui lui envoie les événements destinés à être transformés en messages transactionnels personnalisés.

>[!NOTE]
>
>Selon vos options, les messages transactionnels peuvent être envoyés par email, SMS ou notification push. Veuillez vérifier votre accord de licence.

Dans Adobe Campaign, deux types de message transactionnel sont disponibles :

* [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md) ciblant un événement. Les données contenues dans l'événement sont utilisées pour définir la cible de la diffusion.
* [Messages transactionnels basés sur un profil](../../channels/using/profile-transactional-messages.md) ciblant des profils de la base de données marketing Adobe Campaign. Vous pouvez utiliser les informations de la base de données Adobe Campaign pour envoyer un message transactionnel selon les profils marketing des clients.

Le type du message est défini lors de la configuration de l'événement qui sera transformé en message transactionnel. Voir [Configuration des messages transactionnels](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign donne la priorité au traitement des messages transactionnels par rapport à toute autre diffusion.

Les messages transactionnels sont également disponibles depuis l'API Adobe Campaign Standard. Consultez à ce sujet la [documentation dédiée](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Principe de fonctionnement des messages transactionnels {#transactional-messaging-operating-principle}

Prenons le cas d'une société disposant d'un site web, sur lequel ses clients peuvent acheter des produits.

Adobe Campaign vous permet d'envoyer un email de notification aux utilisateurs du site ayant ajouté des produits dans leur panier : lorsque l'un d'eux quitte le site sans poursuivre ses achats, un email d'abandon de panier lui est automatiquement envoyé.

Les étapes de mise en œuvre sont les suivantes :

1. Configurez un événement qui sera nommé "Abandon de panier". La publication de la configuration de cet événement crée automatiquement un message transactionnel. La création et la publication d'un événement sont présentées dans la section [Configuration d'un événement pour envoyer un message transactionnel basé sur un événement](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).
1. Le message transactionnel doit être personnalisé, testé, puis publié. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).
1. Par ailleurs, pour que cet événement soit déclenché lorsqu'un client abandonne son panier, il faut l'envoyer depuis le site web de la société en utilisant l'API REST Adobe Campaign Standard. Voir [Intégration à un site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Une fois toutes ces étapes effectuées, dès qu'un utilisateur quitte le site sans commander les produits de son panier, il reçoit automatiquement un email de notification.

## Limites des messages transactionnels {#transactional-messaging-limitations}

### Conception et publication {#design-and-publication}

Au cours de la conception et de la publication de messages transactionnels, certaines des étapes à suivre ne peuvent pas être annulées. Vous devez connaître les limites suivantes :

* Un seul canal peut être utilisé pour chaque configuration d'événement. Voir la section [Créer un événement](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Une fois l'événement créé, vous ne pouvez plus modifier le canal. Par conséquent, si un message n'est pas envoyé avec succès, vous devez concevoir le mécanisme permettant de l'envoyer depuis un autre canal à l'aide d'un workflow. Voir la section [Données de workflow et processus](../../automating/using/workflow-data-and-processes.md).
* Une fois l'événement créé, vous ne pouvez pas modifier la dimension de ciblage (**[!UICONTROL Evénement temps réel]** ou **[!UICONTROL Profil]**). Voir la section [Créer un événement](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Il n'est pas possible de restaurer une publication, mais vous pouvez dépublier un événement : cette opération rend l'événement et le message transactionnel associé inaccessibles. Voir la section [Dépublier un événement](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* Le seul message transactionnel pouvant être associé à un événement est le message créé automatiquement lors de la publication de cet événement. Voir la section [Prévisualiser et publier l'événement](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personnalisation  {#personalization}

La manière dont vous pouvez personnaliser le contenu d'un message dépend du type du message transactionnel. Les spécificités sont répertoriées ci-dessous :

**Messages transactionnels basés sur un événement** :

* les informations de personnalisation proviennent des données contenues dans l'événement. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).
* Vous ne pouvez pas utiliser les blocs de contenu **Lien de désabonnement** dans un message transactionnel basé sur un événement.
* Les messages transactionnels basés sur un événement sont censés utiliser uniquement les données figurant dans l'événement envoyé pour définir le destinataire et la personnalisation du contenu du message. Il est toutefois possible d'enrichir le contenu de votre message transactionnel en utilisant des informations de la base de données Adobe Campaign. Voir [Enrichir le contenu d'un message transactionnel](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Comme les messages transactionnels basés sur un événement ne contiennent pas d'informations sur les profils, ils ne sont pas compatibles avec les règles de fatigue, même dans le cas d'un enrichissement avec des profils. Voir [Règles de fatigue](../../administration/using/fatigue-rules.md).

**Messages transactionnels basés sur un profil** :

* les informations de personnalisation peuvent provenir des données contenues dans l'événement ou de l'enregistrement de profil réconcilié. Voir [Messages transactionnels basés sur un profil](../../channels/using/profile-transactional-messages.md).
* Vous pouvez utiliser les blocs de contenu **Lien de désabonnement** dans un message transactionnel basé sur un profil. Voir [Ajouter un bloc de contenu](../../designing/using/adding-a-content-block.md).
* Les règles de fatigue sont compatibles avec les messages transactionnels basés sur un profil. Voir [Règles de fatigue](../../administration/using/fatigue-rules.md).

Les listes de produits ne sont disponibles que dans les emails transactionnels. Voir [Utiliser des listes de produits dans un message transactionnel](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissions et marques  {#permissions-and-branding}

En matière de gestion des [marques](../../administration/using/branding.md), les messages transactionnels offrent moins de souplesse que les messages standard. Adobe recommande de lier toutes les marques utilisées dans les messages transactionnels à l'entité organisationnelle **[!UICONTROL Tous]**. Pour plus d'informations, lisez l'explication détaillée ci-après.

Lorsque vous éditez un message transactionnel, vous pouvez le lier à une marque pour appliquer automatiquement certains paramètres tels que le nom ou le logo de la marque. La **[!UICONTROL Marque par défaut]** est sélectionnée par défaut dans les propriétés des messages transactionnels.

![](assets/message-center_branding.png)

Pour accéder aux messages transactionnels, vous devez appartenir au groupe de sécurité **[!UICONTROL Agents Message Center]** (mcExec) qui est lié à l'[entité organisationnelle](../../administration/using/organizational-units.md) **[!UICONTROL Message Center]**. Par conséquent, tous les objets (notamment les marques) utilisés dans un message transactionnel doivent être visibles à partir de l'unité organisationnelle **[!UICONTROL Message Center]**, ce qui signifie qu'ils doivent figurer dans les unités organisationnelles **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**.

Si la marque sélectionnée dans les propriétés du message est liée à une entité organisationnelle autre que **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**, une erreur sera générée et vous ne pourrez pas envoyer le message transactionnel.

Par conséquent, si vous souhaitez utiliser le multi-branding dans le contexte des messages transactionnels, vous devez lier toutes les marques aux unités organisationnelles **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**.

### Exporter et importer des messages transactionnels {#exporting-and-importing-transactional-messages}

* Pour exporter un message transactionnel, vous devez inclure la configuration de l'événement correspondante lors de la [création de l'export de package](../../automating/using/managing-packages.md#creating-a-package).
* Une fois le message transactionnel [importé via un package](../../automating/using/managing-packages.md#importing-a-package); il n'apparaît pas dans la liste de messages transactionnels. Il vous faut [publier](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configuration de l'événement afin de rendre le message transactionnel associé disponible.

