---
title: '"Cas pratique de workflow : diffusion cross-canal"'
description: '"Cas pratique de workflow : diffusion cross-canal"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Cas pratique de workflow : création d’une diffusion cross-canal{#cross-channel-delivery}

Ce document vous permet de découvrir la fonctionnalité d&#39;Adobe Campaign suivante via un cas pratique standard : création d&#39;un workflow de diffusion cross-canal.

Dans ce cas pratique, l&#39;objectif est de sélectionner une audience parmi les destinataires de la base de données et de la segmenter en deux groupes différents afin d&#39;envoyer un email au premier groupe et un SMS au deuxième.

![](assets/wkf_segment_overview.png)

Pour plus d&#39;informations sur les workflows et les différents canaux disponibles dans Adobe Campaign, consultez les documents suivants :

* [Présentation des workflows](../../automating/using/get-started-workflows.md)
* [Découvrir les canaux de communication](../../channels/using/get-started-communication-channels.md)

## Créer un workflow   {#creating-workflow}

Afin d&#39;envoyer deux diffusions différentes à un groupe donné, vous devez tout d&#39;abord définir votre cible.

Pour ce faire, vous devez créer une requête pour identifier les destinataires, et donc, créer un workflow.

Créez un nouveau workflow dans le programme ou la campagne de votre choix:

1. Dans **[!UICONTROL Marketing Activities]**, cliquez sur **[!UICONTROL Create]** et sélectionnez **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL New Workflow]** comme type de processus et cliquez sur **[!UICONTROL Next]**.
1. Enter the properties of the workflow and click **[!UICONTROL Create]**.

