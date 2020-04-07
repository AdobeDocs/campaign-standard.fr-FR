---
title: Recevoir des alertes en cas d'échec
description: Découvrez comment utiliser le système de gestion des alertes.
page-status-flag: never-activated
uuid: a3ab733a-e3db-4adc-b930-cd4064b6dc1c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 0766bd57-c5f1-4f56-ac84-e5a04d3819ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# Recevoir des alertes en cas d&#39;échec{#receiving-alerts-when-failures-happen}

## A propos des alertes de diffusion {#about-delivery-alerting}

La fonctionnalité **Alertes de diffusion** est un système de gestion des alertes qui permet à un groupe d&#39;utilisateurs de recevoir automatiquement des notifications contenant des informations sur l&#39;exécution de leurs diffusions.

Les notifications envoyées comportent un rapport qui repose sur les critères par défaut suivants :

* Diffusions en échec
* Diffusions avec préparation en échec
* Diffusions avec un mauvais taux de soft bounces
* Diffusions avec un mauvais taux de hard bounces
* Diffusions avec un statut &#39;en attente&#39; plus long que d&#39;habitude
* Diffusions avec faible débit
* Diffusions en cours

Les destinataires des alertes peuvent contrôler les diffusions qui sont traitées par Adobe Campaign et prendre les mesures qui s&#39;imposent en cas de problèmes liés à leur exécution.

Ces notifications d&#39;alerte peuvent être personnalisées selon des critères d&#39;alerte spécifiques qui sont définis par le biais d&#39;un tableau de bord dans l&#39;interface d&#39;Adobe Campaign.

>[!NOTE]
>
>Les notifications d&#39;alerte sont diffusées par email uniquement.

Les notifications envoyées contiennent les éléments suivants :

* A **[!UICONTROL Summary]** displaying the number of deliveries meeting the criteria that you defined and the label/color that you chose for each criterion.
* A **[!UICONTROL Details]** section listing all of the delivery criteria defined for the corresponding dashboard and all of the deliveries for each criterion.

![](assets/delivery-alerting_notification.png)

## Tableaux de bord des alertes de diffusion {#delivery-alerting-dashboards}

### A propos des tableaux de bord des alertes de diffusion {#about-delivery-alerting-dashboards}

Pour gérer les destinataires des notifications, définir les critères des alertes et accéder à l&#39;historique des alertes, vous devez utiliser des tableaux de bord.

>[!NOTE]
>
>Pour accéder aux tableaux de bord ainsi qu&#39;aux critères des alertes et les configurer, vous devez disposer de droits d&#39;administration ou figurer dans le groupe de sécurité **Superviseurs de diffusion.** Les utilisateurs standard n&#39;ont pas accès aux tableaux de bord dans l&#39;interface d&#39;Adobe Campaign. Ils peuvent uniquement recevoir les notifications d&#39;alerte. Pour plus d&#39;informations sur les utilisateurs et la sécurité dans Adobe Campaign, voir [Types d&#39;utilisateurs](../../administration/using/users-management.md) et [Groupes de sécurité](../../administration/using/managing-groups-and-users.md#about-security-groups).

Depuis l&#39;interface d&#39;Adobe Campaign, vous pouvez :

