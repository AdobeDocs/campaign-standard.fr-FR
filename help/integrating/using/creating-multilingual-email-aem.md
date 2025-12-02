---
title: Création d’un email multilingue avec l’intégration d’Adobe Experience Manager.
description: Avec l'intégration d'Adobe Experience Manager, vous pouvez créer du contenu directement dans AEM et l'utiliser ultérieurement dans Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 100%

---

# Création d&#39;un e-mail multilingue avec l&#39;intégration d&#39;Adobe Experience Manager {#creating-multilingual-email-aem}

Grâce à ce document, vous allez découvrir comment créer un email multilingue à l&#39;aide d&#39;Adobe Experience Manager et des copies de langue.

Les prérequis sont :

* Avoir accès à une instance AEM configurée pour l&#39;intégration.
* Avoir accès à une instance Adobe Campaign configurée pour l&#39;intégration.
* Un modèle d&#39;email multilingue Adobe Campaign paramétré pour recevoir du contenu AEM.

## Création d&#39;un contenu d&#39;e-mail dans Adobe Experience Manager {#creating-email-content-aem}

1. Dans la page d&#39;accueil d&#39;Adobe Experience Manager, sélectionnez **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. Sélectionnez le dossier dans lequel vous souhaitez créer votre page, puis cliquez sur **[!UICONTROL Créer]** et **[!UICONTROL Page]**. Nous créons ici notre page dans le dossier en_us qui sera notre langue par défaut.

   ![](assets/aem_acs_2.png)

1. Sélectionnez le modèle **[!UICONTROL Email Adobe Campaign (ACS)]**.

1. Renseignez les propriétés de votre email et cliquez sur **[!UICONTROL Créer]**.

   ![](assets/aem_acs_3.png)

1. Ouvrez votre nouveau contenu d&#39;email et personnalisez-le selon vos besoins. Pour plus d’informations à ce sujet, consultez cette [page](../../integrating/using/creating-email-experience-manager.md#editing-email-aem).

   ![](assets/aem_acs_4.png)

1. Dans l’onglet **[!UICONTROL Processus]**, sélectionnez le workflow de validation **[!UICONTROL Approuver pour Adobe Campaign]**. Vous ne pouvez pas envoyer d&#39;email dans Adobe Campaign si son contenu n&#39;a pas été validé.

   ![](assets/aem_acs_7.png)

1. Cliquez sur **[!UICONTROL Terminer]**, puis sur **[!UICONTROL Révision de la newsletter]** dans la fenêtre **[!UICONTROL Terminer l&#39;élément de travail]**.

1. Cliquez sur **[!UICONTROL Terminer]**, puis sur **[!UICONTROL Approbation de la newsletter]**. Une fois que le contenu et les paramètres d’envoi sont définis, vous pouvez passer à la validation, à la préparation et à l’envoi de l’email dans Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Création de copies de langue {#creating-language-copies}

Après avoir conçu le contenu de votre email, vous devez créer des copies de langue qui seront synchronisées avec Adobe Campaign Standard en tant que variantes.

1. Sélectionnez la page que vous avez créée précédemment, cliquez sur **[!UICONTROL Créer]**, puis sur **[!UICONTROL Copie linguistique]**.

   ![](assets/aem_acs_5.png)

1. Sélectionnez le contenu de votre email créé précédemment qui sera traduit dans les langues choisies, puis cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/aem_acs_6.png)

1. Dans la liste déroulante **[!UICONTROL Langue(s) cible(s)]**, sélectionnez la langue dans laquelle votre contenu sera traduit, puis cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/aem_acs_9.png)

1. Cliquez sur **[!UICONTROL Créer]**.

Vos copies de langue sont créées. Vous pouvez maintenant modifier le contenu en fonction de la langue choisie.

>[!CAUTION]
>
>Chaque copie linguistique doit être approuvée via le workflow de validation **[!UICONTROL Approuver pour Adobe Campaign]**. Vous ne pouvez pas envoyer d&#39;email dans Adobe Campaign si son contenu n&#39;a pas été validé.

![](assets/aem_acs_11.png)

## Création de contenu multilingue dans Adobe Campaign Standard {#multilingual-acs}

1. Dans la page d&#39;accueil Adobe Campaign Standard, cliquez sur **[!UICONTROL Créer un email]**.

   ![](assets/aem_acs_12.png)

1. Sélectionnez le modèle d&#39;email multilingue Adobe Campaign configuré pour recevoir le contenu Adobe Experience Manager. Pour en savoir plus sur la création d&#39;un modèle lié à votre instance Adobe Experience Manager, consultez cette [page](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >Dans le cas présent, vous devrez dupliquer le modèle intégré **[!UICONTROL Email multilingue (mailMultiLang)]** pour pouvoir envoyer votre email multilingue.

   ![](assets/aem_acs_13.png)

1. Renseignez les champs **[!UICONTROL Propriétés]** et **[!UICONTROL Audience]** de l&#39;email, puis cliquez sur **[!UICONTROL Créer]**.

1. Dans **[!UICONTROL Éditer les propriétés]**, vérifiez que votre compte Adobe Experience Manager est correctement défini dans la liste déroulante **[!UICONTROL Contenu]**.

   ![](assets/aem_acs_20.png)

1. Cliquez sur **[!UICONTROL Création de la copie linguistique]**.

   ![](assets/aem_acs_16.png)

1. Sélectionnez le contenu Adobe Experience Manager que vous avez créé précédemment et cliquez sur **[!UICONTROL Confirmer]**. Le contenu Adobe Experience Manager affiché ici n&#39;est que du contenu validé et peut être filtré en fonction de ses **[!UICONTROL Libellé]** et **[!UICONTROL Chemin]**.

   >[!NOTE]
   >
   >La copie linguistique choisie sera définie par défaut. Vous pourrez la modifier ultérieurement dans le bloc **[!UICONTROL Variante du contenu]**.

   ![](assets/aem_acs_17.png)

1. Cliquez sur **[!UICONTROL Créer des variantes]** pour lier votre contenu multilingue. Adobe Campaign Standard lie alors automatiquement les autres copies de langue à ce contenu. Les variantes créées ont le même libellé et le même code de langue que ceux choisis dans Adobe Experience Manager.

   ![](assets/aem_acs_18.png)

1. Cliquez sur le bloc **[!UICONTROL Variante du contenu]** pour modifier votre variante par défaut en cas de besoin. Cliquez ensuite sur **[!UICONTROL Confirmer]**.

   ![](assets/aem_acs_19.png)

1. Si votre contenu ou vos variantes sont mis à jour dans Adobe Experience Manager, vous pouvez directement les synchroniser dans Adobe Campaign Standard avec le bouton **[!UICONTROL Actualiser les contenus AEM]**.

1. Votre email est désormais prêt à être envoyé. Pour plus d’informations à ce propos, consultez cette [page](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >Vous ne pouvez pas envoyer d&#39;e-mail dans Adobe Campaign si son contenu AEM pas été validé.

Votre audience recevra votre email selon les **[!UICONTROL Préférences linguistiques]** définies dans leurs **[!UICONTROL Profils]**. Pour en savoir plus sur la modification des profils et des préférences linguistiques, consultez cette [page](../../audiences/using/editing-profiles.md).
