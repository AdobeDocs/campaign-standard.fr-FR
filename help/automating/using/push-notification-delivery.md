---
title: Diffusion Notification push
seo-title: Diffusion Notification push
description: Diffusion Notification push
seo-description: L'activité Diffusion Notification push permet de paramétrer l'envoi d'une notification push unique ou récurrente dans un workflow.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: ht
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Diffusion Notification push{#push-notification-delivery}

## Description {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

L'activité **[!UICONTROL Notification push]** permet de paramétrer l'envoi d'une notification push dans un workflow. Cette notification peut être **unique** et n'être envoyée qu'une seule fois ou être **récurrente**.

Les notifications envoyées une seule fois sont des diffusions standard de notification push sur des applications mobiles, envoyées une seule fois.

Les notifications récurrentes permettent d'envoyer plusieurs fois sur une période définie une même notification push à des cibles différentes. Vous pouvez agréger les diffusions par période afin d'obtenir des rapports adaptés.

## Contexte d'utilisation  {#context-of-use}

L'activité **[!UICONTROL Notification push]** est généralement utilisée afin d'automatiser l'envoi d'une notification push à une cible calculée dans le même workflow.

Lorsque l'activité est associée à un planificateur, il est possible de définir des notifications push récurrentes.

Les destinataires sont définis en amont de l'activité dans le même workflow, grâce à des activités de ciblage telles que requêtes, intersections, etc.

La préparation du message est déclenchée selon les paramètres d'exécution du workflow. Depuis le tableau de bord du message, vous pouvez choisir de demander ou non une confirmation manuelle pour envoyer le message (requise par défaut). Vous pouvez lancer manuellement le workflow ou bien placer une activité de planification afin d'en automatiser l'exécution.

## Configuration  {#configuration}

1. Placez une activité **[!UICONTROL Notification push]** dans votre workflow.
1. Sélectionnez l'activité puis ouvrez-la à l'aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s'affichent.

   >[!NOTE]
   >
   >Les propriétés générales et les options avancées de l'activité (et non de la diffusion elle-même) sont disponibles à l'aide du bouton ![, disponible dans les actions rapides de l'activité. ](assets/dlv_activity_params-24px.png) Ce bouton est spécifique à l'activité **[!UICONTROL Notification push]**. Les propriétés de la notification push sont disponibles via la barre d'actions du tableau de bord de la notification push.

1. Sélectionnez le mode d'envoi de la notification push :

   * **[!UICONTROL Notification unique]** : la notification push est envoyée une seule fois. Vous pouvez définir à cet endroit si vous souhaitez ou non ajouter une transition en sortie de l'activité. Les différents types de transition sont détaillés à l'étape 7 de cette procédure.
   * **[!UICONTROL Notification récurrente]** : la notification push est envoyée plusieurs fois, à une fréquence définie dans une activité **[!UICONTROL Planificateur.]** Choisissez la période d'agrégation des envois. Cela permet de regrouper tous les envois ayant eu lieu dans la période définie dans une seule notification push, aussi appelée **exécution récurrente** et accessible depuis la liste des activités marketing de l'application.

      Par exemple, pour une notification récurrente d'anniversaire, envoyée chaque jour, vous pouvez choisir d'agréger les envois par mois. Vous pourrez ainsi obtenir des rapports sur votre diffusion mois par mois alors que la notification est envoyée chaque jour.

1. Sélectionnez un type de notification. Ces types sont issus des modèles de notifications push définis dans **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles]** &gt; **[!UICONTROL Modèles de diffusion]**.
1. Renseignez les propriétés générales de la notification push. Vous pouvez également rattacher l'activité à une campagne existante. Le libellé de l'activité de diffusion dans le workflow est mis à jour avec le libellé de la notification push.
1. Définissez le contenu de la notification push. Voir [Création d'une notification push](../../channels/using/preparing-and-sending-a-push-notification.md).
1. Par défaut, l'activité **[!UICONTROL Notification push]** ne possède aucune transition sortante. Si vous souhaitez ajouter une transition sortante à votre activité **[!UICONTROL Notification push]**, accédez à l'onglet **[!UICONTROL Général]** des options avancées de l'activité (bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l'activité) puis cochez l'une des options suivantes :

   * **[!UICONTROL Ajouter une transition sortante sans la population]** : permet de générer une transition sortante contenant la même population que la transition entrante.
   * **[!UICONTROL Ajouter une transition sortante avec la population]** : permet de générer une transition sortante contenant la population à qui la notification a été envoyée. Les membres de la cible exclus pendant la préparation de la diffusion sont exclus de cette transition.

1. Validez le paramétrage de l'activité et enregistrez le workflow.

Lorsque vous ouvrez à nouveau l'activité par la suite, vous accédez au tableau de bord de la notification push. Seul son contenu reste modifiable.

Par défaut, le démarrage d'un workflow de diffusion déclenche uniquement la préparation des messages. L'envoi des messages créés depuis un workflow doit toujours être confirmé après le démarrage du workflow. Dans le tableau de bord des messages, vous pouvez toutefois désactiver l'option **[!UICONTROL Demander confirmation avant d'envoyer les messages]** si les messages ont été créés depuis un workflow. Lorsque cette option est décochée, les messages sont envoyés sans autre préavis une fois la préparation terminée.

