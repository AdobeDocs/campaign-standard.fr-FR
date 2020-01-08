---
title: '"Cas d''utilisation du processus : Diffusion cross-canal"'
description: '"Cas d''utilisation du processus : Diffusion cross-canal"'
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
source-git-commit: f959441647d1fea41ecce2fc41e3cad3cb536bac

---


# Workflow use-case: Creating a cross-channel delivery{#cross-channel-delivery}

Ce document vous permet de découvrir la fonctionnalité d&#39;Adobe Campaign suivante via un cas pratique standard : création d&#39;un workflow de diffusion cross-canal.

Dans ce cas pratique, l&#39;objectif est de sélectionner une audience parmi les destinataires de la base de données et de la segmenter en deux groupes différents afin d&#39;envoyer un email au premier groupe et un SMS au deuxième.

![](assets/wkf_segment_overview.png)

Pour plus d&#39;informations sur les workflows et les différents canaux disponibles dans Adobe Campaign, consultez les documents suivants :

* [Présentation des workflows](../../automating/using/discovering-workflows.md)
* [Découvrir les canaux de communication](../../channels/using/discovering-communication-channels.md)

## Créer un workflow  {#creating-workflow}

Afin d&#39;envoyer deux diffusions différentes à un groupe donné, vous devez tout d&#39;abord définir votre cible.

Pour ce faire, vous devez créer une requête pour identifier les destinataires, et donc, créer un workflow.

Créez un nouveau workflow dans le programme ou la campagne de votre choix:

1. Dans **[!UICONTROL Activités marketing]**, cliquez sur**[!UICONTROL  Créer]** et sélectionnez **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]**en tant que type de workflow et cliquez sur**[!UICONTROL  Suivant]**.
1. Saisissez les propriétés du workflow, puis cliquez sur **[!UICONTROL Créer]**.

