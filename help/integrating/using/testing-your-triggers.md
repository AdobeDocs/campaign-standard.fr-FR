---
solution: Campaign Standard
product: campaign
title: Test de vos déclencheurs
description: null
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '450'
ht-degree: 100%

---


# Test de vos déclencheurs{#testing-your-triggers}

Les conseils de dépannage suivants vous aideront à résoudre les problèmes les plus courants que vous pouvez rencontrer lors de l’utilisation de Triggers avec Adobe Campaign :

**La fonctionnalité est-elle activée ?**

Pour vérifier si l’intégration Triggers - Campaign est activée, cliquez sur le logo Adobe Campaign, en haut à gauche, puis sélectionnez **[!UICONTROL Plans marketing]** > **[!UICONTROL Messages transactionnels]**. Vous devriez voir l’élément **[!UICONTROL Triggers Experience Cloud]**.

Si vous le voyez, passez à l’étape suivante.

Dans le cas contraire, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels. Consultez [Activation de la fonctionnalité](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Tentative de création d’un déclencheur**

Suivez les étapes décrites dans [Création d’un déclencheur mappé dans Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) pour créer un déclencheur.

Si le déclencheur est créé, passez à l’étape suivante. Dans le cas contraire, la connexion du paramétrage de l’intégration du déclencheur a échoué. Vérifiez si Triggers est configuré dans Experience Cloud (Découvrez les notions de base d’Adobe Campaign par le biais de procédures détaillées simples et tirez parti de la puissance de la solution.). Dans le cas contraire, contactez votre chargé de compte Adobe ou votre partenaire de services professionnels. Les informations suivantes sont nécessaires :

* Nom de la société Experience Cloud
* Identifiant de l’organisation IMS
* Identifiant de société Analytics (peut être identique au nom de la société Experience Cloud)

**Tentative de publication d’un déclencheur**

Suivez les étapes décrites dans [Création d’un déclencheur mappé dans Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) pour publier un déclencheur.

Si la publication est bien effectuée, passez à l’étape suivante. Dans le cas contraire, contactez Adobe pour relancer votre instance et réessayez.

**Génération du déclencheur à partir du site Web**

Suivez les étapes décrites dans [Édition du modèle de message transactionnel](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) pour modifier et publier le modèle transactionnel. Essayez ensuite de générer le déclencheur à partir du site Web.

Si Analytics reçoit le déclencheur, passez à l’étape suivante. Dans le cas contraire, contrôlez les éléments suivants :

* Le déclencheur est activé pour Analytics
* Le site Web a utilisé MCID et Analytics est activé dans DTM
* La bonne suite de rapports Analytics est utilisée lors de la création des déclencheurs

**Campaign reçoit-il le déclencheur ?**

Dans le cas contraire, le déclencheur est transmis par le pipeline.

Dans le cas contraire, contactez Adobe pour vérifier la configuration des points de terminaison de pipeline.

Si tel est le cas, suivez ces directives :

* Vérifiez le type d’ID de réconciliation dans la source de données Campaign.
* La source de données CustomerId est créée via les attributs du client.
* Vérifiez l’ID de la source de donnée.
* Demandez à Adobe de relancer l’instance de Campaign après la configuration de la source de données.
* Vérifier les problèmes d’analyse du déclencheur dans le rapport de déclencheur.

**Le déclencheur est-il à l’état En attente ?**

Dans le cas contraire, passez à l’étape suivante. Si tel est le cas, suivez ces directives :

* Vérifiez que le modèle transactionnel a été publié.
* Vérifiez que le profil n’est pas sur liste bloquée.
* Vérifiez l’application des règles de typologie.
* Vérifiez les logs du message transactionnel.

**Le message est-il valide ?**

Si le message n’est pas valide, vérifiez les éléments suivants :

* Pour les champs de personnalisation d’enrichissement de déclencheur, validez le modèle transactionnel des collections eventCusResource associées.
* Validation du format du message

