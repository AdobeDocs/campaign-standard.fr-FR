---
title: Créer un service
description: Découvrez comment créer votre premier service et le configurer pour envoyer des emails de confirmation à vos abonnés.
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '448'
ht-degree: 100%

---


# Créer un service{#creating-a-service}

Pour pouvoir gérer les inscriptions, vous devez d&#39;abord créer un service et le configurer. La configuration d&#39;un nouveau service vous permet d&#39;indiquer les emails de confirmation que recevront les profils qui s&#39;abonnent au service ou s&#39;en désabonnent. Vous définirez également les landing pages d&#39;inscription et de désinscription associées au service. Par exemple, un lien d&#39;abonnement à un service inséré dans un email renverra automatiquement le profil vers la landing page d&#39;inscription spécifiée dans le service.

Pour configurer un service :

1. Depuis le menu avancé **[!UICONTROL Profils &amp; audiences]** > **[!UICONTROL Services]**, accessible via le logo Adobe Campaign, ajoutez un nouveau service ou sélectionnez le service existant de votre choix. Si vous créez un nouveau service, suivez simplement les étapes affichées à l&#39;écran.

   Un modèle de service est disponible par défaut. Ce modèle est pré-paramétré avec des landing pages et des emails de confirmation par défaut. Vous pouvez créer d&#39;autres modèles afin de spécifier des paramètres spécifiques. Voir à ce propos la section [Gestion des modèles](../../start/using/marketing-activity-templates.md).

1. Dans la section **[!UICONTROL Propriétés du service]**, accessible via le bouton ![](assets/edit_darkgrey-24px.png) du tableau de bord du service, paramétrez les messages de confirmation pour l&#39;inscription et la désinscription.

   ![](assets/lp_service_parameters.png)

1. Sélectionnez l’option **[!UICONTROL Abonnements limités dans le temps]** pour définir une durée de validité pour l’abonnement.

   ![](assets/lp_service_expiration.png)

   Vous pouvez utiliser la date d’expiration dans une activité de segmentation pour cibler les profils abonnés à un service qui n’a pas expiré.

1. Renseignez le champ **[!UICONTROL Libellé du service]**. Le libellé du service est obligatoire lorsque vous utilisez un message de confirmation personnalisé.

1. Sélectionnez un modèle de message de confirmation pour les inscriptions et désinscriptions. Trois modes sont disponibles :

   * **[!UICONTROL Aucun message]** : ce mode permet de créer un service sans message de confirmation.
   * **[!UICONTROL Message par défaut]** : ce mode utilisera le message transactionnel de confirmation d&#39;abonnement ou de désabonnement par défaut. Les messages de confirmation par défaut sont génériques et seront identiques pour l&#39;ensemble des services utilisant le mode par défaut.

      >[!NOTE]
      >
      >Vous pouvez modifier un message par défaut en cliquant sur son libellé dans la section **[!UICONTROL Propriétés du service]** ou en le sélectionnant dans la liste des messages transactionnels Adobe Campaign, après avoir coché la case **[!UICONTROL Afficher les messages transactionnels internes]**.

   * **[!UICONTROL Message personnalisé]** : ce mode vous permet de gérer des messages de confirmation personnalisés, spécifiques à chaque service. Vous pouvez ensuite sélectionner la **[!UICONTROL Configuration d&#39;événement d&#39;abonnement personnalisé]** qui est associée à un modèle de [message transactionnel](../../channels/using/getting-started-with-transactional-msg.md) spécifique. Pour plus d&#39;informations, voir [Confirmation de l&#39;abonnement à un service](../../audiences/using/confirming-subscription-to-a-service.md).

1. Enregistrez le service. Il est alors prêt à être utilisé.

Une fois qu&#39;un service a été créé, vous pouvez commencer à le promouvoir.

**Rubriques connexes :**

* Vidéo [Gérer un service et des inscriptions](https://docs.adobe.com/content/help/fr-FR/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/services-and-subscriptions.html)
* [Promouvoir un service](../../audiences/using/promoting-a-service.md)
* [Créer une audience composée d&#39;abonnés](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Associer une landing page à un service](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