## Remarques  {#remarks}

Les diffusions créées à partir d'un workflow sont accessibles dans la liste des activités marketing de l'application. Vous pouvez visualiser l'état d'exécution du workflow depuis le tableau de bord. Des liens dans le volet de résumé de la notification push vous permettent d'accéder directement aux éléments liés (workflow, campagne, etc.).

Depuis les diffusions parentes, accessibles depuis la liste des activités marketing, vous pouvez visualiser l'ensemble des envois ayant été réalisés (en fonction de la période d'agrégation définie lors du paramétrage de l'activité **[!UICONTROL Notification push]**.) Pour cela, accédez au détail du bloc **[!UICONTROL Déploiement]** de la diffusion parente en sélectionnant ![](assets/wkf_dlv_detail_button.png).

## Envoi d'une notification push récurrente avec un workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Dans cet exemple, une notification push personnalisée est envoyée chaque premier jour du mois, à 8h, aux abonnés de votre application mobile selon leur fuseau horaire. Pour cela :

1. L'activité **[!UICONTROL Planificateur]** permet de démarrer le workflow plusieurs jours avant le début de la diffusion afin d'envoyer à chaque abonné la notification à 8h, dans tous les fuseaux horaires spécifiés :

   * Dans le champ **[!UICONTROL Fréquence d'exécution]**, sélectionnez Mensuelle.
   * Dans le champ **[!UICONTROL Heure]**, sélectionnez 8h.
   * Sélectionnez le jour auquel la diffusion sera envoyée chaque mois.
   * Sélectionnez la date de début du workflow. Celle-ci doit être au moins un jour avant le début de la diffusion. Sinon, certains destinataires pourront recevoir le message un jour après si l'heure sélectionnée est déjà passée dans leur fuseau horaire.
   * Dans l'onglet **[!UICONTROL Options d'exécution]**, sélectionnez le fuseau horaire dans lequel démarrera le workflow dans le champ **[!UICONTROL Fuseau horaire]**. Dans cet exemple, le workflow démarrera à 8h, heure du Pacifique, une semaine avant le premier jour du mois, afin que les diffusions puissent être créées pour tous les fuseaux horaires applicables.
   ![](assets/wkf_push_example_5.png)

1. L'activité **Requête** permet de cibler les clients VIP, âgés entre 20 et 30 ans, abonnés à votre application mobile et n'ayant pas ouvert l'email que vous avez envoyé :

   * Sélectionnez une audience (vos clients VIP) et appliquez un filtrage sur l'âge.
   * Placez l'élément **Abonnements à une application** dans l'espace de travail. Choisissez **Existe** et sélectionnez l'application mobile à utiliser.
   * Sélectionnez l'email que vous avez envoyé à vos clients.
   * Placez l'élément **Logs de diffusion (logs)** dans l'espace de travail, puis sélectionnez **Existe** pour cibler tous les clients qui ont reçu l'email.
   * Placez l'élément **Tracking (tracking)** dans l'espace de travail, puis sélectionnez **N'existe pas** pour cibler tous les clients qui n'ont pas ouvert l'email.

      ![](assets/wkf_push_example_2.png)

1. L'activité **Notification push** vous permet de saisir le contenu de votre message et de sélectionner les champs de personnalisation que vous souhaitez utiliser.

   * Sélectionnez l'option **[!UICONTROL Notification récurrente]**.
   * Définissez le contenu de la notification push. Pour plus d'informations sur le contenu d'une notification push, consultez cette [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * Dans le bloc **[!UICONTROL Planning]**, sélectionnez **[!UICONTROL Messages à envoyer automatiquement dans le fuseau horaire défini ci-dessous]**. Dans le cas présent, Pacifique a été sélectionné pour le **[!UICONTROL Fuseau horaire de la date de contact]**, comme dans l'activité **[!UICONTROL Planificateur]** du workflow.
   * Dans le champ **[!UICONTROL Optimiser le délai d'envoi par destinataire]**, sélectionnez **[!UICONTROL Envoyer au fuseau horaire du destinataire]**.

      ![](assets/wkf_push_example_4.png)

1. Cliquez sur le bouton **[!UICONTROL Démarrer]** pour démarrer le workflow récurrent.

   ![](assets/wkf_push_example_3.png)

Votre workflow est maintenant en cours d'exécution. Il commencera à la date de début sélectionnée pour le **[!UICONTROL Planificateur]** : 8h, heure du Pacifique. La notification push récurrente sera alors envoyée tous les premiers jours du mois, à 8h, selon le fuseau horaire des clients.
