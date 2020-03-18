---
title: Archivage des messages dans  Adobe Campaign Standard
description: Découvrez comment archiver des courriers électroniques avec  Adobe Campaign Standard à l’aide d’une adresse de messagerie en CC.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2bf1f8acb581645a6f89f50443a8d9a49d8acaf1

---


# Archivage avec BCC de courrier électronique{#archiving-emails}

Vous pouvez configurer  Adobe Campaign pour conserver une copie des courriers électroniques envoyés à partir de votre plate-forme via le Cci électronique.

En particulier, si votre entreprise doit archiver tous les messages électroniques sortants pour qu’ils soient conformes, vous pouvez activer cette fonctionnalité. Il vous permet d&#39;envoyer une copie cachée exacte des messages envoyés correspondants à une adresse de courriel en copie carbone invisible pour les de que vous devez spécifier.

Une fois activé, vous devez activer le Cci électronique à partir de l’ **[!UICONTROL Archive emails]** option du de messagerie.

>[!NOTE]
>
> Adobe Campaign ne gère pas les fichiers archivés. Il vous permet d&#39;envoyer les messages de votre choix à une adresse dédiée, à partir de laquelle ils peuvent être traités et archivés au moyen d&#39;un système externe.

## Recommandations et limitations   {#recommendations-and-limitations}

* Cette fonctionnalité est en option. Vérifiez votre contrat de licence et contactez votre chargé de compte pour l&#39;activer.
* L’adresse CC de votre choix doit être fournie à l’équipe Adobe qui la configurera pour vous.
* Vous ne pouvez utiliser qu&#39;une seule adresse email en Cci.
* Seuls les emails envoyés sont pris en compte, les rebonds ne le sont pas.
* Pour des raisons de confidentialité, les emails en Cci doivent être traités dans un système d&#39;archivage capable de stocker en toute sécurité les informations d&#39;identification personnelles (PII).
* Lors de la création d&#39;un modèle de diffusion, l&#39;option Email BCC n&#39;est pas activée par défaut, même si elle a été achetée. Vous devez l&#39;activer manuellement dans chaque modèle de diffusion où vous souhaitez l&#39;utiliser.

>[!NOTE]
>
>Actuellement, les courriers électroniques archivés ne peuvent pas être envoyés avec la [MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)améliorée, même si vous avez déjà été mis à niveau vers la MTA améliorée.

## Activer l&#39;archivage des emails   {#activating-email-archiving}

Once enabled, Email BCC is activated in the [email template](../../start/using/marketing-activity-templates.md), through a dedicated option:

1. Accédez à **Ressources** > **Modèles** > **Modèles de diffusion**.
1.  le modèle prêt à l’emploi **[!UICONTROL Send via email]** .
1. Sélectionnez le modèle dupliqué.
1. Click the **[!UICONTROL Edit properties]** button to edit the template&#39;s properties.
1. Développez la **[!UICONTROL Send]** section.
1. Check the **[!UICONTROL Archive emails]** box to keep a copy of all sent messages for each delivery based on this template.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.