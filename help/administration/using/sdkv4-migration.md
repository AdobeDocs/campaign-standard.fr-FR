---
solution: Campaign Standard
product: campaign
title: Migration de l'application mobile SDK v4 vers le SDK Adobe Experience Platform
description: Ce document vous permet de migrer votre application mobile SDK v4 vers le SDK Adobe Experience Platform.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: ht
source-git-commit: 6c171d45d655e4055d4a3c7927f1dd8e0913eeaa
workflow-type: ht
source-wordcount: '1358'
ht-degree: 100%

---


# Comment migrer votre application mobile du SDK v4 vers le SDK Adobe Experience Platform {#sdkv4-migration}

>[!IMPORTANT]
>
> Le processus de migration est irréversible.
>
> Veuillez lire attentivement ce document avant de commencer la migration de votre application mobile SDK V4 vers le SDK Adobe Experience Platform.

## À propos de la migration du SDK V4

Adobe Campaign Standard traite les applications mobiles à l’aide du SDK V4 en tant qu’applications distinctes de celles qui utilisent le SDK Adobe Experience Platform.
Après la mise à niveau du SDK Adobe de la version v4 vers Adobe Experience Platform, les applications mobiles doivent continuer à utiliser les campagnes et données d’abonnés d’applications existantes. Une migration est donc nécessaire.

>[!NOTE]
>
> Cette page documente la migration d’une application mobile SDK v4 vers une nouvelle application SDK Adobe Experience Platform. Vos applications mobiles SDK v4 ne seront pas fusionnées avec une application mobile SDK Adobe Experience Platform dotée du **[!UICONTROL Statut de propriété]** **[!UICONTROL Configuré]**.

| Ce qui ne change pas après la migration |
|:-:|
| Il n’y a aucun effet sur les diffusions et campagnes existantes utilisant l’application SDK V4 migrée. |
| Le nom de l’application mobile reste identique. |
| Les informations d’identification de la plateforme pour iOS et Android sont conservées. |
| Tous les abonnés de l&#39;application et leurs données sont conservés. |
| L’application mobile SDK v4 existante continue à envoyer des données (données PII, informations d’abonné et de jeton) à Adobe Campaign Standard. |
| L&#39;**[!UICONTROL entité organisationnelle]** de l&#39;application mobile reste la même. |

| Ce qui change après la migration |
|:-:|
| L’application mobile est disponible dans **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Application mobile (SDK Adobe Experience Platform)]**. Avant la migration, elle était disponible dans **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Application mobile (SDK v4)]**. |
| Le **[!UICONTROL point d&#39;entrée pour la collecte des PII]** de l’application change. L&#39;ancien **[!UICONTROL point d&#39;entrée pour la collecte des PII]** continue de fonctionner. Les données envoyées ne sont donc pas perdues. |
| L&#39;application est liée à une **[!UICONTROL propriété mobile]** Adobe Experience Platform Launch. Elle est traitée en tant qu’application mobile nouvellement créée. |
| L’application SDK Adobe Experience Platform d’origine utilisée dans la migration n’existe pas en tant qu’application distincte. Seule l’application SDK v4 migrée est disponible. |

## Migration de votre application mobile du SDK v4 vers le SDK Adobe Experience Platform {#how-to-migrate}

Avant de procéder à la migration, tenez compte des recommandations suivantes :

* Le processus de migration est irréversible.
* Vous ne devez pas exécuter simultanément la migration de plusieurs applications. Vous devez également vous assurer que la migration d’une même application n’est pas déclenchée par plusieurs fenêtres en même temps.
* Avant la migration, assurez-vous d’avoir affecté l’**[!UICONTROL entité organisationnelle]** de l’application mobile à migrer et de l’application Adobe Experience Platform que vous utilisez pour la migration.
* Après la migration, l’application devient une application SDK Adobe Experience Platform. Ses modifications sont liées à son Launch correspondant **[!UICONTROL Propriété mobile]**.

1. Créez une **[!UICONTROL propriété Mobile]** dans Adobe Experience Platform Launch. Pour plus d&#39;informations à ce sujet, consultez la documentation d&#39;[Adobe Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property).

1. Dans Adobe Campaign Standard, dans le menu avancé, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramètres de l’application]** > **[!UICONTROL Workflows]** et ouvrez le workflow **[!UICONTROL syncWithLaunch]**. Vérifiez si le workflow s’est terminé sans erreur.

