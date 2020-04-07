---
title: A propos des messages transactionnels
description: Découvrez les différents types de messages transactionnels que vous pouvez envoyer et leur utilisation dans Adobe Campaign.
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
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# A propos des messages transactionnels{#about-transactional-messaging}

Vous pouvez créer et gérer des messages transactionnels personnalisés dans Adobe Campaign.

Un message transactionnel est une communication individuelle et unique transmise à un utilisateur par un prestataire tel qu&#39;un site web.

* Ce type de message est particulièrement attendu, car il est porteur d&#39;une information que son destinataire souhaite vérifier ou confirmer. Il peut s&#39;agir par exemple d&#39;un message de bienvenue à l&#39;ouverture d&#39;un compte, d&#39;une confirmation d&#39;expédition de commande, d&#39;une facture ou d&#39;un message de confirmation de changement de mot de passe.
* Il s&#39;agit d&#39;un message important qui définit la relation client : l&#39;utilisateur s&#39;attend à un envoi en temps réel. Le délai entre le déclenchement de l&#39;événement et l&#39;arrivée du message doit donc être très court.
* Les messages transactionnels bénéficient en général d&#39;un taux d&#39;ouverture élevé.

Adobe Campaign permet d&#39;intégrer cette fonctionnalité à un système d&#39;information qui lui envoie les événements destinés à être transformés en messages transactionnels personnalisés.

>[!NOTE]
>
>Selon vos options, les messages transactionnels peuvent être envoyés par email, SMS ou notification push. Veuillez vérifier votre accord de licence.

Dans Adobe Campaign, deux types de message transactionnel sont disponibles :

* [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md) ciblant un événement. Les données contenues dans l&#39;événement sont utilisées pour définir la cible de la diffusion.
* [Messages transactionnels basés sur un profil](../../channels/using/profile-transactional-messages.md) ciblant des profils de la base de données marketing Adobe Campaign. Vous pouvez utiliser les informations de la base de données Adobe Campaign pour envoyer un message transactionnel selon les profils marketing des clients.

Le type du message est défini lors de la configuration de l&#39;événement qui sera transformé en message transactionnel. Voir [Configuration des messages transactionnels](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign donne la priorité au traitement des messages transactionnels par rapport à toute autre diffusion.

Les messages transactionnels sont également disponibles depuis l&#39;API Adobe Campaign Standard. Consultez à ce sujet la [documentation dédiée](../../api/using/managing-transactional-messages.md).

>[!IMPORTANT]
>
>Une fois la mise à niveau effectuée vers le [MTA amélioré](https://helpx.adobe.com/fr/campaign/kb/campaign-enhanced-mta.html), tous les messages transactionnels sont envoyés à l’aide de celui-ci afin d’améliorer la délivrabilité, le débit et la gestion des bounces. Les impacts sont identiques à ceux des messages marketing standard. Ils sont présentés dans le document [Serveur de diffusion MTA amélioré d’Adobe Campaign](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

## Principe de fonctionnement des messages transactionnels {#transactional-messaging-operating-principle}

Prenons le cas d&#39;une société disposant d&#39;un site web, sur lequel ses clients peuvent acheter des produits.

Adobe Campaign vous permet d&#39;envoyer un email de notification aux utilisateurs du site ayant ajouté des produits dans leur panier : lorsque l&#39;un d&#39;eux quitte le site sans poursuivre ses achats, un email d&#39;abandon de panier lui est automatiquement envoyé.

Les étapes de mise en œuvre sont les suivantes :

1. Configurez un événement qui sera nommé &quot;Abandon de panier&quot;. La publication de la configuration de cet événement crée automatiquement un message transactionnel. La création et la publication d&#39;un événement sont présentées dans la section [Configuration d&#39;un événement pour envoyer un message transactionnel basé sur un événement](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).
1. Le message transactionnel doit être personnalisé, testé, puis publié. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).
1. Par ailleurs, pour que cet événement soit déclenché lorsqu&#39;un client abandonne son panier, il faut l&#39;envoyer depuis le site web de la société en utilisant l&#39;API REST Adobe Campaign Standard. Voir [Intégration à un site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Une fois toutes ces étapes effectuées, dès qu&#39;un utilisateur quitte le site sans commander les produits de son panier, il reçoit automatiquement un email de notification.

## Processus de publication de messages transactionnels {#transactional-messaging-pub-process}

Le graphique ci-dessous illustre le processus de publication de messages transactionnels.

![](assets/message-center_pub-process.png)

Pour plus d&#39;informations sur les étapes de configuration des événements, voir [Configuration des messages transactionnels](../../administration/using/configuring-transactional-messaging.md).

## Limites des messages transactionnels {#transactional-messaging-limitations}