* Créer et gérer des tableaux de bord d&#39;alerte de diffusion. Voir [Création d&#39;un tableau de bord des alertes de diffusion](#creating-a-delivery-alerting-dashboard).
* Définir et gérer les critères des alertes de diffusion de chaque tableau de bord. Par exemple, vous pouvez créer des alertes basées sur les diffusions avec préparation en échec ou les diffusions avec faible débit uniquement. Voir [À propos des critères des alertes de diffusion](#about-alerting-criteria).
* Modifier les paramètres des critères pour chaque tableau de bord. Voir [Paramètres des critères](#criteria-parameters).
* Définir un groupe de destinataires pour chaque tableau de bord.

   Vous souhaitez par exemple informer les utilisateurs disposant de droits d&#39;administration des diffusions en échec uniquement. Vous voulez également que les utilisateurs marketing reçoivent des informations sur les diffusions avec mauvais taux de soft bounces. Vous devez donc créer deux tableaux de bord différents et définir les critères souhaités pour chaque groupe de destinataires.

* Accéder à l&#39;historique de toutes les alertes envoyées pour chaque tableau de bord.

   Lorsque vous sélectionnez un tableau de bord, la dernière alerte envoyée associée à celui-ci s&#39;affiche par défaut. Toutes les alertes envoyées sont répertoriées dans la partie gauche de l&#39;écran. Click an item in the **[!UICONTROL History]** list to access the corresponding alerts.

![](assets/delivery-alerting_dashboard.png)

### Création d&#39;un tableau de bord des alertes de diffusion {#creating-a-delivery-alerting-dashboard}

Si vous souhaitez envoyer des notifications selon des critères spécifiques à différents groupes d&#39;utilisateurs, vous devez utiliser plusieurs tableaux de bord. Pour créer un tableau de bord :

1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Sélectionnez **[!UICONTROL Delivery alerting dashboards]** puis cliquez sur **[!UICONTROL Create]**.
1. Check the **[!UICONTROL Enabled]** box to activate the current dashboard.

   Si cette option est désactivée, les notifications associées à ce tableau de bord ne sont plus envoyées. Par défaut, cette option est désactivée.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Select the group of recipients that you want to notify from the **[!UICONTROL Alert group]** drop-down list. Pour créer ou modifier un groupe, consultez la section [Créer un groupe de sécurité et affecter des utilisateurs](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. Dans la **[!UICONTROL Delivery alerting criteria]** section, cliquez sur **[!UICONTROL Create element]** pour ajouter des critères. Voir [À propos des critères des alertes de diffusion](#about-alerting-criteria).
1. Select the **[!UICONTROL Edit properties]** button. In the **[!UICONTROL Criteria parameters]** tab, define how the criteria will be applied. Voir [Paramètres des critères](#criteria-parameters).
1. Click **[!UICONTROL Create]** to save the dashboard.

Désormais, dès qu&#39;une diffusion répond aux critères définis dans ce tableau de bord, une notification d&#39;alerte est envoyée aux groupes d&#39;utilisateurs indiqués.

## Critères des alertes de diffusion  {#delivery-alerting-criteria}

### A propos des critères des alertes de diffusion {#about-alerting-criteria}

Pour accéder aux critères d’alerte , accédez à **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** et sélectionnez **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Les critères suivants peuvent être utilisés dans les tableaux de bord des alertes de diffusion :

* **[!UICONTROL Deliveries failed]**: Tout planifié dans une plage définie, avec un état erroné.
* **[!UICONTROL Deliveries with preparation failed]**: Tout  modifié dans une plage définie, pour lequel l’étape de préparation (calcul de l’et génération de contenu) a échoué. Voir à ce propos la section [Préparer l&#39;envoi](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Tout planifié dans une plage définie, avec un état au moins **[!UICONTROL In progress]**, avec un taux d’erreur de rebonds modéré supérieur à un pourcentage défini.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Tout planifié dans une plage définie, avec un état au moins **[!UICONTROL In progress]**, avec un taux d’erreur de rebond dur supérieur à un pourcentage défini.
* **[!UICONTROL Deliveries with long start pending]**: Tout planifié dans une plage définie, avec un **[!UICONTROL Start pending]** état plus long qu&#39;une durée définie, **[!UICONTROL Start pending]** état signifiant que les messages n&#39;ont pas encore été pris en compte par le système.
* **[!UICONTROL Deliveries with low throughput]**: Tout a démarré pendant plus d’une durée définie, avec moins d’un pourcentage défini de messages traités, avec un débit inférieur à une valeur définie.
* **[!UICONTROL Deliveries in progress]**: Tout planifié dans une plage définie, avec l’ **[!UICONTROL In progress]** état.

>[!NOTE]
>
>Tous les paramètres s&#39;appliquant aux critères ci-dessus possèdent des valeurs par défaut. These values can be changed in the **[!UICONTROL Criteria parameters]** tab of the delivery alerting dashboards. Voir [Paramètres des critères](#criteria-parameters).

You can select any item from the **[!UICONTROL Delivery alerting criteria]** list to access its details.

![](assets/delivery-alerting_criteria_definition.png)

Pour chaque critère, vous pouvez définir les paramètres suivants :

* **[!UICONTROL Indicators to add in alerts]**, c’est-à-dire les colonnes qui apparaîtront dans la **[!UICONTROL Details]** section de la notification pour le  correspondant au critère sélectionné.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, c’est-à-dire l’étiquette et la couleur qui s’afficheront en regard du critère  du dans le résumé de la notification.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Si un critère est satisfait pour un , il est répété dans chaque notification envoyée au cours de la période de surveillance. Sinon, une seule alerte est envoyée par jour (à la première occurrence) par critère d&#39;alerte pour une diffusion.

   Cette option est définie par défaut sur une fois par jour pour tous les critères.

**Rubriques connexes :**

* [Envois](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Fréquence des alertes](#alerting-frequency)
* [Icônes et statuts des activités marketing ](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Créer un critère d&#39;alerte de diffusion  {#creating-a-delivery-alerting-criterion}

Vous pouvez créer des critères d&#39;alerte de diffusion en fonction de vos besoins.

For example, you can create a new criterion enabling to send a notification listing all deliveries with a **[!UICONTROL Finished]** status.

To do this, you first need to extend the **Delivery** resource and add a new filter allowing you to select only the deliveries with a **[!UICONTROL Finished]** status.

1. Go to **Adobe Campaign** > **Administration** > **Development** > **Custom resources** and click **[!UICONTROL Create]**.
1. Sélectionnez **[!UICONTROL Extend an existing resource]**, sélectionnez la **[!UICONTROL Delivery]** ressource dans le  déroulant et cliquez **[!UICONTROL Create]** pour la modifier.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Pour plus d&#39;informations sur l&#39;extension d&#39;une ressource existante, voir [Définir la ressource](../../developing/using/creating-or-extending-the-resource.md).

1. Dans la **[!UICONTROL Delivery]** ressource, accédez à l’ **[!UICONTROL Filter definition]** onglet et cliquez **[!UICONTROL Add an element]** pour créer un filtre.

   ![](assets/delivery-alerting_new-filter.png)

1. Edit the new filter definition: in the **[!UICONTROL Filter definition]** window, drag and drop the **[!UICONTROL Status]** item into the workspace and select **[!UICONTROL Finished]** as the filter condition.

   ![](assets/delivery-alerting_filter-status.png)

   Pour plus d&#39;informations sur la création et l&#39;édition des filtres personnalisés, voir [Définir des filtres](../../developing/using/configuring-filter-definition.md).

1. Enregistrez vos modifications et publiez vos ressources. Voir à ce propos la section [Publier une ressource personnalisée](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   Le filtre est créé. Il peut maintenant être sélectionné dans un nouveau critère d&#39;alerte de diffusion.

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, sélectionnez **[!UICONTROL Delivery alerting criteria]** et cliquez sur **[!UICONTROL Create]**.
1. Dans le  **[!UICONTROL Delivery filter applied by this criterion]** déroulant, sélectionnez le filtre que vous venez de créer.

   ![](assets/delivery-alerting_cus-filter.png)

   Vous pouvez définir les paramètres du critère de la même manière que pour les critères par défaut. Voir [À propos des critères des alertes de diffusion](#about-alerting-criteria).

Une fois créés, ces critères peuvent être ajoutés, ainsi que d&#39;autres critères, à un tableau de bord des alertes de diffusion. Voir [À propos des tableaux de bord des alertes de diffusion](#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Rubrique connexe :**

[Ajouter ou étendre une ressource](../../developing/using/key-steps-to-add-a-resource.md)

## Paramètres des alertes de diffusion  {#delivery-alerting-parameters}

### Paramètres des critères {#criteria-parameters}

In the **[!UICONTROL Criteria parameters]** tab of a [delivery alerting dashboard](#creating-a-delivery-alerting-dashboard), you can define the settings that apply to the criteria selected in this dashboard.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Par exemple, si vous entrez 100 dans ce champ, une notification est envoyée uniquement pour les  avec un  égal ou supérieur à 100. Ce paramètre s&#39;applique à tous les critères.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Nombre d&#39;heures avant et après l&#39;heure actuelle. Seules les diffusions dont la date de contact est comprise dans cette plage sont prises en compte. Ce paramètre s&#39;applique à tous les critères. Par défaut, la valeur de ce champ est définie sur 24 heures.

   Pour plus d&#39;informations sur la date de contact, voir [Planning](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Une notification est envoyée pour tous les  de avec un taux d’erreur de rebond souple supérieur à la valeur spécifiée. Par défaut, la valeur de ce champ est définie sur 0,05 (5 %).

   Pour plus d&#39;informations sur les soft bounces, voir [À propos de la qualification des emails bounce](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) et [Liste des types de diffusions en échec](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Une notification est envoyée pour tous les  avec un taux d’erreur de rebond dur supérieur à la valeur spécifiée. Par défaut, la valeur de ce champ est définie sur 0,05 (5 %).

   Pour plus d&#39;informations sur les hard bounces, voir [À propos de la qualification des emails bounce](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) et [Liste des types de diffusions en échec](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Une notification est envoyée pour tous les  avec un **[!UICONTROL Start pending]** état plus long que la durée spécifiée dans ce champ, **[!UICONTROL Start pending]** état signifiant que les messages n&#39;ont pas encore été pris en compte par le système.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Seuls les  démarrés (avec **[!UICONTROL In progress]** statut) pendant plus de la durée spécifiée sont pris en compte pour le **[!UICONTROL Deliveries with low throughput]** critère.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Seuls les  dont le pourcentage de messages traités est inférieur au pourcentage spécifié sont pris en compte pour le **[!UICONTROL Deliveries with low throughput]** critère.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Seuls les  dont le débit est inférieur à la valeur spécifiée sont pris en compte pour le **[!UICONTROL Deliveries with low throughput]** critère.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Seuls les dont le pourcentage de messages traités est supérieur au pourcentage spécifié sont pris en compte.

### Fréquence des alertes {#alerting-frequency}

L’ **[!UICONTROL Frequency of delivery alerting]** option permet de définir le délai entre deux envois d’alerte. Par défaut, elle est définie sur 10 minutes.

Vous pouvez modifier ce paramètre dans le menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

>[!NOTE]
>
>Cette option s&#39;applique à tous les tableaux de bord définis dans Adobe Campaign. Vous ne pouvez pas définir une fréquence spécifique pour chaque tableau de bord.

## Motifs des alertes de diffusion  {#delivery-alerting-reasons}

La fonctionnalité **Alertes de diffusion** maintient automatiquement informés tous les utilisateurs actifs d&#39;Adobe Campaign en ce qui concerne le statut d&#39;exécution des diffusions, par email ou par le biais d&#39;un tableau de bord.

Lorsque vous recevez une notification d&#39;alerte de diffusion, voici ce que vous pouvez faire.

Tout d&#39;abord, consultez l&#39;onglet **Log** de la diffusion pour afficher toutes les informations relatives à la diffusion et aux BAT. Les icônes rouge et jaune permettent de repérer les erreurs ou avertissements. L&#39;icône rouge indique une erreur critique qui empêche le démarrage de la diffusion.

To view the history of every occurrence of a delivery, select the **[!UICONTROL Sending logs]** tab. Il contient la liste des messages envoyés et leur statut. There you can check the delivery status for each recipient ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). Pour plus d&#39;informations à ce sujet, voir [Envois](../../sending/using/monitoring-a-delivery.md#sending-logs).

Vous trouverez ci-dessous quelques raisons possibles de la réception de notifications d&#39;alerte lorsque les critères d&#39;une diffusion sont respectés.

* **[!UICONTROL Deliveries failed]**: Ce critère vous informe de tous les ayant un statut erroné. Les raisons peuvent être les suivantes :

   * un problème lié au serveur de diffusion (MTA, Message Transfer Agent) ;
   * une connexion arrivée à expiration entre le serveur de diffusion Adobe Campaign et le serveur de réception ;
   * un problème de délivrabilité ;
   * un workflow en erreur.
   Si la diffusion est déclenchée à l&#39;aide d&#39;un workflow, vérifiez que ce dernier a correctement démarré. Voir à ce propos la section [Exécuter un workflow](../../automating/using/executing-a-workflow.md). Sinon, contactez votre administrateur Adobe Campaign pour résoudre ce problème.

* **[!UICONTROL Deliveries with preparation failed]**: Une erreur peut se produire lors de la préparation des  de dans les cas suivants :

   * Il manque un objet dans la diffusion.
   * Les champs de personnalisation contiennent une syntaxe incorrecte.
   * La cible est absente.
   * La diffusion dépasse la taille limite.
   Voir à ce propos la section [Préparer l&#39;envoi](../../sending/using/preparing-the-send.md). Ces erreurs sont toutefois généralement détectées lors de l&#39;analyse des messages. Voir [Règles de contrôle](../../sending/using/control-rules.md).

* Les causes possibles d’une **[!UICONTROL Delivery with bad error ratio for soft bounces]** alerte peuvent être les suivantes :

   * Le serveur du destinataire est en panne.
   * La boîte de messagerie du destinataire est pleine.
   Pour plus d’informations, consultez les **[!UICONTROL Exclusion logs]** onglets et les **[!UICONTROL Exclusion causes]** onglets du. Voir [Exclus](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   Les causes possibles d’une **[!UICONTROL Delivery with bad error ratio for hard bounces]** alerte peuvent être les suivantes :

   * Le destinataire est blacklisté, ce qui signifie qu&#39;il ne souhaite plus être contacté.
   * L&#39;adresse email du destinataire n&#39;existe pas.
   * Le domaine du destinataire n&#39;existe pas.
   * Le serveur du destinataire bloque la diffusion.
   Pour éviter les soft et hard bounces, suivez les bonnes pratiques suivantes :

   * Créez des règles de typologie de type Filtrage pour exclure une partie de la cible des messages (comme les destinataires en quarantaine) pendant l&#39;analyse de la diffusion. Voir [Créer une règle de filtrage](../../sending/using/filtering-rules.md).
   * Mettez régulièrement à jour votre base client pour conserver de bons processus de gestion des quarantaines. Voir [A propos des quarantaines](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * D&#39;une manière générale, améliorez autant que possible la délivrabilité. Consultez la documentation détaillé d&#39;Adobe Campaign relative à la [délivrabilité](../../sending/using/about-deliverability.md) et contactez votre administrateur Adobe Campaign pour obtenir de l&#39;aide.



* **[!UICONTROL Deliveries with long start pending]**: En général, cela signifie qu’il y a un problème au niveau de l’agent de transfert de message (MTA). Le processus d&#39;exécution attend la disponibilité de certaines ressources. Le MTA n&#39;a peut-être pas été démarré.

   **[!UICONTROL Deliveries with low throughput]**: Encore une fois, il s&#39;agit d&#39;un problème de délivrabilité, ce qui signifie que la MTA est trop lente.

   Pour plus d&#39;informations sur ces problèmes, contactez votre administrateur Adobe Campaign.

**Rubriques connexes :**

* [Comprendre les diffusions en échec](../../sending/using/understanding-delivery-failures.md)
* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)
* [Gestion du blacklistage dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

