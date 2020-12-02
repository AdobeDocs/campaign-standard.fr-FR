---
solution: Campaign Standard
product: campaign
title: Utilisation de Triggers dans Campaign
description: null
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 100%

---


# Utilisation de Triggers dans Campaign{#using-triggers-in-campaign}

## Création d’un trigger mappé dans Campaign {#creating-a-mapped-trigger-in-campaign}

Vous devez au préalable définir les comportements que vous souhaitez contrôler dans Adobe Experience Cloud (core service **[!UICONTROL Triggers]**). Voir à ce propos la [documentation Adobe Experience Cloud](https://docs.adobe.com/content/help/fr-FR/core-services/interface/activation/triggers.html). Lorsque vous définissez le trigger, vous devez activer les alias. Pour chaque comportement (abandon de navigation/formulaire, ajout/suppression de produits, session expirée, etc.), un nouveau trigger doit être ajouté dans Adobe Experience Cloud.

Vous devez à présent créer un événement déclencheur dans Adobe Campaign. Celui-ci doit être basé sur un trigger Adobe Experience Cloud existant.

Vous pouvez regarder cette [vidéo](https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html#step-two) pour mieux comprendre comment les Triggers sont configurés dans Adobe Campaign.

Les étapes de mise en œuvre sont les suivantes :

1. Cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez **[!UICONTROL Plans marketing]** > **[!UICONTROL Messages transactionnels]** > **[!UICONTROL Triggers Experience Cloud]**.

   ![](assets/remarketing_1.png)

1. Cliquez sur le bouton **[!UICONTROL Créer.]** L’assistant de création qui s’affiche contient la liste de tous les Triggers définis dans Adobe Experience Cloud. La colonne **[!UICONTROL Nombre d’envois Analytics]** indique le nombre d’événements envoyés à Campaign par le trigger Adobe Experience Cloud. Il s’agit d’un mappage des Triggers créés dans l’interface d’Experience Cloud.

   ![](assets/remarketing_2.png)

1. Sélectionnez le trigger Adobe Experience Cloud que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Suivant]**.
1. Configurez les propriétés générales du trigger. A cette étape de l’assistant, indiquez également le canal et la dimension de ciblage à utiliser pour le trigger (voir [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources)). Validez ensuite la création du trigger.
1. Cliquez sur le bouton situé à droite du champ **[!UICONTROL Contenu et enrichissement de l’événement]** pour afficher le contenu de la payload. Cet écran vous permet également d’enrichir les données de l’événement avec les données de profil stockées dans la base de données Adobe Campaign. L’enrichissement s’effectue de la même manière que pour un message transactionnel standard.

   ![](assets/remarketing_3.png)

1. Dans le champ **[!UICONTROL Durée de validité du message transactionnel]**, définissez la durée de validité du message après l’envoi de l’événement par Analytics. Si vous définissez une durée de 2 jours, le message n’est plus envoyé une fois cette durée écoulée. Si vous suspendez plusieurs messages, ceux-ci ne sont pas envoyés en cas de reprise après un certain temps.

   ![](assets/remarketing_4.png)

1. Vous pouvez maintenant publier vos triggers. Pour plus d’informations à ce sujet, voir [Publication d’un trigger dans Campaign](../../integrating/using/using-triggers-in-campaign.md#publishing-trigger-in-campaign).

## Publication d’un trigger dans Campaign {#publishing-trigger-in-campaign}

Après avoir créé un événement déclencheur dans Adobe Campaign en fonction d’un trigger Adobe Experience Cloud existant, vous devez le publier.

1. À partir du trigger précédemment créé, cliquez sur le bouton **[!UICONTROL Publier]** pour commencer la publication de l’événement déclencheur.

   ![](assets/trigger_publish_1.png)

1. Vous pouvez vérifier l’avancement de la publication du déclencheur sous **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_2.png)

1. Lorsque la publication est terminée, le message suivant s’affiche sous **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_3.png)

1. Si vous devez apporter une modification à votre schéma de trigger même après la publication de votre événement de trigger, cliquez sur le bouton **[!UICONTROL Mettre à jour le schéma]** pour récupérer les dernières modifications.

   Cette action entraîne la dépublication de votre trigger et du message transactionnel. Vous devrez les republier par la suite.

   ![](assets/trigger_publish_4.png)

1. Cliquer sur le bouton **[!UICONTROL Afficher le trigger dans Experience Cloud]** permet d’afficher la définition du trigger dans Adobe Experience Cloud.

Une fois la publication effectuée, un modèle transactionnel associé au nouvel événement est alors automatiquement créé. Vous devez ensuite modifier et publier le modèle qui vient d’être créé. Voir à ce propos la section [Edition du modèle](../../start/using/marketing-activity-templates.md).

## Édition du modèle de message transactionnel      {#editing-the-transactional-message-template}

Une fois que vous avez créé et publié l’événement déclencheur, le modèle transactionnel correspondant est automatiquement créé. Consultez la section [Création d’un trigger mappé dans Campaign](#creating-a-mapped-trigger-in-campaign) pour en savoir plus.

Pour que l’événement entraîne l’envoi d’un message transactionnel, vous devez personnaliser ce modèle, le tester et le publier. Ces étapes sont les mêmes que pour un message transactionnel standard. Voir à ce propos la section [Modèle transactionnel](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

>[!NOTE]
>
>Si vous dépubliez le modèle, l’événement déclencheur sera automatiquement dépublié.

Lors de l’édition du contenu, vous pouvez ajouter un champ de personnalisation basé sur les informations envoyées par le trigger Analytics. Si vous enrichissez les données de l’événement avec les données de profil Adobe Campaign, vous pouvez personnaliser le message selon ces informations. Pour personnaliser votre message, sélectionnez **[!UICONTROL Evénement transactionnel]** > **[!UICONTROL Contexte de l’événement]**, puis un champ.

![](assets/remarketing_8.png)

## Accès aux rapports {#accessing-the-reports}

Pour afficher le rapport de trigger dédié dans Adobe Campaign, ouvrez l’événement déclencheur que vous avez précédemment créé, puis cliquez sur **[!UICONTROL Afficher le rapport]**.

![](assets/remarketing_9.png)

Le rapport montre le nombre d’événements traités par rapport au nombre d’événements envoyés par Analytics. Il affiche également la liste de tous les Triggers récents.

![](assets/trigger_uc_browse_14.png)

