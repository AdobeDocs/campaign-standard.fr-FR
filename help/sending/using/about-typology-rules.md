---
title: 'A propos des typologies et des '
description: Découvrez comment les typologies et les  de fonctionnent dans  Adobe Campaign.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a9c0e3cc4609e747bbfebeb90049862f29c9d8d9

---


# A propos des typologies et des{#about-typology-rules}

Campaign Standard vous permet de lier un message à une **typologie**, afin de vérifier si le message est valide et répond à vos critères de qualité.

Les typologies sont des ensembles de ****, qui sont exécutés pendant la phase  du message  la phase du. Elles vous permettent de vous assurer que vos courriels contiennent toujours certains éléments (comme un lien de  ou une ligne d’objet) ou des règles de filtrage pour exclure des groupes de votre  de (tels que les clients non abonnés, les clients non fidèles ou les clients non abonnés).

![](assets/typology_messagelink.png)

Les typologies prêtes à l&#39;emploi et les  de sont disponibles dans Campaign Standard. En fonction de vos besoins, vous pouvez également créer de nouvelles règles et les ajouter à des typologies existantes ou nouvelles pour lier vos messages.

Pour créer et appliquer une typologie aux messages, procédez comme suit :

1. Créez des  (voir [cette section](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Create a typology and reference the rules you created into it (see [this section](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configurez votre  pour utiliser la typologie que vous avez créée (voir [cette section](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Pendant la préparation du message, les  sont exclus lorsque le critère est satisfait. Vous pouvez consulter les journaux pour surveiller les exclusions.
