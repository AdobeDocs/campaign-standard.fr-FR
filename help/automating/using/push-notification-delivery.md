---
title: Diffusion Notification push
description: L'activité Diffusion Notification push permet de paramétrer l'envoi d'une notification push unique ou récurrente dans un workflow.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '814'
ht-degree: 100%

---


# Diffusion Notification push{#push-notification-delivery}

## Description {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

L&#39;activité **[!UICONTROL Notification push]** permet de paramétrer l&#39;envoi d&#39;une notification push dans un workflow. Cette notification peut être unique et n’être envoyée qu’une seule fois ou être récurrente.

* **Les notifications envoyées une seule fois sont des diffusions standard de notification push sur des applications mobiles, envoyées une seule fois.**
* **Les notifications récurrentes permettent d’envoyer plusieurs fois sur une période définie une même notification push à des cibles différentes.** Vous pouvez agréger les diffusions par période afin d’obtenir des rapports adaptés.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Notification push]** est généralement utilisée afin d&#39;automatiser l&#39;envoi d&#39;une notification push à une cible calculée dans le même workflow.

Lorsque l&#39;activité est associée à un planificateur, il est possible de définir des notifications push récurrentes.

Les destinataires sont définis en amont de l&#39;activité dans le même workflow, grâce à des activités de ciblage telles que requêtes, intersections, etc.

La préparation du message est déclenchée selon les paramètres d&#39;exécution du workflow. Depuis le tableau de bord du message, vous pouvez choisir de demander ou non une confirmation manuelle pour envoyer le message (requise par défaut). Vous pouvez lancer manuellement le workflow ou bien placer une activité de planification afin d&#39;en automatiser l&#39;exécution.

**Rubriques connexes :**

* [Envoi d&#39;une notification push récurrente avec un workflow](../../automating/using/recurring-push-notifications.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Notification push]** dans votre workflow.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.

   >[!NOTE]
   >
   >Les propriétés générales et les options avancées de l&#39;activité (et non de la diffusion elle-même) sont disponibles à l&#39;aide du bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité. Ce bouton est spécifique à l&#39;activité **[!UICONTROL Notification push]**. Les propriétés de la notification push sont disponibles via la barre d&#39;actions du tableau de bord de la notification push.

1. Sélectionnez le mode d&#39;envoi de la notification push :

   * **[!UICONTROL Notification unique]** : la notification push est envoyée une seule fois. Vous pouvez définir à cet endroit si vous souhaitez ou non ajouter une transition en sortie de l&#39;activité. Les différents types de transition sont détaillés à l&#39;étape 7 de cette procédure.
   * **[!UICONTROL Notification récurrente]** : la notification push est envoyée plusieurs fois, à une fréquence définie dans une activité **[!UICONTROL Planificateur]**. Choisissez la période d&#39;agrégation des envois. Cela permet de regrouper tous les envois ayant eu lieu dans la période définie dans une seule notification push, aussi appelée **exécution récurrente** et accessible depuis la liste des activités marketing de l&#39;application.

      Par exemple, pour une notification récurrente d&#39;anniversaire, envoyée chaque jour, vous pouvez choisir d&#39;agréger les envois par mois. Vous pourrez ainsi obtenir des rapports sur votre diffusion mois par mois alors que la notification est envoyée chaque jour.

1. Sélectionnez un type de notification. Ces types sont issus des modèles de notifications push définis dans **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]**.
1. Renseignez les propriétés générales de la notification push. Vous pouvez également rattacher l&#39;activité à une campagne existante. Le libellé de l&#39;activité de diffusion dans le workflow est mis à jour avec le libellé de la notification push.
1. Définissez le contenu de la notification push. Voir [Création d&#39;une notification push](../../channels/using/preparing-and-sending-a-push-notification.md).
1. Par défaut, l&#39;activité **[!UICONTROL Notification push]** ne possède aucune transition sortante. Si vous souhaitez ajouter une transition sortante à votre activité **[!UICONTROL Notification push]**, accédez à l&#39;onglet **[!UICONTROL Général]** des options avancées de l&#39;activité (bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité) puis cochez l&#39;une des options suivantes :

   * **[!UICONTROL Ajouter une transition sortante sans la population]** : permet de générer une transition sortante contenant la même population que la transition entrante.
   * **[!UICONTROL Ajouter une transition sortante avec la population]** : permet de générer une transition sortante contenant la population à qui la notification a été envoyée. Les membres de la cible exclus pendant la préparation de la diffusion sont exclus de cette transition.

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

Lorsque vous ouvrez à nouveau l&#39;activité par la suite, vous accédez au tableau de bord de la notification push. Seul son contenu reste modifiable.

Par défaut, le démarrage d&#39;un workflow de diffusion déclenche uniquement la préparation des messages. L&#39;envoi des messages créés depuis un workflow doit toujours être confirmé après le démarrage du workflow. Dans le tableau de bord des messages, vous pouvez toutefois désactiver l&#39;option **[!UICONTROL Demander confirmation avant d&#39;envoyer les messages]** si les messages ont été créés depuis un workflow. Lorsque cette option est décochée, les messages sont envoyés sans autre préavis une fois la préparation terminée.

## Remarques       {#remarks}

Les diffusions créées à partir d&#39;un workflow sont accessibles dans la liste des activités marketing de l&#39;application. Vous pouvez visualiser l&#39;état d&#39;exécution du workflow depuis le tableau de bord. Des liens dans le volet de résumé de la notification push vous permettent d&#39;accéder directement aux éléments liés (workflow, campagne, etc.).

Depuis les diffusions parentes, accessibles depuis la liste des activités marketing, vous pouvez visualiser l&#39;ensemble des envois ayant été réalisés (en fonction de la période d&#39;agrégation définie lors du paramétrage de l&#39;activité **[!UICONTROL Notification push]**). Pour cela, accédez au détail du bloc **[!UICONTROL Déploiement]** de la diffusion parente en sélectionnant![](assets/wkf_dlv_detail_button.png) .
