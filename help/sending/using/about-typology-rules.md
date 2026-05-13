---
title: À propos des typologies et des règles de typologie
description: Découvrez comment les typologies et les règles de typologie fonctionnent dans Adobe Campaign.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
TQID: https://experienceleague.adobe.com/fFTJTgKfIhII-D6pefx9hqnX3a022odFZS5AAmNK1Ao
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 193
ht-degree: 100%

---

# À propos des typologies et des règles de typologie{#about-typology-rules}

Campaign Standard vous permet de lier un message à une **typologie**, afin de vérifier si le message est valide et répond à vos critères de qualité.

Les typologies sont des ensembles de **règles de typologie**, qui sont exécutés pendant la phase d’analyse du message. Elles vous permettent de vous assurer que vos e-mails contiennent toujours certains éléments (comme un lien de désinscription ou une ligne d’objet) ou des règles de filtrage pour exclure des groupes de votre cible visée (tels que les clients désabonnés, les concurrents et les clients ne faisant pas partie du programme de fidélité).

![](assets/typology_messagelink.png)

Des typologies prêtes à l&#39;emploi et des règles de typologie sont disponibles dans Campaign Standard. En fonction de vos besoins, vous pouvez également créer de nouvelles règles et les ajouter à des typologies existantes ou nouvelles pour les lier à vos messages.

Pour créer et appliquer une typologie aux messages, procédez comme suit :

1. Créez des règles de typologie (voir [cette section](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Créez une typologie et référencez les règles que vous avez créées dans celle-ci (voir [cette section](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configurez votre diffusion pour utiliser la typologie que vous avez créée (voir [cette section](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Pendant la préparation du message, les profils sont exclus lorsque le critère est satisfait. Vous pouvez consulter les logs pour surveiller les exclusions.