1. Une fois le processus terminé, dans le menu **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Application mobile (SDK Adobe Experience Platform)]**, vérifiez si l’application mobile est disponible dans Adobe Campaign Standard et si elle a le statut **[!UICONTROL Prêt pour configuration]**.

   ![](assets/aep_v4_2.png)

1. Dans **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Application mobile (SDK v4)]**, sélectionnez l’application SDK v4 à migrer.

1. Sélectionnez l&#39;onglet **[!UICONTROL Migration des applications mobiles vers le SDK AEP]**.

   ![](assets/aep_v4_3.png)

1. Dans la liste déroulante **[!UICONTROL Sélectionner l’application mobile SDK AEP avec laquelle fusionner l’application actuelle]**, sélectionnez l’application mobile SDK Adobe Experience Platform précédemment créée.

1. Cliquez sur **[!UICONTROL Migrer]**.

   ![](assets/aep_v4_4.png)

1. Dans la fenêtre **[!UICONTROL Application de migration]**, cliquez sur **[!UICONTROL OK]**.

   ![](assets/aep_v4_5.png)

1. La fenêtre d’achèvement réussi s’affiche, cliquez sur **[!UICONTROL Accéder à la liste du canal du SDK Adobe Experience Platform]**.

1. Dans la page de la liste des canaux du SDK Adobe Experience Platform, vérifiez que votre application mobile V4 précédente est définie sur **[!UICONTROL Prêt pour configuration]**.

1. Sélectionnez votre application mobile et cliquez sur **[!UICONTROL Enregistrer]** pour terminer la migration.

Après cette migration, les abonnés collectés par la version V4 de l’application mobile et les nouveaux abonnés collectés par la version AEP de l’application mobile seront disponibles dans l’application migrée.

Pour distinguer les deux types d&#39;abonnés, vous pouvez ajouter un nouveau champ personnalisé de type **[!UICONTROL Texte]** lors de l&#39;extension de la ressource personnalisée **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]** en tant que `sdkversion` ou `appVersion` par exemple. Pour plus d’informations sur l&#39;extension d&#39;une ressource personnalisée, consultez cette [page](../../developing/using/creating-or-extending-the-resource.md).
Vous devrez ensuite configurer la **[!UICONTROL Propriété mobile]** Launch associée pour envoyer cette valeur de champ personnalisé dans l’appel de collecte PII et modifier la configuration de votre application mobile en conséquence.

## FAQ {#faq}

### Q : Dans l’application mobile SDK v4, l’onglet Migration de l’application mobile vers le SDK Adobe Experience Platform n’est pas visible. {#tab-not-visible}

R : Dans le menu avancé **[!UICONTROL Administration]** > **[!UICONTROL Paramètres de l’application]** > **[!UICONTROL Options]**, vérifiez la valeur de l’option **[!UICONTROL Activer la migration de l’application mobile du SDK v4 vers le SDK Adobe Experience Platform]**. Il doit être défini sur 1 et activé par défaut. L’administrateur peut l’avoir désactivé manuellement.

![](assets/aep_v4_1.png)

### Q : Dans l’onglet Migration de l’application mobile vers l’onglet SDK Adobe Experience Platform, le message Aucune donnée s’affiche. {#no-data}

