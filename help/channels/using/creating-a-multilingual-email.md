---
title: Créer un email multilingue
description: Suivez ces étapes pour créer un email multilingue qui cible des destinataires avec des préférences linguistiques différentes.
page-status-flag: never-activated
uuid: e90f4ec8-14e3-4304-b5fc-bce0ba08a4ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: 79231445-1d51-499a-adcf-0c0f6db1cfa3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Créer un email multilingue{#creating-a-multilingual-email}

Vous pouvez envoyer un email multilingue aux profils ayant des préférences linguistiques différentes : chaque profil recevra une variante de l&#39;email dans sa langue préférée.

Pour cela, vérifiez qu&#39;un modèle d&#39;email multilingue est disponible. Si ce n&#39;est pas le cas, apprenez à en créer un dans [cette section](../../channels/using/multilingual-messages-template.md).

L&#39;audience est composée de profils dont la préférence linguistique a été indiquée.

1. Créez un email à partir d&#39;un [modèle multilingue](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Définissez les propriétés générales et l&#39;audience cible de l&#39;email de la même manière que pour un email standard. Consultez la section [Créer une audience](../../audiences/using/creating-audiences.md).
1. A la quatrième étape de l&#39;assistant de création, définissez les options des variantes. Si le [modèle multilingue](../../channels/using/multilingual-messages-template.md) contient déjà tous les paramètres désirés, vous pouvez cliquer directement sur le bouton **[!UICONTROL Créer]**.

   ![](assets/multi_create4.png)

   Au besoin, ajoutez des variantes à l&#39;aide du bouton **[!UICONTROL Ajouter un élément]**. **[!UICONTROL La variante Par défaut]** ne doit pas être supprimée. Lorsqu&#39;elle est définie sur la valeur **[!UICONTROL Par défaut]**, la [langue préférée du profil](../../audiences/using/creating-profiles.md) est utilisée pour sélectionner la variante. Vous pouvez également définir la variante **[!UICONTROL Par défaut]** sur n&#39;importe quelle autre langue.

1. Confirmez la création de l&#39;email : le tableau de bord des emails s&#39;affiche alors.
1. Définissez le contenu de chaque variante d&#39;email. En fonction du modèle que vous avez choisi, vous pouvez définir plusieurs objets, plusieurs noms d&#39;expéditeurs ou plusieurs contenus différents. Utilisez le menu déroulant afin de naviguer entre les différentes variantes de l&#39;élément. Pour plus d&#39;informations, consultez la section relative à l&#39;[éditeur de contenu](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Testez votre message et validez-le. Reportez-vous à la section [Envoyer un bon à tirer (BAT)](../../sending/using/sending-proofs.md).
1. Planifiez l&#39;envoi à l&#39;aide de l&#39;option **[!UICONTROL Envoi après confirmation]**.
1. Une fois l&#39;email envoyé, vous pouvez accéder à ses logs et rapports pour mesurer le succès de votre campagne. Pour plus d’informations sur le reporting, consultez [cette section](../../reporting/using/about-dynamic-reports.md).

**Rubrique connexe :**

* [Atteindre des audiences multilingues à l&#39;aide d&#39;un seul workflow](https://helpx.adobe.com/fr/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
