---
solution: Campaign Standard
product: campaign
title: Limites des messages transactionnels
description: Découvrez les principales recommandations et limitations concernant les messages transactionnels à Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 0092ad11314fab232663f558ca6635b8fcc03133
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 83%

---


# Meilleures pratiques et limites de la messagerie transactionnelle {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

Cette section liste les meilleures pratiques et les limites que vous devez connaître avant de commencer à créer des messages transactionnels.

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## Autorisations {#permissions}

Seuls les utilisateurs dotés du rôle [Administration](../../administration/using/users-management.md#functional-administrators) peuvent configurer des événements transactionnels et des messages transactionnels d’accès.

## Configuration et publication d’événement {#design-and-publication}

Au cours de la configuration et de la publication de messages transactionnels, certaines des étapes à suivre ne peuvent pas être annulées. Vous devez connaître les limites suivantes :

* Les canaux disponibles pour la messagerie transactionnelle sont les suivants : **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** et **[!UICONTROL Notification push]**.
* Un seul canal peut être utilisé pour chaque configuration d’événement. Voir la section [Créer un événement](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Une fois l’événement créé, vous ne pouvez plus modifier le canal. Par conséquent, si un message n&#39;est pas envoyé avec succès, vous devez concevoir le mécanisme permettant de l&#39;envoyer depuis un autre canal à l&#39;aide d&#39;un workflow. Voir la section [Données de workflow et processus](../../automating/using/get-started-workflows.md).
* Une fois l&#39;événement créé, vous ne pouvez pas modifier la dimension de ciblage (**[!UICONTROL Evénement temps réel]** ou **[!UICONTROL Profil]**). Voir la section [Créer un événement](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Il n&#39;est pas possible de restaurer une publication, mais vous pouvez dépublier un événement : cette opération rend l&#39;événement et le message transactionnel associé inaccessibles. Voir la section [Dépublier un événement](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
* Le seul message transactionnel pouvant être associé à un événement est le message créé automatiquement lors de la publication de cet événement. Voir la section [Prévisualiser et publier l&#39;événement](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Nombre de messages transactionnels {#transactional-message-number}

Le nombre de messages transactionnels publiés peut avoir un impact significatif sur votre plateforme. Pour des performances optimales, le nombre de messages transactionnels publiés doit rester inférieur à 100. Pour ce faire, annulez la publication ou supprimez les messages transactionnels inutilisés. Voir [Annulation de la publication d&#39;un message transactionnel](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) et [Suppression d&#39;un message transactionnel](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

Pour optimiser les performances, vous pouvez également annuler la publication ou supprimer des événements inutilisés. En effet, l’annulation de publication ou la suppression d’un événement entraînera également l’annulation de la publication ou la suppression des messages transactionnels correspondants, ainsi que de leur envoi et de leurs logs de tracking, le cas échéant. Voir [Annulation de la publication d&#39;un événement](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) et [Suppression d&#39;un événement](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Personnalisation        {#personalization}

La manière dont vous pouvez personnaliser le contenu d&#39;un message dépend du type du message transactionnel. Les spécificités sont répertoriées ci-dessous.

### Messages transactionnels basés sur un événement.

* Les informations de personnalisation proviennent des données contenues dans l’événement. Voir [Configuration des messages transactionnels basés sur un événement](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* Vous ne **pouvez pas** utiliser les blocs de contenu **[!UICONTROL Lien de désabonnement]** dans un message transactionnel basé sur un événement.
* Les messages transactionnels basés sur un événement sont censés utiliser uniquement les données figurant dans l’événement envoyé pour définir le destinataire et la personnalisation du contenu du message. Il est toutefois possible d’enrichir le contenu de votre message transactionnel en utilisant des informations de la base de données Adobe Campaign. Voir [Enrichissement d&#39;un événement](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) et [Personnalisation d&#39;un message transactionnel](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* Comme les messages transactionnels basés sur un événement ne contiennent pas d’informations sur les profils, ils ne sont pas compatibles avec les règles de fatigue, même dans le cas d’un enrichissement avec des profils.

### Messages transactionnels basés sur un profil  

* Les informations de personnalisation peuvent provenir des données contenues dans l’événement ou de l’enregistrement de profil réconcilié. Voir [Configuration des messages transactionnels basés sur un profil](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) et [Caractéristiques des messages transactionnels basés sur un profil](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* Vous **pouvez** utiliser les blocs de contenu **[!UICONTROL Lien de désabonnement]** dans un message transactionnel basé sur un profil. Voir [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block).
* Les règles de fatigue sont compatibles avec les messages transactionnels basés sur un profil. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

### Listes de produits

Les listes de produits ne sont disponibles que dans les **emails transactionnels**. Voir [Utiliser des listes de produits dans un message transactionnel](../../channels/using/editing-transactional-message.md#using-product-listings-in-a-transactional-message).

## Marques {#permissions-and-branding}

En matière de gestion des [marques](../../administration/using/branding.md), les messages transactionnels offrent moins de souplesse que les messages standard. Adobe recommande de lier toutes les marques utilisées dans les messages transactionnels à l&#39;entité organisationnelle **** Tous[](../../administration/using/organizational-units.md). Pour plus d&#39;informations, lisez l&#39;explication détaillée ci-après.

Lorsque vous éditez un message transactionnel, vous pouvez le lier à une marque pour appliquer automatiquement certains paramètres tels que le nom ou le logo de la marque. La **[!UICONTROL Marque par défaut]** est sélectionnée par défaut dans les propriétés des messages transactionnels.

![](assets/message-center_branding.png)

Tous les objets (notamment les marques) utilisés dans un message transactionnel doivent être visibles à partir de l&#39;entité organisationnelle **[!UICONTROL Message Center]**, ce qui signifie qu&#39;ils doivent figurer dans les entités organisationnelles **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**.

Si la marque sélectionnée dans les propriétés du message est liée à une entité organisationnelle autre que **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**, une erreur sera générée et vous ne pourrez pas envoyer le message transactionnel.

Par conséquent, si vous souhaitez utiliser le multi-branding dans le contexte des messages transactionnels, vous devez lier toutes les marques aux entités organisationnelles **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**.

## Exporter et importer des messages transactionnels {#exporting-and-importing-transactional-messages}

* Pour exporter un message transactionnel, vous devez inclure la configuration de l&#39;événement correspondante lors de la [création de l&#39;export de package](../../automating/using/managing-packages.md#creating-a-package).
* Une fois le message transactionnel [importé via un package](../../automating/using/managing-packages.md#importing-a-package); il n&#39;apparaît pas dans la liste de messages transactionnels. Il vous faut [publier](../../channels/using/publishing-transactional-event.md) la configuration de l&#39;événement afin de rendre le message transactionnel associé disponible.
