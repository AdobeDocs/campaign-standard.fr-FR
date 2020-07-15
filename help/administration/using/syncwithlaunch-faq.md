---
title: Gestion des accès
description: Gérez les opérateurs d'Adobe Campaign à l'aide des rôles, des groupes et des entités organisationnelles.
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
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 4%

---


# FAQ sur le processus technique SyncWithLaunch {#syncwithlaunch-faq}

The **[!UICONTROL Sync with Launch]** workflow enables automatic importing of all Adobe Launch mobile properties into Adobe Campaign Standard.

Pour plus d’informations à ce sujet, consultez [cette page](../../administration/using/technical-workflows.md).

>[!NOTE]
>
>You will need to submit a ticket to Adobe Customer Care (either directly or through your Adobe contact) to have the **[!UICONTROL syncWithLaunch]** technical workflow enabled in your Campaign instance.

## J&#39;ai créé une propriété dans [!DNL Launch] (non-administrateur de l&#39;unité d&#39;organisation TOUT). Mon application est à l&#39;état Prêt à configurer dans l&#39;Adobe Campaign mais je ne peux pas l&#39;ouvrir/configurer. {#configuring-property}

Seul l&#39;administrateur de l&#39;unité d&#39;organisation ALL peut configurer les applications mobiles dans l&#39;Adobe Campaign Standard. Une fois configurée, seuls les utilisateurs de l&#39;unité d&#39;organisation affectée peuvent modifier l&#39;application. For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Je ne peux pas modifier une application mobile configurée dans l&#39;Adobe Campaign Standard et les applications mobiles sont en mode lecture seule. {#read-mode-mobile-app}

Vérifiez l&#39;unité d&#39;organisation de l&#39;application mobile dans la **[!UICONTROL section Autorisation d&#39;]** accès. Seuls les utilisateurs de l&#39;unité d&#39;organisation affectée peuvent modifier l&#39;application mobile.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Je suis un administrateur de l&#39;unité d&#39;organisation ALL dans l&#39;Adobe Campaign Standard mais je ne peux pas configurer d&#39;application mobile. {#org-unit-mobile}

Un administrateur dont l’unité d’organisation est définie sur ALL doit disposer de droits sur toutes les propriétés mobiles dans [!DNL Launch] la configuration de l’application mobile.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## J&#39;ai créé une propriété mobile dans [!DNL Launch] mais ma propriété n&#39;est pas visible dans l&#39;Adobe Campaign Standard. {#visibility-mobile-property}

1. Vérifiez que l&#39;extension d&#39;Adobe Campaign Standard est installée dans la propriété mobile de [!DNL Launch].

1. Vérifiez que les points de terminaison de l’instance sont correctement configurés dans l’extension.

1. Vérifiez que &quot;Launch_URL_Campaign&quot; ou &quot;NmsServer_URL&quot; sont corrects.

1. Ensuite, vérifiez que la synchronisation entre [!DNL Launch] et l’Adobe Campaign est terminée avec le flux de travail technique **[!UICONTROL syncWithLaunch]** .

## Comment vérifier si la synchronisation entre l&#39;Adobe Campaign et le lancement est terminée ? {#sync-campaign-launch}

1. Dans Adobe Campaign Standard, dans le menu avancé, sélectionnez **[!UICONTROL Administration]** > Paramètres **[!UICONTROL de l’]** application > **[!UICONTROL Workflows]**.

1. Ouvrez le processus **[!UICONTROL syncWithLaunch]** .

1. Vérifiez si le flux de travaux s’est terminé sans erreur.

1. Vérifiez dans les journaux que la synchronisation du flux de travail est activée et que vous avez terminé.

## J&#39;ai réinitialisé la clé pour une application mobile configurée dans Launch. Comment reconfigurer la clé dans Lancement ? {#configuring-pkey}

1. Ouvrez la propriété mobile dans Adobe Launch.

1. Définissez une nouvelle URL dans l’extension d’Adobe Campaign Standard pour laquelle PKey a été réinitialisé.

1. Enregistrez-la et laissez le processus synchroniser entre l’Adobe Campaign et [!DNL Launch].

1. Une fois la synchronisation terminée, ouvrez la propriété mobile dans [!DNL Launch].

1. Définissez l’URL correcte dans l’extension d’Adobe Campaign Standard pour laquelle PKey a été réinitialisé.

1. Enregistrez-la et laissez le processus se synchroniser à nouveau.

1. Ce n’est qu’à ce moment que la propriété apparaîtra à l’état **[!UICONTROL Prêt à configurer]** dans l’Adobe Campaign et peut maintenant être configurée.

## Je souhaite configurer une propriété mobile dans Adobe Campaign. Dois-je attendre que le processus technique se synchronise entre Adobe Launch et Adobe Campaign ?

Vous pouvez exécuter immédiatement le processus :

1. Dans Adobe Campaign Standard, dans le menu avancé, sélectionnez **[!UICONTROL Administration]** > Paramètres **[!UICONTROL de l’]** application > **[!UICONTROL Workflows]**.

1. Ouvrez le processus **[!UICONTROL syncWithLaunch]** .

1. Cliquez sur l’activité **[!UICONTROL Planificateur]** et sélectionnez Exécution **** immédiate.
