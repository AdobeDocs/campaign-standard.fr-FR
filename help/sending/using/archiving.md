---
title: Archivage des messages dans Adobe Campaign Standard
description: Découvrez comment archiver des emails avec Adobe Campaign Standard à l’aide d’une adresse email en Cci.
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
source-git-commit: 72366d56e21933bcd79e907e5f8d5a9ad5281725

---


# Archivage avec Email BCC{#archiving-emails}

Vous pouvez paramétrer Adobe Campaign pour conserver une copie des emails envoyés depuis votre plateforme via Email BCC.

Activez cette fonctionnalité notamment si votre entreprise doit archiver tous les emails sortants à des fins de conformité. Celle-ci vous permet d’envoyer une copie cachée exacte des messages envoyés correspondants à une adresse email en Cci (invisible aux destinataires de l’envoi) que vous devez spécifier.

Once enabled, you need to activate Email BCC from the **[!UICONTROL Archive emails]** option in the email delivery template.

>[!NOTE]
>
>Adobe Campaign ne gère pas les fichiers archivés. Il vous permet d’envoyer les messages de votre choix à une adresse dédiée, à partir de laquelle ils peuvent être traités et archivés au moyen d’un système externe.

## Recommandations et limitations     {#recommendations-and-limitations}

* Cette fonctionnalité est en option. Vérifiez votre contrat de licence et contactez votre chargé de compte pour l’activer.
* L’adresse en Cci de votre choix doit être fournie à l’équipe Adobe qui la configurera pour vous.
* Vous ne pouvez utiliser qu’une seule adresse email en Cci.
* Seuls les emails envoyés sont pris en compte, les rebonds ne le sont pas.
* Pour des raisons de confidentialité, les emails en Cci doivent être traités dans un système d’archivage capable de stocker en toute sécurité les informations d’identification personnelles (PII).
* Lors de la création d’un modèle de diffusion, l’option Email BCC n’est pas activée par défaut, même si elle a été achetée. Vous devez l’activer manuellement dans chaque modèle de diffusion où vous souhaitez l’utiliser.

>[!NOTE]
>
>Actuellement, les emails archivés ne peuvent pas être envoyés avec le MTA amélioré d’Adobe Campaign, même si vous avez déjà effectué une mise à niveau vers celui-ci.

## Activer l’archivage des emails     {#activating-email-archiving}

Une fois activée, la fonctionnalité Email BCC est activée dans le [modèle d’email](../../start/using/marketing-activity-templates.md) par le biais d’une option dédiée :

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