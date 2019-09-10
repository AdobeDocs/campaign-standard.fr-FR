---
title: Diffusion SMS
seo-title: Diffusion SMS
description: Diffusion SMS
seo-description: L'activité Diffusion SMS permet de paramétrer l'envoi d'un SMS unique ou récurrent dans un workflow.
page-status-flag: never-activated
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Diffusion SMS{#sms-delivery}

## Description {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

L'activité **[!UICONTROL Diffusion SMS]** permet de paramétrer l'envoi d’un SMS dans un workflow. Ce SMS peut être **unique** et n'être envoyé qu'une seule fois ou être **récurrent**.

Les SMS uniques sont des SMS standard, envoyés une seule fois.

Les SMS récurrents permettent d'envoyer plusieurs fois sur une période définie un même SMS à des cibles différentes. Vous pouvez agréger les diffusions par période afin d'obtenir des rapports adaptés.

## Contexte d'utilisation {#context-of-use}

L'activité **[!UICONTROL Diffusion SMS]** est généralement utilisée afin d'automatiser l'envoi d'un SMS à une cible calculée dans le même workflow.

Lorsque la diffusion SMS est associée à un planificateur, il est possible de définir des SMS de type récurrent.

Les destinataires du SMS sont définis en amont de l'activité dans le même workflow, grâce à des activités de ciblage telles que requêtes, intersections, etc.

La préparation du message est déclenchée selon les paramètres d'exécution du workflow. Depuis le tableau de bord du message, vous pouvez choisir de demander ou non une confirmation manuelle pour envoyer le message (requise par défaut). Vous pouvez lancer manuellement le workflow ou bien placer une activité de planification afin d'en automatiser l'exécution.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Diffusion SMS]** dans votre workflow.
1. Sélectionnez l'activité puis ouvrez-la à l'aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s'affichent.

   >[!NOTE]
   >
   >Les propriétés générales et les options avancées de l'activité (et non de la diffusion elle-même) sont disponibles à l'aide du bouton ![, disponible dans les actions rapides de l'activité. ](assets/dlv_activity_params-24px.png) Ce bouton est spécifique à l'activité de **[!UICONTROL Diffusion SMS]**. Les propriétés du SMS sont disponibles via la barre d'actions du tableau de bord du SMS.

1. Sélectionnez le mode d'envoi du SMS :

   * **[!UICONTROL SMS]** : le SMS est envoyé une seule fois. Vous pouvez définir à cet endroit si vous souhaitez ou non ajouter une transition en sortie de l'activité. Les différents types de transition sont détaillés à l'étape 7 de cette procédure.
   * **[!UICONTROL SMS récurrent]** : le SMS est envoyé plusieurs fois, à une fréquence définie dans une activité **[!UICONTROL Planificateur]**. Choisissez la période d'agrégation des envois. Cela permet de regrouper tous les envois ayant eu lieu dans la période définie dans une seule vue, aussi appelé **exécution récurrente** et accessible depuis la liste des activités marketing de l'application.

      Par exemple, pour un SMS récurrent d'anniversaire, envoyé chaque jour, vous pouvez choisir d'agréger les envois par mois. Vous pourrez ainsi obtenir des rapports sur votre diffusion mois par mois alors que le SMS est envoyé chaque jour.

1. Sélectionnez un type de SMS. Les types de SMS sont issus des modèles de SMS définis dans **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles]** &gt; **[!UICONTROL Modèles de diffusion]**.
1. Renseignez les propriétés générales du SMS. Vous pouvez également rattacher l'activité à une campagne existante. Le libellé de l'activité de la diffusion dans le workflow est mis à jour avec le libellé du SMS.
1. Définissez le contenu du SMS. Consultez la section concernant la [création d'un SMS](../../channels/using/creating-an-sms-message.md).
1. Par défaut, l'activité de **[!UICONTROL Diffusion SMS]** ne possède aucune transition sortante. Si vous souhaitez ajouter une transition sortante à votre activité de **[!UICONTROL Diffusion Email]**, accédez à l'onglet **[!UICONTROL Général]** des options avancées de l'activité (bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l'activité) puis cochez l'une des options suivantes :

   * **[!UICONTROL Ajouter une transition sortante sans la population]** : permet de générer une transition sortante contenant la même population que la transition entrante.
   * **[!UICONTROL Ajouter une transition sortante avec la population]** : permet de générer une transition sortante contenant la population à qui le SMS a été envoyé. La population ciblée exclue pendant la préparation de la diffusion (quarantaine, numéros non valides, etc.) est exclue de cette transition.

1. Validez le paramétrage de l'activité et enregistrez le workflow.

Lorsque vous ouvrez à nouveau l'activité par la suite, vous accédez au tableau de bord du SMS. Seul son contenu reste modifiable.

Par défaut, le démarrage d'un workflow de diffusion déclenche uniquement la préparation des messages. L'envoi des messages créés depuis un workflow doit toujours être confirmé après le démarrage du workflow. Dans le tableau de bord des messages, vous pouvez toutefois désactiver l'option **[!UICONTROL Demander confirmation avant d'envoyer les messages]** si les messages ont été créés depuis un workflow. Lorsque cette option est décochée, les messages sont envoyés sans autre préavis une fois la préparation terminée.

