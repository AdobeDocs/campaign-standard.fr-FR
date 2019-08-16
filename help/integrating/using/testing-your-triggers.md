---
title: Test de vos triggers
seo-title: Test de vos triggers
description: Test de vos triggers
seo-description: null
page-status-flag: never-activated
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: ht
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Test de vos triggers{#testing-your-triggers}

Les conseils de dépannage suivants vous aideront à résoudre les problèmes les plus courants que vous pouvez rencontrer lors de l'utilisation de triggers avec Adobe Campaign :

**La fonctionnalité est-elle activée ?**

Pour vérifier si l'intégration des triggers Campaign est activée, cliquez sur le logo Adobe Campaign, en haut à gauche, puis sélectionnez **[!UICONTROL Plans marketing]** &gt; **[!UICONTROL Messages transactionnels]**. Vous devriez voir l'élément **[!UICONTROL Triggers Experience Cloud]**.

Si vous le voyez, passez à l'étape suivante.

Dans le cas contraire, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels. Consultez [Activation de la fonctionnalité](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Tentative de création d'un trigger**

Suivez les étapes décrites dans [Création d'un trigger mappé dans Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) pour créer un trigger.

Si le trigger est créé, passez à l'étape suivante. Dans le cas contraire, la connexion du paramétrage de l'intégration Trigger a échoué. Vérifiez si Triggers est configuré dans Experience Cloud (services d'activation). Dans le cas contraire, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels. Les informations suivantes sont nécessaires :

* Nom de la société Marketing Cloud
* ID de l'organisation IMS
* Identifiant de société Analytics (peut être identique au nom de la société Marketing Cloud)

**Tentative de publication d'un trigger**

Suivez les étapes décrites dans [Création d'un trigger mappé dans Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) pour publier un trigger.

Si la publication est bien effectuée, passez à l'étape suivante. Dans le cas contraire, contactez Adobe pour relancer votre instance et réessayez.

**Génération du trigger à partir du site Web**

Suivez les étapes décrites dans [Édition du modèle de message transactionnel](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) pour modifier et publier le modèle transactionnel. Essayez ensuite de générer le trigger à partir du site Web.

Si Analytics reçoit le trigger, passez à l'étape suivante. Dans le cas contraire, contrôlez les éléments suivants :

* Le Trigger est activé pour Analytics
* Le site Web a utilisé MCID et Analytics est activé dans DTM
* La bonne suite de rapports Analytics est utilisée lors de la création des triggers

**Campaign reçoit-il le trigger ?**

Dans le cas contraire, le trigger est transmis par la pipeline.

Dans le cas contraire, contactez Adobe pour vérifier la configuration des points de terminaison de pipeline.

Dans l'affirmative, suivez ces recommandations :

* Vérifiez le type d'ID de réconciliation dans la source de données Campaign.
* La source de données CustomerId est créée via les attributs du client.
* Vérifiez l'ID de la source de donnée.
* Demandez à Adobe de relancer l'instance de Campaign après la configuration de la source de données.
* Vérifier les problèmes d'analyse du trigger dans le rapport de trigger.

**Le trigger est-il à l'état En attente ?**

Dans le cas contraire, passez à l'étape suivante. Dans l'affirmative, suivez ces recommandations :

* Vérifiez que le modèle transactionnel a été publié.
* Si le seuil propensityScore est activé pour Campaign, vérifiez le score de propension du trigger de la pipeline.
* Vérifiez que le profil n'est pas blacklisté.
* Vérifiez l'application des règles de typologie.
* Vérifiez les logs du message transactionnel.

**Le message est-il valide ?**

Si le message n'est pas valide, vérifiez les éléments suivants :

* Pour les champs de personnalisation d'enrichissement de trigger, validez le modèle transactionnel des collections eventCusResource associées.
* Validation du format du message

