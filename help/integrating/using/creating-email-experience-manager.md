---
solution: Campaign Standard
product: campaign
title: Création d’un contenu d’email dans Adobe Experience Manager.
description: Avec l'intégration d'Adobe Experience Manager, vous pouvez créer du contenu directement dans AEM et l'utiliser ultérieurement dans Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 99%

---


# Import d’un contenu Adobe Experience Manager dans un email Adobe Campaign {#creating-email-aem}

A travers ce document, vous apprendrez à créer et gérer des contenus d&#39;email dans Adobe Experience Manager, puis à les utiliser pour vos campagnes marketing en les important dans vos emails Adobe Campaign Standard.

Les prérequis sont :

* Avoir accès à une instance AEM configurée pour l&#39;intégration.
* Avoir accès à une instance Adobe Campaign configurée pour l&#39;intégration.
* Un modèle d&#39;email Adobe Campaign paramétré pour recevoir du contenu AEM.

## Accès aux emails dans Adobe Experience Manager {#email-content-aem}

Connectez-vous à votre instance Adobe Experience Manager de création et parcourez votre site pour accéder au dossier contenant les contenus d&#39;emails.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Création d’un contenu d’email dans Adobe Experience Manager {#creating-email-content-aem}

Plusieurs modèles spécifiques à Adobe Campaign sont disponibles. Vous devez utiliser l’un de ces modèles car ils contiennent des composants prédéfinis pris en charge par Adobe Campaign.

Par défaut, deux modèles prédéfinis permettent de créer des contenus d&#39;email pour Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]** : ce modèle contient du contenu standard que vous pouvez personnaliser. Vous pouvez choisir entre Adobe Campaign Email (AC6.1) et Adobe Campaign Email (ACS).
* **[!UICONTROL Page d&#39;importateur]** : ce modèle permet d&#39;importer un fichier ZIP comportant un fichier HTML dont vous pourrez personnaliser le contenu.

1. Dans Adobe Experience Manager, créez une **[!UICONTROL page]**.

1. Sélectionnez le modèle **[!UICONTROL Adobe Campaign Email]**. Regardez la vidéo ci-après pour connaître les étapes détaillées.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Ouvrez votre nouveau contenu d’email.

1. Dans les **[!UICONTROL Propriétés de la page]**, définissez **[!UICONTROL Adobe Campaign]** comme **[!UICONTROL Configuration du service Cloud]**. Cela permet la communication entre votre contenu et votre instance Adobe Campaign.

   Pour en savoir plus, visionnez la vidéo suivante :

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Modification et envoi d’un email{#editing-email-aem}

Vous pouvez modifier le contenu de l’email en ajoutant des composants et des ressources. Les champs de personnalisation peuvent être utilisés pour diffuser un message plus pertinent en fonction des données des destinataires dans Adobe Campaign.

Pour créer un contenu d&#39;email dans Adobe Experience Manager :

1. Modifiez l’objet ainsi que la version **[!UICONTROL text brut]** de votre email en accédant à l’onglet **[!UICONTROL Propriétés de la page]**> **[!UICONTROL Email]**.

1. Ajoutez des **[!UICONTROL champs de personnalisation]** via le composant **[!UICONTROL Texte et personnalisation]**. Chaque composant correspond à une utilisation spécifique : insertion d’images, ajout de personnalisation, etc.

   Pour en savoir plus, visionnez la vidéo suivante :
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Dans l’onglet **[!UICONTROL Processus]**, sélectionnez le workflow de validation **[!UICONTROL Approuver pour Adobe Campaign]**. Vous ne pouvez pas envoyer d&#39;email dans Adobe Campaign si son contenu n&#39;a pas été validé.

1. Une fois que le contenu et les paramètres d’envoi sont définis, vous pouvez passer à la validation, à la préparation et à l’envoi de l’email dans Adobe Campaign Standard.

   Pour en savoir plus, visionnez la vidéo suivante :

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
