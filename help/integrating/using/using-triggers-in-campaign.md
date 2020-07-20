---
title: Utilisation de Triggers dans Campaign
description: null
page-status-flag: never-activated
uuid: d844d013-b38a-4e69-9df5-0edc01fa9c6e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: a524c700-bad6-4fcf-857a-c31bfae4d30c
internal: n
snippet: y
translation-type: ht
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: ht
source-wordcount: '694'
ht-degree: 100%

---


# Utilisation de Triggers dans Campaign{#using-triggers-in-campaign}

## Création d&#39;un trigger mappé dans Campaign {#creating-a-mapped-trigger-in-campaign}

Vous devez au préalable définir les comportements que vous souhaitez contrôler dans Adobe Experience Cloud (core service **[!UICONTROL Triggers]**). Voir à ce propos la [documentation Adobe Experience Cloud](https://docs.adobe.com/content/help/fr-FR/core-services/interface/activation/triggers.html). Lorsque vous définissez le trigger, vous devez activer les alias. Pour chaque comportement (abandon de navigation/formulaire, ajout/suppression de produits, session expirée, etc.), un nouveau trigger doit être ajouté dans Adobe Experience Cloud.

Vous devez à présent créer un événement déclencheur dans Adobe Campaign. Celui-ci doit être basé sur un trigger Adobe Experience Cloud existant.

Vous pouvez regarder cette [vidéo](https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html#step-two) pour mieux comprendre comment les Triggers sont configurés dans Adobe Campaign.

Les étapes de mise en œuvre sont les suivantes :

1. Cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez **[!UICONTROL Plans marketing]** > **[!UICONTROL Messages transactionnels]** > **[!UICONTROL Triggers Experience Cloud]**.

   ![](assets/remarketing_1.png)

1. Cliquez sur le bouton **[!UICONTROL Créer.]** L&#39;assistant de création qui s&#39;affiche contient la liste de tous les Triggers définis dans Adobe Experience Cloud. La colonne **[!UICONTROL Nombre d&#39;envois Analytics]** indique le nombre d&#39;événements envoyés à Campaign par le trigger Adobe Experience Cloud. Il s&#39;agit d&#39;un mappage des Triggers créés dans l&#39;interface d&#39;Experience Cloud.

   ![](assets/remarketing_2.png)

1. Sélectionnez le trigger Adobe Experience Cloud que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Suivant]**.
1. Configurez les propriétés générales du trigger. A cette étape de l&#39;assistant, indiquez également le canal et la dimension de ciblage à utiliser pour le trigger (voir [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources)). Validez ensuite la création du trigger.
1. Cliquez sur le bouton situé à droite du champ **[!UICONTROL Contenu et enrichissement de l&#39;événement]** pour afficher le contenu de la payload. Cet écran vous permet également d&#39;enrichir les données de l&#39;événement avec les données de profil stockées dans la base de données Adobe Campaign. L&#39;enrichissement s&#39;effectue de la même manière que pour un message transactionnel standard.

   ![](assets/remarketing_3.png)

1. Dans le champ **[!UICONTROL Durée de validité du message transactionnel]**, définissez la durée de validité du message après l&#39;envoi de l&#39;événement par Analytics. Si vous définissez une durée de 2 jours, le message n&#39;est plus envoyé une fois cette durée écoulée. Si vous suspendez plusieurs messages, ceux-ci ne sont pas envoyés en cas de reprise après un certain temps.

   ![](assets/remarketing_4.png)

1. Cliquez sur le bouton **[!UICONTROL Publier]** pour lancer la publication de l&#39;événement déclencheur.
1. Si vous devez apporter une modification à votre schéma de trigger même après la publication de votre événement de trigger, cliquez sur le bouton **[!UICONTROL Mettre à jour le schéma]** pour récupérer les dernières modifications.

   Cette action entraîne la dépublication de votre trigger et du message transactionnel. Vous devrez les republier par la suite.

   ![](assets/remarketing_11.png)

Le bouton **[!UICONTROL Afficher le trigger dans Experience Cloud]** permet d&#39;afficher la définition du trigger dans Adobe Experience Cloud.

Une fois la publication effectuée, un modèle transactionnel associé au nouvel événement est alors automatiquement créé. Vous devez ensuite modifier et publier le modèle qui vient d&#39;être créé. Voir à ce propos la section [Edition du modèle](../../start/using/marketing-activity-templates.md).

## Édition du modèle de message transactionnel   {#editing-the-transactional-message-template}

Une fois que vous avez créé et publié l&#39;événement déclencheur, le modèle transactionnel correspondant est automatiquement créé. Consultez la section [Création d&#39;un trigger mappé dans Campaign](#creating-a-mapped-trigger-in-campaign) pour en savoir plus.

Pour que l&#39;événement entraîne l&#39;envoi d&#39;un message transactionnel, vous devez personnaliser ce modèle, le tester et le publier. Ces étapes sont les mêmes que pour un message transactionnel standard. Voir à ce propos la section [Modèle transactionnel](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

>[!NOTE]
>
>Si vous dépubliez le modèle, l&#39;événement déclencheur sera automatiquement dépublié.

Lors de l&#39;édition du contenu, vous pouvez ajouter un champ de personnalisation basé sur les informations envoyées par le trigger Analytics. Si vous enrichissez les données de l&#39;événement avec les données de profil Adobe Campaign, vous pouvez personnaliser le message selon ces informations. Pour personnaliser votre message, sélectionnez **[!UICONTROL Evénement transactionnel]** > **[!UICONTROL Contexte de l&#39;événement]**, puis un champ.

![](assets/remarketing_8.png)

## Accès aux rapports {#accessing-the-reports}

Pour afficher le rapport de trigger dédié dans Adobe Campaign, ouvrez l&#39;événement déclencheur que vous avez précédemment créé, puis cliquez sur **[!UICONTROL Afficher le rapport]**.

![](assets/remarketing_9.png)

Le rapport montre le nombre d&#39;événements traités par rapport au nombre d&#39;événements envoyés par Analytics. Il affiche également la liste de tous les Triggers récents.

![](assets/trigger_uc_browse_14.png)

