---
title: FAQ sur la synchronisation avec le lancement du processus technique
description: Questions courantes à propos du processus technique de lancement.
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95a7397092f6e07c84967d90908469f630f7a170
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 6%

---


# FAQ sur la synchronisation des lancements d&#39;Adobe {#syncwithlaunch-faq}

Vous pouvez importer les propriétés de lancement d’Adobe mobile dans Adobe Campaign Standard via le processus technique dédié **[!UICONTROL Synchroniser avec le lancement]** . Pour plus d’informations, consultez cette [page](../../administration/using/technical-workflows.md)

La section ci-dessous liste les questions courantes sur cette synchronisation.

>[!NOTE]
>
>You will need to submit a ticket to Adobe Customer Care (either directly or through your Adobe contact) to have the **[!UICONTROL syncWithLaunch]** technical workflow enabled in your Campaign instance.

## J&#39;ai créé une propriété dans [!DNL Launch] (non-administrateur de l&#39;unité d&#39;organisation TOUT). Mon application est à l&#39;état Prêt à configurer en Adobe Campaign, mais je ne peux pas l&#39;ouvrir/configurer. {#configuring-property}

Seul l’administrateur de l’unité d’organisation ALL peut configurer des applications mobiles en Adobe Campaign Standard. Une fois configurée, seuls les utilisateurs de l&#39;unité d&#39;organisation affectée peuvent modifier l&#39;application. For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Je ne peux pas modifier une application mobile configurée en Adobe Campaign Standard et les applications mobiles sont en mode lecture seule. {#read-mode-mobile-app}

Vérifiez l&#39;unité d&#39;organisation de l&#39;application mobile dans la **[!UICONTROL section Autorisation d&#39;]** accès. Seuls les utilisateurs de l&#39;unité d&#39;organisation affectée peuvent modifier l&#39;application mobile.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Je suis un administrateur de l&#39;unité d&#39;organisation ALL en Adobe Campaign Standard mais je ne peux pas configurer d&#39;application mobile. {#org-unit-mobile}

Un administrateur dont l’unité d’organisation est définie sur ALL doit disposer de droits sur toutes les propriétés mobiles dans [!DNL Launch] la configuration de l’application mobile.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## J&#39;ai créé une propriété mobile dans [!DNL Launch] mais ma propriété n&#39;est pas visible en Adobe Campaign Standard. {#visibility-mobile-property}

1. Vérifiez que l’extension Adobe Campaign Standard est installée dans la propriété mobile de [!DNL Launch].

1. Vérifiez que les points de terminaison de l’instance sont correctement configurés dans l’extension.

1. Vérifiez que &quot;Launch_URL_Campaign&quot; ou &quot;NmsServer_URL&quot; sont corrects.

1. Ensuite, vérifiez que la synchronisation entre [!DNL Launch] et Adobe Campaign est terminée avec le processus technique **[!UICONTROL syncWithLaunch]** .

## Comment vérifier si la synchronisation entre Adobe Campaign et Launch est terminée ? {#sync-campaign-launch}

1. Dans le menu avancé d’Adobe Campaign Standard, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l’application]** > **[!UICONTROL Workflows]**.

1. Ouvrez le processus **[!UICONTROL syncWithLaunch]** .

1. Vérifiez si le flux de travaux s’est terminé sans erreur.

1. Vérifiez dans les journaux que la synchronisation du flux de travail est activée et que vous avez terminé.

## J&#39;ai réinitialisé la clé pour une application mobile configurée dans Launch. Comment reconfigurer la clé dans Lancement ? {#configuring-pkey}

1. Ouvrez la propriété mobile dans Lancement d’Adobe.

1. Définissez une nouvelle URL dans l’extension Adobe Campaign Standard pour laquelle PKey a été réinitialisé.

1. Enregistrez-la et laissez le flux de travail synchronisé entre Adobe Campaign et [!DNL Launch].

1. Une fois la synchronisation terminée, ouvrez la propriété mobile dans [!DNL Launch].

1. Définissez l’URL correcte dans l’extension Adobe Campaign Standard pour laquelle PKey a été réinitialisé.

1. Enregistrez-la et laissez le processus se synchroniser à nouveau.

1. Ce n’est qu’à ce moment que la propriété apparaîtra dans l’état **[!UICONTROL Prêt à configurer]** en Adobe Campaign et peut désormais être configurée.

## Je souhaite configurer une propriété mobile en Adobe Campaign. Dois-je attendre que le processus technique se synchronise entre le lancement d&#39;Adobe et Adobe Campaign ?

Vous pouvez exécuter immédiatement le processus :

1. Dans le menu avancé d’Adobe Campaign Standard, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l’application]** > **[!UICONTROL Workflows]**.

1. Ouvrez le processus **[!UICONTROL syncWithLaunch]** .

1. Cliquez sur l’activité **[!UICONTROL Planificateur]** et sélectionnez Exécution **** immédiate.
