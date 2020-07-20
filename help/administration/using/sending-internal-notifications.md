---
title: Envoi de notifications internes
description: Découvrez comment envoyer des notifications système en temps réel à vos utilisateurs Adobe Campaign.
page-status-flag: never-activated
uuid: f196f025-dbb9-4268-9d7d-ff626994b447
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: 4d51229a-745a-4f24-b1c2-22fa203b499c
internal: n
snippet: y
translation-type: ht
source-git-commit: 422f5eb7011dfcc1d923079e7346394a64934a9a
workflow-type: ht
source-wordcount: '269'
ht-degree: 100%

---


# Envoi de notifications internes{#sending-internal-notifications}

Adobe Campaign vous permet de recevoir directement dans l&#39;application des notifications concernant des activités système importantes. Les notifications en temps réel maintiennent les parties concernées informées et permettent aux utilisateurs d&#39;agir immédiatement et directement dans l&#39;application en fonction des notifications d&#39;activité. Pour les équipes, il en résulte une meilleure agilité, une plus grande efficacité et une exécution des campagnes sans accrocs.

![](assets/pulse_3.png)

Vous pouvez configurer des notifications pour les objets suivants :

* **[!UICONTROL Emails de test A/B]** : le créateur de l&#39;email et la ou les personnes qui le modifient sont informés qu&#39;une variante a été sélectionnée (mode automatique) ou qu&#39;une variante doit être sélectionnée (mode manuel). Un clic sur la notification affiche l&#39;email correspondant. Les notifications sont activées par défaut dans le modèle d&#39;usine Test A/B. Si vous souhaitez les désactiver, éditez les propriétés de l&#39;email ou du modèle d&#39;email et décochez la case située sous **Général > Notifications**. Pour plus d&#39;informations sur les emails de test A/B, voir [Créer un test A/B](../../channels/using/designing-an-a-b-test-email.md). Pour plus d&#39;informations sur les propriétés d&#39;un email, voir [Liste des propriétés des emails](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]** : chaque membre du groupe de sécurité sélectionné est informé (par email et notification dans l&#39;application) en cas d&#39;erreur dans un workflow. Un clic sur la notification ou sur le lien de l&#39;email affiche le workflow correspondant. Les notifications sont désactivées par défaut dans le modèle d&#39;usine de workflow. Si vous souhaitez les activer, éditez les propriétés du workflow ou du modèle de workflow et ajoutez un groupe de sécurité sous **Général > Exécution > Gestion des erreurs > Superviseurs**. Pour plus d&#39;informations sur les groupes de sécurité, voir [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md). Pour plus d&#39;informations sur les propriétés d&#39;un workflow, voir [Propriétés d&#39;un workflow](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)
