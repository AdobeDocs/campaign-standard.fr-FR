---
solution: Campaign Standard
product: campaign
title: Limites des messages transactionnels
description: Découvrez les principales limites et recommandations concernant les messages transactionnels dans Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 100%

---


# Limites des messages transactionnels {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

La section ci-dessous répertorie les limites que vous devez connaître avant de créer des messages transactionnels.

Pour plus d’informations sur les messages transactionnels, y compris sur leur configuration et leur création, voir la section [Prise en main de la messagerie transactionnelle](../../channels/using/getting-started-with-transactional-msg.md).

>[!IMPORTANT]
>
>Pour accéder aux messages transactionnels, vous devez disposer des droits d&#39;administration.

## Conception et publication {#design-and-publication}

Au cours de la conception et de la publication de messages transactionnels, certaines des étapes à suivre ne peuvent pas être annulées. Vous devez connaître les limites suivantes :

* Un seul canal peut être utilisé pour chaque configuration d’événement. Voir la section [Créer un événement](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Une fois l’événement créé, vous ne pouvez plus modifier le canal. Par conséquent, si un message n&#39;est pas envoyé avec succès, vous devez concevoir le mécanisme permettant de l&#39;envoyer depuis un autre canal à l&#39;aide d&#39;un workflow. Voir la section [Données de workflow et processus](../../automating/using/get-started-workflows.md).
* Une fois l&#39;événement créé, vous ne pouvez pas modifier la dimension de ciblage (**[!UICONTROL Evénement temps réel]** ou **[!UICONTROL Profil]**). Voir la section [Créer un événement](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Il n&#39;est pas possible de restaurer une publication, mais vous pouvez dépublier un événement : cette opération rend l&#39;événement et le message transactionnel associé inaccessibles. Voir la section [Dépublier un événement](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* Le seul message transactionnel pouvant être associé à un événement est le message créé automatiquement lors de la publication de cet événement. Voir la section [Prévisualiser et publier l&#39;événement](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

## Personnalisation        {#personalization}

La manière dont vous pouvez personnaliser le contenu d&#39;un message dépend du type du message transactionnel. Les spécificités sont répertoriées ci-dessous.

### Messages transactionnels basés sur un événement.

* les informations de personnalisation proviennent des données contenues dans l&#39;événement. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).
* Vous ne **pouvez pas** utiliser les blocs de contenu **[!UICONTROL Lien de désabonnement]** dans un message transactionnel basé sur un événement.
* Les messages transactionnels basés sur un événement sont censés utiliser uniquement les données figurant dans l’événement envoyé pour définir le destinataire et la personnalisation du contenu du message. Il est toutefois possible d’enrichir le contenu de votre message transactionnel en utilisant des informations de la base de données Adobe Campaign. Voir [Enrichir le contenu d’un message transactionnel](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Comme les messages transactionnels basés sur un événement ne contiennent pas d&#39;informations sur les profils, ils ne sont pas compatibles avec les règles de fatigue, même dans le cas d&#39;un enrichissement avec des profils. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

### Messages transactionnels basés sur un profil  

* les informations de personnalisation peuvent provenir des données contenues dans l&#39;événement ou de l&#39;enregistrement de profil réconcilié. Voir [Messages transactionnels basés sur un profil](../../channels/using/profile-transactional-messages.md).
* Vous **pouvez** utiliser les blocs de contenu **[!UICONTROL Lien de désabonnement]** dans un message transactionnel basé sur un profil. Voir [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block).
* Les règles de fatigue sont compatibles avec les messages transactionnels basés sur un profil. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

Les listes de produits ne sont disponibles que dans les emails transactionnels. Voir [Utiliser des listes de produits dans un message transactionnel](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

## Permissions et marques        {#permissions-and-branding}

En matière de gestion des [marques](../../administration/using/branding.md), les messages transactionnels offrent moins de souplesse que les messages standard. Adobe recommande de lier toutes les marques utilisées dans les messages transactionnels à l&#39;entité organisationnelle **** Tous[](../../administration/using/organizational-units.md). Pour plus d&#39;informations, lisez l&#39;explication détaillée ci-après.

Lorsque vous éditez un message transactionnel, vous pouvez le lier à une marque pour appliquer automatiquement certains paramètres tels que le nom ou le logo de la marque. La **[!UICONTROL Marque par défaut]** est sélectionnée par défaut dans les propriétés des messages transactionnels.

![](assets/message-center_branding.png)

Tous les objets (notamment les marques) utilisés dans un message transactionnel doivent être visibles à partir de l&#39;entité organisationnelle **[!UICONTROL Message Center]**, ce qui signifie qu&#39;ils doivent figurer dans les entités organisationnelles **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**.

Si la marque sélectionnée dans les propriétés du message est liée à une entité organisationnelle autre que **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**, une erreur sera générée et vous ne pourrez pas envoyer le message transactionnel.

Par conséquent, si vous souhaitez utiliser le multi-branding dans le contexte des messages transactionnels, vous devez lier toutes les marques aux entités organisationnelles **[!UICONTROL Message Center]** ou **[!UICONTROL Tous]**.

## Exporter et importer des messages transactionnels {#exporting-and-importing-transactional-messages}

* Pour exporter un message transactionnel, vous devez inclure la configuration de l&#39;événement correspondante lors de la [création de l&#39;export de package](../../automating/using/managing-packages.md#creating-a-package).
* Une fois le message transactionnel [importé via un package](../../automating/using/managing-packages.md#importing-a-package); il n&#39;apparaît pas dans la liste de messages transactionnels. Il vous faut [publier](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configuration de l&#39;événement afin de rendre le message transactionnel associé disponible.