Les étapes détaillées pour créer un workflow sont présentées dans la section [Création d&#39;un workflow](../../automating/using/building-a-workflow.md).

## Créer une activité Requête {#creating-query-activity}

Une fois le workflow créé, vous accédez à son interface.

Insérez une activité de requête dans votre processus pour cibler les profils qui recevront vos livraisons.

1. In **[!UICONTROL Activities]**>**[!UICONTROL  Targeting]**, drag and drop a **[!UICONTROL Query activity]**.
1. Double-cliquez sur l&#39;activité.
1. Dans l’onglet **[!UICONTROL Target]**, parcourez les raccourcis et sélectionnez l’une de vos[audiences](../../audiences/using/about-audiences.md).
1. Déplacez le raccourci dans la zone d&#39;édition. En fonction du type de raccourci sélectionné, une fenêtre s&#39;affiche.
1. Paramétrez les éléments de ciblage puis validez votre requête.

![](assets/wkf_segment_query.png)

Vous pouvez créer une requête sur un ou plusieurs éléments.

Utilisez le bouton **[!UICONTROL Comptage]**pour avoir une estimation du nombre de profils ciblés par la requête.

Les étapes détaillées pour créer une activité Requête sont présentées dans la section [Requête](../../automating/using/query.md).

## Créer une activité Segmentation {#creating-segmentation-activity}

Une fois votre cible identifiée par l&#39;activité Requête, vous devez sélectionner un critère pour segmenter la cible en deux populations distinctes : l&#39;une recevra un email et l&#39;autre un SMS.

Vous devez utiliser une activité de Segmentation pour créer un ou plusieurs segments à partir d&#39;une population calculée en amont dans une requête.

![](assets/wkf_segment_activity.png)

Le premier groupe **Email** ciblera les destinataires dont l&#39;email est renseigné, mais pas le numéro de téléphone portable. Le second groupe **SMS** contiendra les destinataires dont le numéro de téléphone portable est enregistré dans leur profil.

Pour configurer la première transition (courriel) :

1. Dans l’onglet **[!UICONTROL Segments]**, un premier segment est présent par défaut. Modifiez ses propriétés pour configurer ce segment.

   ![](assets/wkf_segment_properties.png)

1. Sélectionnez le **[!UICONTROL courriel]**du profil comme critère de filtrage.

   ![](assets/wkf_segment_email.png)

1. Dans la nouvelle fenêtre qui s’affiche à l’écran, sélectionnez l’opérateur **[!UICONTROL N’est pas vide]**.

   ![](assets/wkf_segment_email_not_empty.png)

1. Add a second filtering criterion, **[!UICONTROL Mobile]**, and select the operator**[!UICONTROL  Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Tous les profils provenant de la requête pour lesquels un courrier électronique n’est pas défini, mais aucun numéro de téléphone mobile, seront dans cette transition.

1. Pour plus de clarté dans votre workflow, vous pouvez éditer le libellé de la transition. Validez vos modifications.

   ![](assets/wkf_segment_transition_label.png)

Votre première transition est paramétrée. Pour configurer la seconde transition (SMS) :

1. Cliquez sur le bouton **[!UICONTROL Ajouter un élément]**pour ajouter une nouvelle transition.
1. Définissez une condition qui vous permet de récupérer tous les profils dont les numéros de téléphone mobile ont été fournis. Pour ce faire, créez une règle sur le champ **[!UICONTROL Mobile]**avec l’opérateur logique**[!UICONTROL  N’est pas vide]** .

   ![](assets/wkf_segment_mobile_not_empty.png)

   Tous les profils provenant de la requête pour lesquels un numéro de téléphone mobile est défini seront dans cette transition.

1. Vous pouvez modifier le libellé de la transition. Validez vos modifications.

Votre deuxième transition est maintenant également configurée.

![](assets/wkf_segment_transitions.png)

Les étapes détaillées pour créer une activité Segmentation sont présentées dans la section [Segmentation](../../automating/using/segmentation.md) .

## Créer des diffusions {#creating-deliveries}

As two transitions were already created, you must now add two types of deliveries to the outbound transitions of the Segmentation activity: an **[!UICONTROL Email delivery]**and an**[!UICONTROL  SMS delivery]**.

Adobe Campaign vous permet d&#39;ajouter des diffusions dans un workflow. Pour ce faire, sélectionnez une diffusion depuis la catégorie **[!UICONTROL Canaux]**de la palette d&#39;activités de votre workflow.

![](assets/wkf_segment_deliveries1.png)

Pour créer une diffusion par courrier électronique :

1. Drag and drop an **[!UICONTROL Email delivery]**after the first segment.
1. Double-cliquez sur l&#39;activité   pour l&#39;éditer.
1. Sélectionnez Courriel ****simple.
1. Select **[!UICONTROL Add an outbound transition with the population]**and click**[!UICONTROL  Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   La transition sortante vous permettra de récupérer la population et les journaux de suivi. Vous pourrez utiliser ce service, par exemple, pour envoyer un deuxième courrier aux personnes qui n’ont pas cliqué sur le premier courrier.

1. Sélectionnez un modèle d&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés de l&#39;email et cliquez sur **[!UICONTROL Suivant]**.
1. To create the layout of your email, select **[!UICONTROL Use the Email Designer]**.
1. Editez et enregistrez votre contenu.
1. Dans la section **[!UICONTROL Planning]**du tableau de bord des messages, désélectionnez l&#39;option**[!UICONTROL Demander confirmation avant d&#39;envoyer les messages}**.

Les étapes détaillées pour créer une activité Email sont présentées dans la section [Diffusion Email](../../automating/using/email-delivery.md).

Pour créer une diffusion SMS :

1. Drag and drop an **[!UICONTROL SMS delivery]**after the other segment.
1. Double-cliquez sur l&#39;activité   pour l&#39;éditer.
1. Select **[!UICONTROL SMS]**and click**[!UICONTROL  Next]**.
1. Select an SMS template and click **[!UICONTROL Next]**.
1. Enter the SMS properties and click **[!UICONTROL Next]**.
1. Editez et enregistrez votre contenu.

The detailed steps to build an SMS activity are presented in the [SMS delivery](../../automating/using/sms-delivery.md) section.

Une fois vos diffusions créées et éditées, votre workflow est prêt à être démarré.

![](assets/wkf_segment_deliveries.png)

## Exécuter le workflow {#running-the-workflow}

Une fois le flux de travail démarré, la population ciblée par l’activité Requête sera segmentée afin de recevoir une diffusion par courriel ou par SMS.

To execute your workflow, click the **[!UICONTROL Start]**button from the action bar.

You can access your deliveries from the **[!UICONTROL Marketing plans]**>**[!UICONTROL  Marketing activities]** advanced menu via the Adobe Campaign logo. Click the delivery then the **[!UICONTROL Reports]**button to access the[delivery reports](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports), such as the delivery summary, the open rate or the email rendering according to the recipients&#39; message inbox.