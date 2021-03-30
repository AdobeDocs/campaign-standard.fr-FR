---
solution: Campaign Standard
product: campaign
title: Gérer les SMS entrants
description: Découvrez comment gérer les SMS STOP et stocker les SMS entrants dans Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: Professionnel
level: Intermédiaire
translation-type: ht
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: ht
source-wordcount: '690'
ht-degree: 100%

---


# Gérer les SMS entrants{#managing-incoming-sms}

## Gérer les SMS STOP {#managing-stop-sms}

Lorsqu&#39;un profil répond à un SMS envoyé par le biais de Campaign, vous pouvez configurer les messages qui lui sont automatiquement renvoyés, ainsi que l&#39;action à exécuter.

Cette configuration est définie dans la section **[!UICONTROL Réponse automatique aux MO]** du [compte externe de routage des SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO est l&#39;acronyme de « Mobile Originated », ce qui signifie que vous pouvez configurer une réponse automatique au téléphone mobile qui a envoyé le SMS.

Pour ce faire :

1. Dans le menu avancé, via le logo Adobe Campaign, sélectionnez **[!UICONTROL Administration > Paramétrage de l&#39;application > Comptes externes]**, puis le compte externe **[!UICONTROL Routage des SMS par SMPP]**.
1. Dans la catégorie **[!UICONTROL Réponse automatique aux MO]**, cliquez sur **[!UICONTROL Créer un élément]** pour commencer à configurer votre réponse automatique.

   ![](assets/sms_mo_1.png)

1. Sélectionnez le mot-clé qui déclenchera cette réponse automatique. Les mots-clés ne respectent pas la casse. Dans le cas présent, si les destinataires envoient le mot-clé &quot;STOP&quot;, ils recevront la réponse automatique.

   Laissez cette colonne vide si vous souhaitez envoyer la même réponse quel que soit le mot-clé.

   ![](assets/sms_mo_2.png)

1. Dans le champ **[!UICONTROL Numéro court]**, indiquez un numéro généralement utilisé pour l&#39;envoi des diffusions qui servira de nom d&#39;expéditeur. Vous pouvez également laisser le champ **[!UICONTROL Numéro court]** vide pour envoyer la même réponse quel que soit le numéro court.

   ![](assets/sms_mo_4.png)

1. Saisissez la réponse à envoyer aux destinataires dans le champ **[!UICONTROL Répondre]**.

   Pour effectuer une action sans envoyer de réponse, laissez la colonne **[!UICONTROL Réponse]** vide. Cela permet par exemple de retirer de la quarantaine le numéro de téléphone d&#39;un utilisateur qui envoie un message autre que &quot;STOP&quot;.

   ![](assets/sms_mo_3.png)

1. Dans le champ **[!UICONTROL Action supplémentaire]**, associez une action à votre réponse automatique :

   * L&#39;action **[!UICONTROL Envoyer en quarantaine]** permet de mettre automatiquement en quarantaine le numéro de téléphone du profil.
   * L&#39;action **[!UICONTROL Supprimer de la quarantaine]** retire de la quarantaine le numéro de téléphone du profil.
   * L&#39;action **[!UICONTROL Aucune]** permet d&#39;envoyer uniquement le message aux destinataires sans effectuer d&#39;action.

   Par exemple, dans la configuration ci-dessous, si les destinataires envoient le mot-clé « STOP », ils reçoivent automatiquement une confirmation de désinscription et leur numéro de téléphone est mis en quarantaine, avec le statut **[!UICONTROL Sur liste bloquée]**. Ce statut se rapporte uniquement au numéro de téléphone. Le profil n’est pas placé sur la liste bloquée afin que l’utilisateur puisse continuer à recevoir des emails.

   ![](assets/sms_mo.png)

Les destinataires peuvent maintenant être automatiquement désabonnés de vos messages et mis en quarantaine avec cette réponse automatique. Les destinataires en quarantaine sont répertoriés dans la table **[!UICONTROL Adresses]** accessible via le menu **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Quarantaines.]** Pour plus d&#39;informations sur les quarantaines, consultez cette [section](../../sending/using/understanding-quarantine-management.md).

Au besoin, ces SMS entrants peuvent être stockés. Voir à ce propos cette [section](#storing-incoming-sms).

## Stocker les SMS entrants       {#storing-incoming-sms}

Dans le compte externe **[!UICONTROL Routage des SMS par SMPP]**, vous pouvez choisir de stocker les messages entrants, par exemple lorsqu&#39;un abonné répond &quot;STOP&quot; à un message SMS afin d&#39;être retiré de la liste des destinataires.

![](assets/sms_config_mo_1.png)

Si vous cochez **[!UICONTROL Stocker les MO entrants dans la base de données]** dans la catégorie **[!UICONTROL Paramètres du canal SMPP]**, tous les SMS seront stockés dans la table SMS entrants et peuvent être récupérés à l&#39;aide d&#39;une activité de requête dans un workflow.

Pour ce faire :

1. Dans le champ **[!UICONTROL Paramètres du canal SMPP]**, cochez **[!UICONTROL Stocker les MO entrants dans la base de données]**.

   ![](assets/sms_config_mo_2.png)

1. Dans l&#39;onglet **[!UICONTROL Activités marketing]**, cliquez sur **[!UICONTROL Créer]**, puis sélectionnez **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Sélectionnez votre type de workflow.
1. Editez les propriétés de votre workflow, puis cliquez sur **[!UICONTROL Créer]**. Pour plus d&#39;informations sur la création de workflows, reportez-vous à cette [section](../../automating/using/building-a-workflow.md).
1. Placez une activité **[!UICONTROL Requête]** dans un workflow, puis double-cliquez sur l&#39;activité.
1. Dans l&#39;onglet **[!UICONTROL Propriétés]** de la requête, sélectionnez **[!UICONTROL SMS entrants]** dans le champ **[!UICONTROL Ressource]**.

   ![](assets/sms_config_mo_4.png)

1. Ensuite, dans l&#39;onglet **[!UICONTROL Cible]**, placez la règle **[!UICONTROL Attributs de SMS entrants]**.

   ![](assets/sms_config_mo_5.png)

1. Nous voulons cibler ici chaque message entrant du jour précédent. Dans la catégorie **[!UICONTROL Champ]**, sélectionnez **[!UICONTROL Date de création (créé)]**.
1. Dans **[!UICONTROL Type de filtre]**, sélectionnez **[!UICONTROL Relatif]**, puis dans le **[!UICONTROL Niveau de précision]**, choisissez **[!UICONTROL Jour]**.

   ![](assets/sms_config_mo_6.png)

1. Vous pouvez ensuite choisir de récupérer les données à partir d&#39;aujourd&#39;hui, d&#39;hier ou des derniers jours. Une fois votre requête configurée, cliquez sur **[!UICONTROL Confirmer]**.

Cette requête récupérera chaque message STOP reçu selon la période sélectionnée.

L&#39;activité vous permet, par exemple, de créer une population et d&#39;améliorer la personnalisation de vos diffusions.
