---
title: FAQ sur le workflow technique de synchronisation avec Launch
description: Questions courantes à propos du workflow technique d’Adobe Launch
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: ht
source-wordcount: '519'
ht-degree: 100%

---

# FAQ sur les balises dans la synchronisation Adobe Experience Platform {#syncwithlaunch-faq}

Vous pouvez importer les propriétés mobiles de balise dans Adobe Campaign Standard grâce au workflow technique dédié **[!UICONTROL Synchronisation avec Launch]**. Pour plus d’informations, consultez cette [page](../../administration/using/technical-workflows.md)

La section ci-dessous répertorie les questions courantes sur cette synchronisation.

## J’ai créé une propriété dans de balise (non-administrateur ou entité organisationnelle ALL). Mon application est à l’état Prêt pour configuration dans Adobe Campaign, mais je ne peux pas l’ouvrir/la configurer. {#configuring-property}

Seul l’administrateur de l’entité organisationnelle ALL peut configurer des applications mobiles dans Adobe Campaign Standard. Une fois l’application configurée, seuls les utilisateurs de l’entité organisationnelle affectée peuvent la modifier. Pour plus d’informations sur les entités organisationnelles, consultez cette [page](../../administration/using/organizational-units.md).

## Je ne peux pas modifier une application mobile configurée dans Adobe Campaign Standard et les applications mobiles sont en mode lecture seule. {#read-mode-mobile-app}

Vérifiez l’entité organisationnelle de l’application mobile dans la section **[!UICONTROL Autorisation d’accès]**. Seuls les utilisateurs de l’entité organisationnelle affectée peuvent modifier l’application mobile.

Pour plus d’informations sur les entités organisationnelles, consultez cette [page](../../administration/using/organizational-units.md).

## Je suis un administrateur de l’entité organisationnelle ALL dans Adobe Campaign Standard mais je ne peux pas configurer d’application mobile. {#org-unit-mobile}

Un administrateur dont l’entité organisationnelle est définie sur ALL doit disposer de droits sur toutes les propriétés mobiles de balise pour configurer l’application balise mobile.

Pour plus d’informations sur les entités organisationnelles, consultez cette [page](../../administration/using/organizational-units.md).

## J’ai créé une propriété de balise mobile mais elle n’est pas visible dans Adobe Campaign Standard. {#visibility-mobile-property}

1. Vérifiez que l’extension Adobe Campaign Standard est installée dans la propriété mobile de l’interface utilisateur de collecte de données.

1. Vérifiez que les points d’entrée de l’instance sont correctement configurés dans l’extension.

1. Vérifiez que les valeurs &#39;Launch_URL_Campaign&#39; ou &#39;NmsServer_URL&#39; sont correctes.

1. Ensuite, vérifiez que la synchronisation a été effectuée avec le workflow technique **[!UICONTROL syncWithLaunch]**.

## Comment vérifier si la synchronisation entre Adobe Campaign et les balises dans Adobe Experience Platform a été effectuée ? {#sync-campaign-launch}

1. Dans le menu avancé d’Adobe Campaign Standard, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l’application]** > **[!UICONTROL Workflows]**.

1. Ouvrez le workflow **[!UICONTROL syncWithLaunch]**.

1. Vérifiez si le workflow s’est terminé sans erreur.

1. Vérifiez dans les logs que la synchronisation du workflow est activée et qu’elle a été effectuée avec succès.

## J’ai réinitialisé la PKey pour une application mobile de balise configurée. Comment reconfigurer la PKey dans l’interface utilisateur de collecte de données ? {#configuring-pkey}

1. Ouvrez la propriété mobile dans l’interface utilisateur de collecte de données.

1. Définissez une nouvelle URL dans l’extension Adobe Campaign Standard pour laquelle la clé PKey a été réinitialisée.

1. Enregistrez-la et attendez que le workflow se synchronise.

1. Une fois la synchronisation terminée, ouvrez la propriété mobile dans l’interface utilisateur de collecte de données.

1. Définissez l’URL dans l’extension Adobe Campaign Standard pour laquelle la clé PKey a été réinitialisée.

1. Enregistrez-la et attendez que le workflow se synchronise à nouveau.

1. Ce n’est qu’à ce moment que la propriété apparaît dans l’état **[!UICONTROL Ready to Configure]** dans Adobe Campaign et peut ainsi être configurée.

## Je souhaite configurer une propriété mobile dans Adobe Campaign. Dois-je attendre que le workflow technique se synchronise entre les balises dans Adobe Experience Platform et Adobe Campaign ?

Vous pouvez exécuter immédiatement le workflow :

1. Dans le menu avancé d’Adobe Campaign Standard, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l’application]** > **[!UICONTROL Workflows]**.

1. Ouvrez le workflow **[!UICONTROL syncWithLaunch]**.

1. Cliquez sur l’activité **[!UICONTROL Planificateur]** et sélectionnez **[!UICONTROL Traitement anticipé]**.
