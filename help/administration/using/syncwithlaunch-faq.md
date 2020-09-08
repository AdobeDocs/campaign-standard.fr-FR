---
title: FAQ sur le workflow technique de synchronisation avec Launch
description: Questions courantes à propos du workflow technique de Launch.
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
translation-type: ht
source-git-commit: 95a7397092f6e07c84967d90908469f630f7a170
workflow-type: ht
source-wordcount: '534'
ht-degree: 100%

---


# FAQ sur la synchronisation d’Adobe Launch {#syncwithlaunch-faq}

Vous pouvez importer les propriétés mobiles d’Adobe Launch dans Adobe Campaign Standard grâce au workflow technique dédié **[!UICONTROL Synchronisation avec Launch]**. Pour plus d’informations, consultez cette [page](../../administration/using/technical-workflows.md)

La section ci-dessous répertorie les questions courantes sur cette synchronisation.

>[!NOTE]
>
>Vous devrez envoyer une demande à l’Assistance client d’Adobe (directement ou par l’intermédiaire de votre contact Adobe) pour que le workflow technique **[!UICONTROL syncWithLaunch]** soit activé dans votre instance Campaign.

## J’ai créé une propriété dans [!DNL Launch] (non-administrateur ou entité organisationnelle ALL). Mon application est à l’état Ready to Configure dans Adobe Campaign, mais je ne peux pas l’ouvrir/la configurer. {#configuring-property}

Seul l’administrateur de l’entité organisationnelle ALL peut configurer des applications mobiles dans Adobe Campaign Standard. Une fois l’application configurée, seuls les utilisateurs de l’entité organisationnelle affectée peuvent la modifier. Pour plus d’informations sur les entités organisationnelles, consultez cette [page](../../administration/using/organizational-units.md).

## Je ne peux pas modifier une application mobile configurée dans Adobe Campaign Standard et les applications mobiles sont en mode lecture seule. {#read-mode-mobile-app}

Vérifiez l’entité organisationnelle de l’application mobile dans la section **[!UICONTROL Autorisation d’accès]**. Seuls les utilisateurs de l’entité organisationnelle affectée peuvent modifier l’application mobile.

Pour plus d’informations sur les entités organisationnelles, consultez cette [page](../../administration/using/organizational-units.md).

## Je suis un administrateur de l’entité organisationnelle ALL dans Adobe Campaign Standard mais je ne peux pas configurer d’application mobile. {#org-unit-mobile}

Un administrateur dont l’entité organisationnelle est définie sur ALL doit disposer de droits sur toutes les propriétés mobiles dans [!DNL Launch] pour configurer l’application mobile.

Pour plus d’informations sur les entités organisationnelles, consultez cette [page](../../administration/using/organizational-units.md).

## J’ai créé une propriété mobile dans [!DNL Launch] mais elle n’est pas visible dans Adobe Campaign Standard. {#visibility-mobile-property}

1. Vérifiez que l’extension Adobe Campaign Standard est installée dans la propriété mobile de [!DNL Launch].

1. Vérifiez que les points d’entrée de l’instance sont correctement configurés dans l’extension.

1. Vérifiez que les valeurs &#39;Launch_URL_Campaign&#39; ou &#39;NmsServer_URL&#39; sont correctes.

1. Ensuite, vérifiez que la synchronisation entre [!DNL Launch] et Adobe Campaign a été effectuée avec le workflow technique **[!UICONTROL syncWithLaunch]**.

## Comment vérifier si la synchronisation entre Adobe Campaign et Launch a été effectuée ? {#sync-campaign-launch}

1. Dans le menu avancé d’Adobe Campaign Standard, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l’application]** > **[!UICONTROL Workflows]**.

1. Ouvrez le workflow **[!UICONTROL syncWithLaunch]**.

1. Vérifiez si le workflow s’est terminé sans erreur.

1. Vérifiez dans les logs que la synchronisation du workflow est activée et qu’elle a été effectuée avec succès.

## J’ai réinitialisé la clé PKey pour une application mobile configurée dans Launch. Comment la reconfigurer dans Launch ? {#configuring-pkey}

1. Ouvrez la propriété mobile dans Adobe Launch.

1. Définissez une nouvelle URL dans l’extension Adobe Campaign Standard pour laquelle la clé PKey a été réinitialisée.

1. Enregistrez-la et attendez que la synchronisation entre Adobe Campaign et [!DNL Launch] soit effectuée.

1. Une fois la synchronisation effectuée, ouvrez la propriété mobile dans [!DNL Launch].

1. Définissez l’URL dans l’extension Adobe Campaign Standard pour laquelle la clé PKey a été réinitialisée.

1. Enregistrez-la et attendez que le workflow se synchronise à nouveau.

1. Ce n’est qu’à ce moment que la propriété apparaît dans l’état **[!UICONTROL Ready to Configure]** dans Adobe Campaign et peut ainsi être configurée.

## Je souhaite configurer une propriété mobile dans Adobe Campaign. Dois-je attendre que le workflow technique se synchronise entre Adobe Launch et Adobe Campaign ?

Vous pouvez exécuter immédiatement le workflow :

1. Dans le menu avancé d’Adobe Campaign Standard, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l’application]** > **[!UICONTROL Workflows]**.

1. Ouvrez le workflow **[!UICONTROL syncWithLaunch]**.

1. Cliquez sur l’activité **[!UICONTROL Planificateur]** et sélectionnez **[!UICONTROL Traitement anticipé]**.
