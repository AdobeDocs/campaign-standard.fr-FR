---
title: Diffusion SMS
description: L'activité Diffusion SMS permet de paramétrer l'envoi d'un SMS unique ou récurrent dans un workflow.
page-status-flag: never-activated
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '828'
ht-degree: 100%

---


# Diffusion SMS{#sms-delivery}

## Description {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

L&#39;activité **[!UICONTROL Diffusion SMS]** permet de paramétrer l&#39;envoi d&#39;un SMS dans un workflow. Ce SMS peut être unique et n’être envoyé qu’une seule fois ou être récurrent.

* **Les SMS uniques sont des SMS standard, envoyés une seule fois.**
* **Les SMS récurrents permettent d’envoyer plusieurs fois sur une période définie un même SMS à des cibles différentes.** Vous pouvez agréger les diffusions par période afin d’obtenir des rapports adaptés.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Diffusion SMS]** est généralement utilisée afin d&#39;automatiser l&#39;envoi d&#39;un SMS à une cible calculée dans le même workflow.

Lorsque la diffusion SMS est associée à un planificateur, il est possible de définir des SMS de type récurrent.

Les destinataires du SMS sont définis en amont de l&#39;activité dans le même workflow, grâce à des activités de ciblage telles que requêtes, intersections, etc.

La préparation du message est déclenchée selon les paramètres d&#39;exécution du workflow. Depuis le tableau de bord du message, vous pouvez choisir de demander ou non une confirmation manuelle pour envoyer le message (requise par défaut). Vous pouvez lancer manuellement le workflow ou bien placer une activité de planification afin d&#39;en automatiser l&#39;exécution.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Diffusion SMS]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.

   >[!NOTE]
   >
   >Les propriétés générales et les options avancées de l&#39;activité (et non de la diffusion elle-même) sont disponibles à l&#39;aide du bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité. Ce bouton est spécifique à l&#39;activité de **[!UICONTROL Diffusion SMS]**. Les propriétés du SMS sont disponibles via la barre d&#39;actions du tableau de bord du SMS.

1. Sélectionnez le mode d&#39;envoi du SMS :

   * **[!UICONTROL SMS]** : le SMS est envoyé une seule fois. Vous pouvez définir à cet endroit si vous souhaitez ou non ajouter une transition en sortie de l&#39;activité. Les différents types de transition sont détaillés à l&#39;étape 7 de cette procédure.
   * **[!UICONTROL SMS récurrent]** : le SMS est envoyé plusieurs fois, à une fréquence définie dans une activité **[!UICONTROL Planificateur]**. Choisissez la période d&#39;agrégation des envois. Cela permet de regrouper tous les envois ayant eu lieu dans la période définie dans une seule vue, aussi appelé **exécution récurrente** et accessible depuis la liste des activités marketing de l&#39;application.

      Par exemple, pour un SMS récurrent d&#39;anniversaire, envoyé chaque jour, vous pouvez choisir d&#39;agréger les envois par mois. Vous pourrez ainsi obtenir des rapports sur votre diffusion mois par mois alors que le SMS est envoyé chaque jour.

1. Sélectionnez un type de SMS. Les types de SMS sont issus des modèles de SMS définis dans **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]**.
1. Renseignez les propriétés générales du SMS. Vous pouvez également rattacher l&#39;activité à une campagne existante. Le libellé de l&#39;activité de la diffusion dans le workflow est mis à jour avec le libellé du SMS.
1. Définissez le contenu du SMS. Consultez la section concernant la [création d&#39;un SMS](../../channels/using/creating-an-sms-message.md).
1. Par défaut, l&#39;activité de **[!UICONTROL Diffusion SMS]** ne possède aucune transition sortante. Si vous souhaitez ajouter une transition sortante à votre activité de **[!UICONTROL Diffusion Email]**, accédez à l&#39;onglet **[!UICONTROL Général]** des options avancées de l&#39;activité (bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité) puis cochez l&#39;une des options suivantes :

   * **[!UICONTROL Ajouter une transition sortante sans la population]** : permet de générer une transition sortante contenant la même population que la transition entrante.
   * **[!UICONTROL Ajouter une transition sortante avec la population]** : permet de générer une transition sortante contenant la population à qui le SMS a été envoyé. La population ciblée exclue pendant la préparation de la diffusion (quarantaine, numéros non valides, etc.) est exclue de cette transition.

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

Lorsque vous ouvrez à nouveau l&#39;activité par la suite, vous accédez au tableau de bord du SMS. Seul son contenu reste modifiable.

Par défaut, le démarrage d&#39;un workflow de diffusion déclenche uniquement la préparation des messages. L&#39;envoi des messages créés depuis un workflow doit toujours être confirmé après le démarrage du workflow. Dans le tableau de bord des messages, vous pouvez toutefois désactiver l&#39;option **[!UICONTROL Demander confirmation avant d&#39;envoyer les messages]** si les messages ont été créés depuis un workflow. Lorsque cette option est décochée, les messages sont envoyés sans autre préavis une fois la préparation terminée.

## Remarques       {#remarks}

Les diffusions créées à partir d&#39;un workflow sont accessibles dans la liste des activités marketing de l&#39;application. Vous pouvez visualiser l&#39;état d&#39;exécution du workflow depuis le tableau de bord. Des liens dans le volet de résumé du SMS vous permettent d&#39;accéder directement aux éléments liés (workflow, campagne, diffusion parente dans le cas d&#39;un SMS récurrent).

Toutefois, les exécutions des diffusions récurrentes sont masquées par défaut. Pour les afficher, cochez l&#39;option **[!UICONTROL Afficher les exécutions récurrentes]** dans le volet de recherche des activités marketing.

Depuis les diffusions parentes, accessibles depuis la liste des activités marketing ou directement via les exécutions récurrentes associées, vous pouvez visualiser l&#39;ensemble des envois ayant été réalisés (en fonction de la période d&#39;agrégation définie lors du paramétrage de l&#39;activité de **[!UICONTROL Diffusion SMS).]** Pour cela, accédez au détail du bloc **[!UICONTROL Déploiement]** de la diffusion parente en sélectionnant![](assets/wkf_dlv_detail_button.png) .
