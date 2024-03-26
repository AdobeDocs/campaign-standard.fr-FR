---
title: Utiliser les Triggers dans Campaign
description: Créez un événement Trigger dans Adobe Campaign, basé sur un Trigger Adobe Experience Cloud existant.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6b8d5118-89ed-49c2-b601-0aff472fcadd
source-git-commit: cf2ded703e53d6db27e62712734f7ea846da9a21
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 100%

---

# Utiliser les Triggers dans Campaign{#using-triggers-in-campaign}

## Création d&#39;un Trigger mappé dans Campaign {#creating-a-mapped-trigger-in-campaign}

>[!NOTE]
>
>Pour créer des déclencheurs, vous aurez besoin du rôle **[!UICONTROL Administration]** ou vous devrez appartenir au groupe de sécurité **[!UICONTROL Administrateurs]**. Pour plus d’informations à ce propos, consultez cette [page](../../administration/using/list-of-roles.md).

Vous devez au préalable définir les comportements que vous souhaitez surveiller dans Adobe Experience Cloud (core service **[!UICONTROL Triggers]**). Voir à ce propos la [documentation Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=fr). Lorsque vous définissez le déclencheur, vous devez activer les alias. Pour chaque comportement (abandon de navigation/formulaire, ajout/suppression de produits, session expirée, etc.), un nouveau déclencheur doit être ajouté dans Adobe Experience Cloud.

Vous devez à présent créer un événement déclencheur dans Adobe Campaign. Celui-ci doit être basé sur un déclencheur Adobe Experience Cloud existant.

Les étapes de mise en œuvre sont les suivantes :

1. Cliquez sur le logo **Adobe**, en haut à gauche, puis sélectionnez **[!UICONTROL Plans de marketing]** > **[!UICONTROL Messages transactionnels]** > **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Cliquez sur le bouton **[!UICONTROL Créer.]** L’assistant de création qui s’affiche contient la liste de tous les déclencheurs définis dans Adobe Experience Cloud. La colonne **[!UICONTROL Nombre d’envois Analytics]** indique le nombre d’événements envoyés à Campaign par le déclencheur Adobe Experience Cloud. Il s’agit d’un mappage des déclencheurs créés dans l’interface d’Experience Cloud.

   ![](assets/remarketing_2.png)

1. Sélectionnez le déclencheur Adobe Experience Cloud que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Suivant]**.
1. Configurez les propriétés générales du déclencheur. A cette étape de l’assistant, indiquez également le canal et la dimension de ciblage à utiliser pour le déclencheur (voir [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources)). Validez ensuite la création du déclencheur.
1. Cliquez sur le bouton situé à droite du champ **[!UICONTROL Contenu et enrichissement de l’événement]** pour afficher le contenu de la payload. Cet écran vous permet également d’enrichir les données de l’événement avec les données de profil stockées dans la base de données Adobe Campaign. L’enrichissement s’effectue de la même manière que pour un message transactionnel standard.

   ![](assets/remarketing_3.png)

1. Dans le champ **[!UICONTROL Durée de validité du message transactionnel]**, définissez la durée de validité du message après l’envoi de l’événement par Analytics. Si vous définissez une durée de 2 jours, le message n’est plus envoyé une fois cette durée écoulée. Si vous suspendez plusieurs messages, ceux-ci ne sont pas envoyés en cas de reprise après un certain temps.

   ![](assets/remarketing_4.png)

1. Vous pouvez maintenant publier vos déclencheurs. Pour plus d’informations à ce sujet, voir [Publication d’un déclencheur dans Campaign](../../integrating/using/using-triggers-in-campaign.md#publishing-trigger-in-campaign).

## Publication d&#39;un Trigger dans Campaign {#publishing-trigger-in-campaign}

Après avoir créé un événement déclencheur dans Adobe Campaign en fonction d’un déclencheur Adobe Experience Cloud existant, vous devez le publier.

1. À partir du déclencheur précédemment créé, cliquez sur le bouton **[!UICONTROL Publier]** pour commencer la publication de l’événement déclencheur.

   ![](assets/trigger_publish_1.png)

1. Vous pouvez vérifier l’avancement de la publication du déclencheur sous **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_2.png)

1. Lorsque la publication est terminée, le message suivant s’affiche sous **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_3.png)

1. Si vous devez apporter une modification à votre schéma de déclencheur même après la publication de votre événement de déclencheur, cliquez sur le bouton **[!UICONTROL Mettre à jour le schéma]** pour récupérer les dernières modifications.

   Cette action entraîne la dépublication de votre déclencheur et du message transactionnel. Vous devrez les republier par la suite.

   ![](assets/trigger_publish_4.png)

1. Cliquer sur le bouton **[!UICONTROL Afficher le déclencheur dans Experience Cloud]** permet d’afficher la définition du déclencheur dans Adobe Experience Cloud.

Une fois la publication effectuée, un modèle transactionnel associé au nouvel événement est alors automatiquement créé. Vous devez ensuite modifier et publier le modèle qui vient d’être créé. Pour plus d&#39;informations, consultez la section [Edition du modèle](../../start/using/marketing-activity-templates.md).

## Édition du modèle de message transactionnel         {#editing-the-transactional-message-template}

Une fois que vous avez créé et publié l’événement déclencheur, le modèle transactionnel correspondant est automatiquement créé. Consultez la section [Création d’un déclencheur mappé dans Campaign](#creating-a-mapped-trigger-in-campaign) pour en savoir plus.

Pour que l’événement entraîne l’envoi d’un message transactionnel, vous devez personnaliser ce modèle, le tester et le publier. Ces étapes sont les mêmes que pour un message transactionnel standard. Pour plus d&#39;informations, consultez la section [Modifier un message transactionnel](../../channels/using/editing-transactional-message.md).

>[!NOTE]
>
>Si vous dépubliez le modèle, l’événement déclencheur sera automatiquement dépublié.

Lors de l’édition du contenu, vous pouvez ajouter un champ de personnalisation basé sur les informations envoyées par le déclencheur Analytics. Si vous enrichissez les données de l’événement avec les données de profil Adobe Campaign, vous pouvez personnaliser le message selon ces informations. Pour personnaliser votre message, sélectionnez **[!UICONTROL Evénement transactionnel]** > **[!UICONTROL Contexte de l’événement]**, puis un champ.

![](assets/remarketing_8.png)

## Accès aux rapports {#accessing-the-reports}

Pour afficher le rapport de trigger dédié dans Adobe Campaign, ouvrez l&#39;événement déclencheur que vous avez précédemment créé, puis cliquez sur **[!UICONTROL Afficher le rapport]**.

![](assets/remarketing_9.png)

Le rapport montre le nombre d’événements traités par rapport au nombre d’événements envoyés par Analytics. Il affiche également la liste de tous les déclencheurs récents.

![](assets/trigger_uc_browse_14.png)
