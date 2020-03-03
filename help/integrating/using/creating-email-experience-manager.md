---
title: Création d’un contenu d’email dans Adobe Experience Manager.
description: Avec l'intégration d'Adobe Experience Manager, vous pouvez créer du contenu directement dans AEM et l'utiliser ultérieurement dans Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9efce905cd767013a22afb2a4d642e42b6616ef1

---


# Importation d’un contenu Adobe Experience Manager dans un courrier électronique Adobe Campaign {#creating-email-aem}

A travers ce document, vous apprendrez à créer et gérer des contenus d&#39;email dans Adobe Experience Manager, puis à les utiliser pour vos campagnes marketing en les important dans vos emails Adobe Campaign Standard.

Les prérequis sont :

* Avoir accès à une instance AEM configurée pour l&#39;intégration.
* Avoir accès à une instance Adobe Campaign configurée pour l&#39;intégration.
* Un modèle d&#39;email Adobe Campaign paramétré pour reçevoir du contenu AEM.

## Accès aux courriers électroniques dans Adobe Experience Manager {#email-content-aem}

Connectez-vous à votre instance de création Adobe Experience Manager et parcourez votre site pour accéder au dossier contenant votre contenu de courrier électronique.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Creating new email content in Adobe Experience Manager {#creating-email-content-aem}

Plusieurs modèles spécifiques à Adobe Campaign sont disponibles. Vous devez utiliser l’un de ces modèles, car ils contiennent des composants prédéfinis pris en charge par Adobe Campaign.

Par défaut, deux modèles prédéfinis permettent de créer des contenus d&#39;email pour Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: ce modèle contient un contenu standard que vous pouvez personnaliser. Vous pouvez choisir entre Courriel Adobe Campaign (AC6.1) et Courriel Adobe Campaign (ACS).
* **[!UICONTROL Importer Page]**: ce modèle vous permet d&#39;importer un fichier ZIP contenant un fichier HTML avec du contenu que vous pourrez ensuite personnaliser.

1. Dans Adobe Experience Manager, créez un nouveau **[!UICONTROL Page]**.

1. Select the **[!UICONTROL Adobe Campaign Email]** template. Reportez-vous à la vidéo suivante pour connaître les étapes détaillées.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Ouvrez votre nouveau contenu de courrier électronique.

1. Dans la **[!UICONTROL Page properties]**, définissez **[!UICONTROL Adobe Campaign]** comme **[!UICONTROL Cloud Service Configuration]**. Cela permet la communication entre votre contenu et votre instance Adobe Campaign.

   Pour en savoir plus, visionnez la vidéo suivante :

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Modification et envoi d’un courrier électronique {#editing-email-aem}

Vous pouvez modifier le contenu du courrier électronique en ajoutant des composants et des ressources. Les champs de personnalisation peuvent être utilisés pour diffuser un message plus pertinent en fonction des données des destinataires dans Adobe Campaign.

Pour créer un contenu d&#39;email dans Adobe Experience Manager :

1. Edit the subject as well as the **[!UICONTROL Plain text]** version of your email by accessing the **[!UICONTROL Page properties]** > **[!UICONTROL Email]** tab from the sidekick.

1. Ajouter **[!UICONTROL Personalization fields]** par le biais du **[!UICONTROL Text & Personalization]** composant. Chaque composant correspond à une utilisation spécifique : insertion d’images, ajout de personnalisation, etc.

   Pour en savoir plus, visionnez la vidéo suivante :
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Dans l’ **[!UICONTROL Workflow]** onglet, sélectionnez le processus de **[!UICONTROL Approve for Adobe Campaign]** validation. Vous ne pourrez pas envoyer de courrier électronique dans Adobe Campaign s’il utilise un contenu non approuvé.

1. Une fois le contenu et les paramètres d’envoi définis, vous pouvez procéder à l’approbation, à la préparation et à l’envoi du courrier électronique dans Adobe Campaign Standard.

   Pour en savoir plus, visionnez la vidéo suivante :

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