Les étapes détaillées pour créer un workflow sont présentées dans la section [Création d&#39;un workflow](../../automating/using/building-a-workflow.md).

## Créer une activité Requête {#creating-query-activity}

Une fois le workflow créé, vous accédez à son interface.

Insérez une activité Requête dans votre workflow afin de cibler les profils qui recevront vos diffusions.

1. Dans **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, faites glisser et déposez un **[!UICONTROL Query activity]**.
1. Double-cliquez sur l&#39;activité.
1. In the **[!UICONTROL Target]** tab, browse the shortcuts and select one of your [audiences](../../audiences/using/about-audiences.md).
1. Déplacez le raccourci dans la zone d&#39;édition. En fonction du type de raccourci sélectionné, une fenêtre s&#39;affiche.
1. Paramétrez les éléments de ciblage puis validez votre requête.

![](assets/wkf_segment_query.png)

Vous pouvez créer une requête sur un ou plusieurs éléments.

Use the **[!UICONTROL Count]** button to see an estimation of the number of profiles targeted by the query.

Les étapes détaillées pour créer une activité Requête sont présentées dans la section [Requête](../../automating/using/query.md).

## Créer une activité Segmentation {#creating-segmentation-activity}

Une fois votre cible identifiée par l&#39;activité Requête, vous devez sélectionner un critère pour segmenter la cible en deux populations distinctes : l&#39;une recevra un email et l&#39;autre un SMS.

Vous devez utiliser une activité de Segmentation pour créer un ou plusieurs segments à partir d&#39;une population calculée en amont dans une requête.

![](assets/wkf_segment_activity.png)

Le premier groupe **Email** ciblera les destinataires dont l&#39;email est renseigné, mais pas le numéro de téléphone portable. Le second groupe **SMS** contiendra les destinataires dont le numéro de téléphone portable est enregistré dans leur profil.

Pour configurer la première transition (Email) :

1. Dans l’onglet **[!UICONTROL Segments]**, un premier segment est présent par défaut. Modifiez ses propriétés pour le configurer.

   ![](assets/wkf_segment_properties.png)

1. Sélectionnez l’**[!UICONTROL Email]** du profil comme critère de filtrage.

   ![](assets/wkf_segment_email.png)

1. In the new window that appears on the screen, select the **[!UICONTROL Is not empty]** operator.

   ![](assets/wkf_segment_email_not_empty.png)

1. Add a second filtering criterion, **[!UICONTROL Mobile]**, and select the operator **[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Tous les profils provenant de la requête qui auront un email, mais pas de téléphone portable renseigné, seront dans cette transition.

1. Pour plus de clarté dans votre workflow, vous pouvez éditer le libellé de la transition. Validez vos modifications.

   ![](assets/wkf_segment_transition_label.png)

Votre première transition est paramétrée. Pour configurer la seconde transition (SMS) :

1. Cliquez sur le **[!UICONTROL Add an element]** bouton pour ajouter une nouvelle transition.
1. Définissez une condition qui vous permet de récupérer tous les profils dont les numéros de téléphone mobile ont été fournis. To do this, create a rule on the **[!UICONTROL Mobile]** field with the **[!UICONTROL Is not empty]** logical operator.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Tous les profils provenant de la requête qui auront un numéro de téléphone portable renseigné seront dans cette transition.

1. Vous pouvez modifier le libellé de la transition. Validez vos modifications.

Votre seconde transition est maintenant également configurée.

![](assets/wkf_segment_transitions.png)

Les étapes détaillées pour créer une activité Segmentation sont présentées dans la section [Segmentation](../../automating/using/segmentation.md) .

## Créer des diffusions {#creating-deliveries}

As two transitions were already created, you must now add two types of deliveries to the outbound transitions of the Segmentation activity: an **[!UICONTROL Email delivery]** and an **[!UICONTROL SMS delivery]**.

Adobe Campaign vous permet d’ajouter des diffusions à un processus. Pour ce faire, sélectionnez une diffusion dans la **[!UICONTROL Channels]** catégorie de la palette activité de votre flux de travail.

![](assets/wkf_segment_deliveries1.png)

Pour créer une diffusion email :

1. Drag and drop an **[!UICONTROL Email delivery]** after the first segment.
1. Double-cliquez sur l&#39;activité pour l&#39;éditer.
1. Sélectionner **[!UICONTROL Simple email]**.
1. Sélectionnez **[!UICONTROL Add an outbound transition with the population]** puis cliquez sur **[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   La transition sortante vous permettra de récupérer la population et les logs de tracking. Vous pourrez utiliser ceci, par exemple, pour envoyer un deuxième email aux personnes qui n’ont pas cliqué sur le premier.

1. Select an email template and click **[!UICONTROL Next]**.
1. Enter the email properties and click **[!UICONTROL Next]**.
1. Pour créer la mise en page de votre courrier électronique, sélectionnez **[!UICONTROL Use the Email Designer]**.
1. Editez et enregistrez votre contenu.
1. In the **[!UICONTROL Schedule]** section of the message dashboard, unselect the **[!UICONTROL Request confirmation before sending messages}** option.

Les étapes détaillées pour créer une activité Email sont présentées dans la section [Diffusion Email](../../automating/using/email-delivery.md).

Pour créer une diffusion SMS :

1. Drag and drop an **[!UICONTROL SMS delivery]** after the other segment.
1. Double-cliquez sur l&#39;activité pour l&#39;éditer.
1. Sélectionnez **[!UICONTROL SMS]** puis cliquez sur **[!UICONTROL Next]**.
1. Select an SMS template and click **[!UICONTROL Next]**.
1. Enter the SMS properties and click **[!UICONTROL Next]**.
1. Editez et enregistrez votre contenu.

Les étapes détaillées pour créer une activité SMS sont présentées dans la section [Diffusion SMS](../../automating/using/sms-delivery.md).

Une fois vos diffusions créées et éditées, votre workflow est prêt à être démarré.

![](assets/wkf_segment_deliveries.png)

## Exécuter le workflow {#running-the-workflow}

Une fois le workflow démarré, la population ciblée par l’activité Requête sera segmentée afin de recevoir une diffusion par email ou par SMS.

To execute your workflow, click the **[!UICONTROL Start]** button from the action bar.

Vous pouvez accéder à vos diffusions à partir du menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Marketing activities]** avancé via le logo Adobe Campaign. Cliquez sur la diffusion puis sur le **[!UICONTROL Reports]** bouton pour accéder aux [rapports de diffusion](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports), tels que le résumé de la diffusion, le taux d’ouverture ou le rendu du courrier électronique selon la boîte de réception du message du destinataire.