>[!NOTE]
>
>Pour accéder aux messages transactionnels, vous devez disposer des droits d&#39;administration.

### Conception et publication {#design-and-publication}

Au cours de la conception et de la publication de messages transactionnels, certaines des étapes à suivre ne peuvent pas être annulées. Vous devez connaître les limites suivantes :

* Un seul canal peut être utilisé pour chaque configuration d&#39;événement. Voir la section [Créer un événement](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Une fois l&#39;événement créé, vous ne pouvez plus modifier le canal. Par conséquent, si un message n&#39;est pas envoyé avec succès, vous devez concevoir le mécanisme permettant de l&#39;envoyer depuis un autre canal à l&#39;aide d&#39;un workflow. Voir la section [Données de workflow et processus](../../automating/using/workflow-data-and-processes.md).
* You cannot change the targeting dimension ( **[!UICONTROL Real-time event]** or **[!UICONTROL Profile]** ) after the event is created. Voir la section [Créer un événement](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Il n&#39;est pas possible de restaurer une publication, mais vous pouvez dépublier un événement : cette opération rend l&#39;événement et le message transactionnel associé inaccessibles. Voir la section [Dépublier un événement](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* Le seul message transactionnel pouvant être associé à un événement est le message créé automatiquement lors de la publication de cet événement. Voir la section [Prévisualiser et publier l&#39;événement](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personnalisation   {#personalization}

La manière dont vous pouvez personnaliser le contenu d&#39;un message dépend du type du message transactionnel. Les spécificités sont répertoriées ci-dessous :

**Messages transactionnels basés sur un événement** :

* les informations de personnalisation proviennent des données contenues dans l&#39;événement. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).
* Vous ne pouvez pas utiliser les blocs de contenu **Lien de désabonnement** dans un message transactionnel basé sur un événement.
* Les messages transactionnels basés sur un événement sont censés utiliser uniquement les données figurant dans l&#39;événement envoyé pour définir le destinataire et la personnalisation du contenu du message. Il est toutefois possible d&#39;enrichir le contenu de votre message transactionnel en utilisant des informations de la base de données Adobe Campaign. Voir [Enrichir le contenu d&#39;un message transactionnel](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Comme les messages transactionnels basés sur un événement ne contiennent pas d&#39;informations sur les profils, ils ne sont pas compatibles avec les règles de fatigue, même dans le cas d&#39;un enrichissement avec des profils. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

**Messages transactionnels basés sur un profil** :

* les informations de personnalisation peuvent provenir des données contenues dans l&#39;événement ou de l&#39;enregistrement de profil réconcilié. Voir [Messages transactionnels basés sur un profil](../../channels/using/profile-transactional-messages.md).
* Vous pouvez utiliser les blocs de contenu **Lien de désabonnement** dans un message transactionnel basé sur un profil. Voir [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block).
* Les règles de fatigue sont compatibles avec les messages transactionnels basés sur un profil. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

Les listes de produits ne sont disponibles que dans les emails transactionnels. Voir [Utiliser des listes de produits dans un message transactionnel](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissions et marques   {#permissions-and-branding}

En matière de gestion des [marques](../../administration/using/branding.md), les messages transactionnels offrent moins de souplesse que les messages standard. Adobe recommends linking all brands used in transactional messages to the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md). Pour plus d&#39;informations, lisez l&#39;explication détaillée ci-après.

Lorsque vous éditez un message transactionnel, vous pouvez le lier à une marque pour appliquer automatiquement certains paramètres tels que le nom ou le logo de la marque. The **[!UICONTROL Default brand]** is selected by default in the transactional message properties.

![](assets/message-center_branding.png)

All objects (including branding) used in a transactional message must be visible from the **[!UICONTROL Message Center]** organizational unit, meaning that these objects must be in the **[!UICONTROL Message Center]** or **[!UICONTROL All]** organizational units.

However, if the brand selected in the message properties is linked to an organizational unit which is different from **[!UICONTROL Message Center]** or **[!UICONTROL All]**, this will cause an error and you will not be able to send the transactional message.

Therefore, if you want to use multi-branding in the context of transactional messaging, you should link all brands either to the **[!UICONTROL Message Center]** organizational unit or to the **[!UICONTROL All]** organizational unit.

### Exporter et importer des messages transactionnels {#exporting-and-importing-transactional-messages}

* Pour exporter un message transactionnel, vous devez inclure la configuration de l&#39;événement correspondante lors de la [création de l&#39;export de package](../../automating/using/managing-packages.md#creating-a-package).
* Une fois le message transactionnel [importé via un package](../../automating/using/managing-packages.md#importing-a-package); il n&#39;apparaît pas dans la liste de messages transactionnels. Il vous faut [publier](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configuration de l&#39;événement afin de rendre le message transactionnel associé disponible.

