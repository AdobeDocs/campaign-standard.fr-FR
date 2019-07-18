---
title: A propos des triggers Adobe Experience Cloud
seo-title: A propos des triggers Adobe Experience Cloud
description: A propos des triggers Adobe Experience Cloud
seo-description: Grâce au tracking de comportements spécifiques des clients avec Adobe Analytics, vous pouvez maintenant leur envoyer des emails personnalisés dans Adobe Campaign.
page-status-flag: jamais activé
uuid: 0 aa 4 bd 6 e -1 bb 5-4 d 0 b -913 b-eca 93 f 050 acd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: intégration
content-type: référence
topic-tags: working-with-campaign-and-triggers
discoiquuid: e 526 b 205-2 d 01-4 a 8 b -9685-ba 1 d 9 a 1 f 459 f
context-tags: trigger, overview ; trigger, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# A propos des triggers Adobe Experience Cloud{#about-adobe-experience-cloud-triggers}

L'intégration entre le core service Activation Experience Cloud **[!UICONTROL Triggers]et Adobe Campaign permet d'envoyer des emails personnalisés à vos clients en réaction à des comportements spécifiques trackés sur votre site web par Adobe Analytics (dans un délai de 15 minutes).**

Dans Adobe Experience Cloud, vous définissez les différents triggers, c'est-à-dire les comportements des clients que vous souhaitez contrôler, comme tous les clients qui ont abandonné leur visite de votre site Web, effectué une recherche sur votre site Web, mais sans effectuer d'achats, ou dont la session a expiré. Lors de la création d'un trigger, vous définissez la condition du trigger et les données qui seront envoyées à Adobe Campaign dans l'événement (pload).

Dans Adobe Campaign, vous sélectionnez le trigger qui a été précédemment créé, vous enrichissez les données de l'événement avec celles du datamart et vous définissez un modèle de message transactionnel lié au trigger. Par exemple, lorsqu'un client abandonne sa visite de votre site Web, un événement est envoyé à Adobe Campaign. Adobe Campaign peut ensuite utiliser cet événement par le biais d'un email de remarketing envoyé au client dans un délai de 15 minutes.

**Rubriques connexes :**

* Apprenez-en plus sur les différents types de triggers : [documentation Adobe Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html).
* Regardez la vidéo [Déclencher des messages de remarketing selon l'activité du site](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).
* Découvrez nos deux [cas pratiques Triggers d'abandon](../../integrating/using/abandonment-triggers-use-cases.md).

## Processus utilisateur de triggers {#triggers-user-process}

>[!CAUTION]
>
>Avant d'effectuer les principales étapes utilisateur, la fonctionnalité doit être configurée. Pour plus d'informations à ce sujet, consultez [Activation de la fonctionnalité](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuration des solutions et services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) et [Création d'un trigger mappé dans Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

Dans Adobe Campaign, les étapes principales du processus utilisateur sont les suivantes :

1. Création d'un événement déclencheur lié à un trigger Adobe Experience Cloud existant
1. Publication de l'événement déclencheur.
1. Définition du contenu du modèle de message transactionnel.
1. Test du modèle (création d'un profil de test et envoi d'un BAT).
1. Publication du modèle de message transactionnel.

Des cas pratiques complets sont présentés dans [cette section](../../integrating/using/abandonment-triggers-use-cases.md).

## Remarques importantes {#important-notes}

Voici quelques remarques importantes à prendre en considération avant d'utiliser l'intégration des triggers Campaign :

* Les notifications push ne sont pas prises en charge pour les triggers. Seuls les emails et les SMS sont pris en charge.
* Vous pouvez enrichir le trigger de métadonnées récupérées par Analytics comme les ID d'email, les noms de page, etc.
* Vous pouvez réconcilier le trigger à un profil enregistré dans Campaign Standard et utiliser les champs du profil pour personnaliser le message.
* Dès que le trigger est transmis, il est traité, réconcilié et renvoyé. Cette opération prend entre 5 et 15 minutes en fonction du volume des triggers reçus et du nombre de champs de personnalisation utilisés dans le modèle.

>[!NOTE]
>
>Pour en savoir plus sur les bonnes pratiques et les limites techniques, consultez [Bonnes pratiques et limites de triggers](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