## Remarques  {#remarks}

Les diffusions créées à partir d'un workflow sont accessibles dans la liste des activités marketing de l'application. Vous pouvez visualiser l'état d'exécution du workflow depuis le tableau de bord. Des liens dans le volet de résumé du SMS vous permettent d'accéder directement aux éléments liés (workflow, campagne, diffusion parente dans le cas d'un SMS récurrent).

Toutefois, les exécutions des diffusions récurrentes sont masquées par défaut. Pour les afficher, cochez l'option **[!UICONTROL Afficher les exécutions récurrentes]** dans le volet de recherche des activités marketing.

Depuis les diffusions parentes, accessibles depuis la liste des activités marketing ou directement via les exécutions récurrentes associées, vous pouvez visualiser l'ensemble des envois ayant été réalisés (en fonction de la période d'agrégation définie lors du paramétrage de l'activité de **[!UICONTROL Diffusion SMS).]** Pour cela, accédez au détail du bloc **[!UICONTROL Déploiement]** de la diffusion parente en sélectionnant ![](assets/wkf_dlv_detail_button.png).

## Exemple {#example}

![](assets/wkf_sms_example_1.png)

Cet exemple représente un workflow d'anniversaire. Un SMS est envoyé chaque jour aux profils dont l'anniversaire a lieu le jour même. Pour cela :

* Le **[!UICONTROL Planificateur]** permet de lancer le workflow chaque jour à 8h00.

   ![](assets/wkf_delivery_example_2.png)

* La **[!UICONTROL Requête]** permet de calculer à chaque exécution du workflow les profils dont c'est l'anniversaire et dont le numéro de mobile est renseignée. Le calcul de l'anniversaire est réalisé grâce à un filtre prédéfini disponible dans la palette de l'outil d'édition de requêtes.

   ![](assets/wkf_delivery_example_3.png)

* Le **[!UICONTROL SMS]** est de type récurrent. Les envois sont agrégés par mois. Ainsi, tous les SMS envoyés dans un mois sont agrégés dans une seule vue. En un an, 365 diffusions sont donc exécutées mais sont regroupées dans 12 vues (aussi appelés **exécutions récurrentes**) dans l'interface d'Adobe Campaign. Le détail des historiques et des rapports est ainsi affiché sur une base mensuelle et non pour chaque envoi.

   ![](assets/wkf_sms_example_4.png)

Pour un autre exemple de livraison SMS dans un flux de travail, voir [Utilisation : Retargeting workflow envoie une nouvelle livraison à des non-initiateurs](../../automating/using/workflow-cross-channel-retargeting.md).