R : Seule l&#39;application éligible de votre **[!UICONTROL entité organisationnelle]** est indiquée dans la liste. Vérifiez que vous disposez de l&#39;application Adobe Experience Platform appropriée pour la migration. Le **[!UICONTROL Statut de propriété]** de votre application Adobe Experience Platform doit être **[!UICONTROL Prêt pour configuration]** et le **[!UICONTROL statut de migration de l&#39;application mobile]** défini sur **[!UICONTROL Non migré]**.

![](assets/aep_v4_6.png)

### Q : Pourquoi l’application SDK Adobe Experience Platform avec le statut de propriété Configuré ne peut-elle pas être utilisée pour la migration ? {#property-status}

R : Le processus de migration conserve les abonnés et les attributs du SDK v4. Il conserve uniquement les informations liées à Launch provenant de l’application SDK Adobe Experience Platform. Les abonnés et autres données provenant de l’application SDK Adobe Experience Platform sont perdus. Pour éviter toute perte de données, seules les applications SDK Adobe Experience Platform dotées du **[!UICONTROL statut de propriété]** **[!UICONTROL Prêt pour configuration]** peuvent être migrées.

### Q : Après la migration, où puis-je trouver mon ancienne application mobile SDK v4 ? {#v4-app-not-visible}

R : L’application mobile après la migration est visible à partir du menu avancé **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Application mobile (SDK Adobe Experience Platform)]**.

### Q : Après la migration, où puis-je trouver mon application SDK Adobe Experience Platform nouvellement créée ? {#aep-not-visible}

R : L’application SDK Adobe Experience Platform nouvellement créée utilisée pour la migration n’existe pas en tant qu’application distincte. Seule l’application SDK v4 migrée est disponible.

### Q : Si l’entité organisationnelle de l’application mobile SDK v4 est définie sur A (enfant de l’entité organisationnelle TOUS) et que le SDK Adobe Experience Platform est défini sur TOUS, comment puis-je migrer mon application mobile ? {#v4-org-unit}

R : Les administrateurs de l&#39;**[!UICONTROL entité organisationnelle]** TOUS disposent des droits pour gérer les deux applications mobiles et sont chargés de la migration.

### Q : Si l’entité organisationnelle de l’application mobile SDK v4 est définie sur A et que l’application SDK Adobe Experience Platform est définie sur B (sœur de l’unité organisationnelle A), comment puis-je migrer mon application mobile ? {#aep-org-unit}

R : L’application Adobe Experience Platform SDK étant la ressource d’une **[!UICONTROL entité organisationnelle]** sœur, l’application mobile n&#39;est pas visible pour les utilisateurs de l’**[!UICONTROL entité organisationnelle]** A. L’application mobile est disponible pour les administrateurs de l’**[!UICONTROL entité organisationnelle]** TOUS, mais nous ne recommandons pas à ces administrateurs de migrer l’application mobile.
Dans ce cas, vous devez déplacer vos applications mobiles dans la même **[!UICONTROL entité organisationnelle]** ou dans une **[!UICONTROL entité organisationnelle]** avec un lien parent.
Pour plus d&#39;informations sur les **[!UICONTROL entités organisationnelles]**, veuillez consulter cette [section](../../administration/using/organizational-units.md).

### Q : Dans la page Application mobile SDK Adobe Experience Platform (migrée depuis votre application mobile v4), sous la liste déroulante des paramètres du canal push, aucune information telle que la date/le nom associés au téléchargement n’est affichée pour la clé Android ou le certificat iOS {#no-information-v5}

R : Le système ne stocke pas ces informations lorsque l’application mobile SDK V4 est créée. Lors de la migration de votre application mobile SDK V4 vers une application mobile Adobe Experience Platform SDK, votre application mobile migrée ne dispose pas non plus de ce type d’information. Dès qu’un utilisateur télécharge un nouveau certificat iOS ou une nouvelle clé Android, les différents détails de la clé ou du certificat sont stockés et affichés correctement sous la liste déroulante **[!UICONTROL Paramètres du canal push]**.
