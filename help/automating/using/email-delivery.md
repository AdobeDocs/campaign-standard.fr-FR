---
solution: Campaign Standard
product: campaign
title: Diffusion Email
description: L'activité Diffusion Email permet de paramétrer l'envoi d'un email unique ou récurrent dans un workflow.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 99%

---


# Diffusion Email{#email-delivery}

## Description {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

L&#39;activité **[!UICONTROL Diffusion Email]** permet de paramétrer l&#39;envoi d&#39;un email dans un workflow. Cet email peut être **unique** et n&#39;être envoyé qu&#39;une seule fois ou être **récurrent**.

Les emails uniques sont des emails standard, envoyés une seule fois.

Les emails récurrents permettent d&#39;envoyer plusieurs fois sur une période définie un même email à des cibles différentes. Vous pouvez agréger les diffusions par période afin d’obtenir des rapports adaptés.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Diffusion Email]** est généralement utilisée afin d&#39;automatiser l&#39;envoi d&#39;un email à une cible calculée dans le même workflow.

Associée à un planificateur, il est possible de définir des emails de type récurrent.

Les destinataires de l&#39;email sont définis en amont de l&#39;activité dans le même workflow, grâce à des activités de ciblage telles que requêtes, intersections, etc.

La préparation du message est déclenchée selon les paramètres d&#39;exécution du workflow. Depuis le tableau de bord du message, vous pouvez choisir de demander ou non une confirmation manuelle pour envoyer le message (requise par défaut). Vous pouvez lancer manuellement le workflow ou bien placer une activité de planification afin d&#39;en automatiser l&#39;exécution.

**Rubriques connexes :**

* [Cas pratique : création d’une diffusion email hebdomadaire](../../automating/using/workflow-weekly-offer.md)
* [Cas pratique : création d’une diffusion segmentée sur la localisation](../../automating/using/workflow-segmentation-location.md)
* [Cas pratique : création de diffusions avec un complément](../../automating/using/workflow-created-query-with-complement.md)
* [Cas pratique : workflow de reciblage envoyant une nouvelle diffusion aux personnes n’ayant pas ouvert l’email](../../automating/using/workflow-cross-channel-retargeting.md)
* [Cas pratique : diffusion d’anniversaire](../../automating/using/birthday-delivery.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Diffusion Email]** dans votre workflow.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.

   >[!NOTE]
   >
   >Les propriétés générales et les options avancées de l&#39;activité (et non de la diffusion elle-même) sont disponibles à l&#39;aide du bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité. Ce bouton est spécifique à l&#39;activité de **[!UICONTROL Diffusion Email]**. Les propriétés de l&#39;email sont disponibles via la barre d&#39;actions du tableau de bord de l&#39;email.

1. Sélectionnez le mode d&#39;envoi de l&#39;email :

   * **[!UICONTROL Email]** : l&#39;email est envoyé une seule fois. Vous pouvez définir à cet endroit si vous souhaitez ou non ajouter une transition en sortie de l&#39;activité. Les différents types de transition sont détaillés à l&#39;étape 7 de cette procédure.
   * **[!UICONTROL Email récurrent]** : l&#39;email est envoyé plusieurs fois, à une fréquence définie dans une activité **[!UICONTROL Planificateur]**. Choisissez la période d&#39;agrégation des envois. Cela permet de regrouper tous les envois ayant eu lieu dans la période définie dans un seul email, aussi appelé **exécution récurrente** et accessible depuis la liste des activités marketing de l&#39;application.

      Par exemple, pour un email récurrent d&#39;anniversaire, envoyé chaque jour, vous pouvez choisir d&#39;agréger les envois par mois. Vous pourrez ainsi obtenir des rapports sur votre diffusion mois par mois alors que l&#39;email est envoyé chaque jour.
   >[!NOTE]
   >
   >Les diffusions récurrentes sont préparées en fonction de la **période d’agrégation**. Par exemple, si la période d’agrégation est &quot;par jour&quot;, la diffusion n’est repréparée qu’une fois par jour. Si vous prévoyez d’appeler ce workflow plusieurs fois par jour, utilisez [!UICONTROL Pas d’agrégation].

1. Choisissez un type d&#39;email. Les types d&#39;emails sont issus des modèles d&#39;emails définis dans **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]**.
1. Renseignez les propriétés générales de l&#39;email. Vous pouvez également rattacher l&#39;activité à une campagne existante. Le libellé de l&#39;activité de la diffusion dans le workflow est mis à jour avec le libellé de l&#39;email.
1. Définissez le contenu de l&#39;email. Consultez la section concernant l&#39;[édition de contenu](../../designing/using/designing-content-in-adobe-campaign.md).
1. Par défaut, l&#39;activité de **[!UICONTROL Diffusion Email]** ne possède aucune transition sortante. Si vous souhaitez ajouter une transition sortante à votre activité de **[!UICONTROL Diffusion Email]**, accédez à l&#39;onglet **[!UICONTROL Général]** des options avancées de l&#39;activité (bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité) puis cochez l&#39;une des options suivantes :

   * **[!UICONTROL Ajouter une transition sortante sans la population]** : permet de générer une transition sortante contenant la même population que la transition entrante.
   * **[!UICONTROL Ajouter une transition sortante avec la population]** : permet de générer une transition sortante contenant la population à qui l&#39;email a été envoyé. La population ciblée exclue pendant la préparation de la diffusion (quarantaine, adresses email non valides, etc.) est exclue de cette transition.

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

Lorsque vous ouvrez à nouveau l&#39;activité par la suite, vous accédez au tableau de bord de l&#39;email. Seul son contenu reste modifiable.

Par défaut, le démarrage d&#39;un workflow de diffusion déclenche uniquement la préparation des messages. L&#39;envoi des messages créés depuis un workflow doit toujours être confirmé après le démarrage du workflow. Dans le tableau de bord des messages, vous pouvez toutefois désactiver l&#39;option **[!UICONTROL Demander confirmation avant d&#39;envoyer les messages]** si les messages ont été créés depuis un workflow. Lorsque cette option est décochée, les messages sont envoyés sans autre préavis une fois la préparation terminée.

## Remarques        {#remarks}

Les diffusions créées à partir d&#39;un workflow sont accessibles dans la liste des activités marketing de l&#39;application. Vous pouvez visualiser l&#39;état d&#39;exécution du workflow depuis le tableau de bord. Des liens dans le volet de résumé de l&#39;email vous permettent d&#39;accéder directement aux éléments liés (workflow, campagne, diffusion parente dans le cas d&#39;un email récurrent).

![](assets/wkf_display_recurrent_executions_2.png)

Toutefois, les exécutions des diffusions récurrentes sont masquées par défaut. Pour les afficher, cochez l&#39;option **[!UICONTROL Afficher les exécutions récurrentes]** dans le volet de recherche des activités marketing.

![](assets/wkf_display_recurrent_executions.png)

Depuis les diffusions parentes, accessibles depuis la liste des activités marketing ou directement via les exécutions récurrentes associées, vous pouvez visualiser l&#39;ensemble des envois ayant été réalisés (en fonction de la période d&#39;agrégation définie lors du paramétrage de l&#39;activité de **[!UICONTROL Diffusion Email]**). Pour cela, accédez au détail du bloc **[!UICONTROL Déploiement]** de la diffusion parente en sélectionnant![](assets/wkf_dlv_detail_button.png) .

![](assets/wkf_display_recurrent_executions_3.png)
