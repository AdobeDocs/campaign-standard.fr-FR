---
solution: Campaign Standard
product: campaign
title: Configuration de Microsoft Dynamics 365 pour l’intégration de Campaign
description: Découvrez comment configurer Microsoft Dynamics 365 pour l’intégration de Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 3ba3e0db816832ea57c124a9bea1fa82cf068859
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 88%

---


# Configuration de Microsoft Dynamics 365 pour l&#39;intégration à Adobe Campaign Standard

Découvrez comment configurer l’intégration de Microsoft Dynamics 365 et activer vos données CRM lors d’une communication cross-canal avec Adobe Campaign Standard.

## Présentation

La description générale de l&#39;intégration Adobe Campaign Standard avec Microsoft Dynamics 365 est décrite dans [cette page](../../integrating/using/d365-acs-get-started.md).

Plusieurs applications devront être configurées pour activer l&#39;intégration. Cependant, cet article se concentrera sur les étapes requises dans Dynamics 365.

## Conditions préalables requises

Avant d’exécuter les étapes de configuration préalable à l’intégration décrites dans ce document, vous devez avoir déjà configuré l’instance Microsoft Dynamics 365 de votre entreprise et disposer d’un accès administrateur.  Si ce n’est pas le cas, vous devrez contacter le service clientèle de Microsoft pour terminer la mise en service de Dynamics 365.

Si vous configurez l’intégration pour les environnements d’évaluation et de production, vous devez exécuter les étapes ci-dessous pour vos instances d’évaluation et de production Dynamics 365. Quelques instructions ci-dessous varient légèrement selon que vous configurez une instance d’évaluation ou de production Dynamics 365 (par exemple, pour l’instance de production, sélectionnez « prod » pour `<stage or prod>`).

## Configuration de l’application et des autorisations

Un jeton d‘accès OAuth permet à l’outil d’intégration de s’authentifier auprès de votre instance Microsoft Dynamics 365 par le biais des API Web afin de publier les événements d’expérience Campaign Standard sur la vue de calendrier de l’interface de Microsoft Dynamics 365.

Les principales étapes sont décrites dans la vidéo suivante :

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Pour générer le jeton d’accès OAuth, suivez les étapes décrites ci-dessous.

### Enregistrement d’une nouvelle application {#register-a-new-app}

1. Avec votre identifiant d’administrateur, connectez-vous à portal.azure.com.

1. Cliquez sur **[!UICONTROL Azure Active Directory]** dans le menu de gauche, puis sur **[!UICONTROL Inscriptions des applications]** dans le sous-menu qui s’affiche.

1. Cliquez sur **[!UICONTROL Nouvelle inscription]** dans la partie supérieure de l’écran.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Renseignez les champs de l’écran d’inscription de l’application :

   * Nom : adobe campaign     `<stage or prod>`
   * Type de compte pris en charge : **[!UICONTROL Comptes dans cet annuaire organisationnel uniquement]** (valeur par défaut)

Pour plus d’informations sur la création d’une application, reportez-vous à [cette section](https://docs.microsoft.com/fr-fr/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Microsoft Azure Directory affecte un ID d&#39;application (client) unique à votre application. Vous aurez besoin de cet ID plus tard dans la configuration de Dynamics 365, ainsi que lorsque vous effectuerez la configuration de l&#39;outil d&#39;intégration.

### Génération du secret client {#generate-a-client-secret}

1. Dans l’écran de présentation de l’application, dans le sous-menu de gauche, cliquez sur **[!UICONTROL Certificats et secrets > Nouveau secret client]**.

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Entrez une description, définissez la durée et cliquez sur **[!UICONTROL OK]**.

Votre secret client est maintenant créé. Conservez temporairement la valeur pour effectuer la configuration préalable à l’intégration de l’outil d’intégration.

>[!CAUTION]
>
>Conservez cette valeur, car vous en aurez besoin pour effectuer la configuration préalable à l’intégration de l’outil d’intégration. Celle-ci ne peut pas être récupérée par la suite.


### Configuration des autorisations

1. Dans cet écran ou l’écran de présentation de l’application, cliquez sur **[!UICONTROL Autorisations de l’API]** dans le sous-menu de gauche.  Après avoir cliqué sur **[!UICONTROL Ajouter une autorisation]**, vous devez sélectionner **[!UICONTROL Dynamics CRM]** dans le menu.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Cochez ensuite la case correspondant à **[!UICONTROL user_impersonation]**, puis cliquez sur le bouton **[!UICONTROL Ajouter des autorisations]**.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Pour plus d&#39;informations sur la configuration des autorisations, reportez-vous à [cette section](https://docs.microsoft.com/fr-fr/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Création de l’utilisateur de l’application

Ce nouvel utilisateur est un utilisateur générique. Il sera utilisé par l’application : toute modification apportée à Microsoft Dynamics 365 à l’aide de l’API sera effectuée par cet utilisateur. Pour le créer, procédez comme suit :

1. Accédez à votre instance Dynamics 365 et connectez-vous en tant qu’administrateur.

1. Cliquez sur l’icône en forme d’engrenage dans le coin supérieur droit, puis sur **[!UICONTROL Paramètres avancés]**. Dans la bannière supérieure, cliquez sur la liste déroulante en regard de **[!UICONTROL Paramètres]**, puis sur **[!UICONTROL Sécurité > Utilisateurs]**.

1. Cliquez sur le menu déroulant pour accéder à **[!UICONTROL Utilisateurs de l’application]**. Cliquez sur **[!UICONTROL Nouveau]**.

1. Vérifiez que le menu déroulant en regard de l’icône utilisateur indique **[!UICONTROL UTILISATEUR : UTILISATEUR DE L’APPLICATION]**.

   Renseignez l’écran du nouvel utilisateur.  Suggestions de paramètres :

   * **[!UICONTROL Nom d’utilisateur]** (email) : adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (par exemple, adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL ID d’application]** : ID de l’application que vous avez inscrite dans Azure AD (obligatoire)
   * Vous pouvez laisser les champs suivants vides : **[!UICONTROL URI de l’ID d’application]** et **[!UICONTROL ID d’objet Azure AD]**
   * **[!UICONTROL Nom complet]** : API Adobe     `<stage or prod>`
   * **[!UICONTROL E-mail]** : identique au **[!UICONTROL nom d’utilisateur]** (ou adresse e-mail de l’administrateur si vous le souhaitez)

   Pour plus d’informations sur la création d’un utilisateur d’application, reportez-vous à [cette section](https://docs.microsoft.com/fr-fr/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Cliquez sur l’icône de l’utilisateur et téléchargez une icône Adobe Campaign ; il s’agit de l’icône qui s’affiche dans la vue de calendrier lorsque de nouveaux événements Adobe apparaissent dans Dynamics 365.

1. Ouvrez la liste des rôles utilisateur en cliquant sur **[!UICONTROL GÉRER LES RÔLES]** dans le ruban supérieur.

1. Faites défiler l’écran vers le bas et sélectionnez **[!UICONTROL Administrateur système]** pour cet utilisateur.

1. Cliquez sur le bouton **[!UICONTROL OK]**.

### Obtention de l’identifiant du tenant  {#get-the-tenant-id}

Suivez les instructions [de cette page](https://docs.microsoft.com/fr-fr/onedrive/find-your-office-365-tenant-id) pour trouver votre identifiant de tenant.  Vous aurez besoin de cet identifiant lors de la configuration préalable à l’intégration dans l’outil d’intégration.

## Installation de Campaign Standard pour Microsoft Dynamics 365 {#install-appsource-app}

Pour intégrer l’application Dynamics 365 à votre environnement Campaign Standard, procédez comme suit :

1. Accédez au lien suivant : [https://appsource.microsoft.com/fr-fr/marketplace/apps](https://appsource.microsoft.com/fr-fr/marketplace/apps) et recherchez _Adobe Campaign pour Dynamics 365_ dans la barre de recherche.
Vous pouvez également accéder à ce [lien](https://appsource.microsoft.com/fr-fr/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Suivez les instructions pour installer l’application pour votre instance Dynamics 365.
1. Une fois installée, accédez à votre instance Dynamics 365 et connectez-vous en tant qu’administrateur.
1. Cliquez sur l’icône en forme d’engrenage dans le coin supérieur droit, puis sur **[!UICONTROL Paramètres avancés]**. Dans la bannière supérieure, cliquez sur la liste déroulante en regard de **[!UICONTROL Paramètres]**, puis sur **[!UICONTROL Traitements]** sous **[!UICONTROL Centre de traitement]**.
1. Recherchez la tâche **[!UICONTROL Email bounce Adobe Campaign]** et cliquez dessus.
1. Dans l’onglet **[!UICONTROL Administration]**, remplacez le propriétaire par l’utilisateur de l’application API Adobe créé précédemment en cliquant sur **[!UICONTROL Actions]** dans le ruban supérieur, puis sélectionnez **[!UICONTROL Attribuer à un autre utilisateur]** et **[!UICONTROL Utilisateur de l’application API Adobe]** dans la liste déroulante.
1. Réactivez le traitement.
1. Faites de même pour la tâche **[!UICONTROL Clic email Adobe Campaign]**.

>[!NOTE]
>
>Si vous souhaitez désactiver ces traitements, vous pouvez le faire à tout moment dans cet écran **[!UICONTROL Traitements]**.

**Rubriques connexes :**

* [Configurer l&#39;](../../integrating/using/d365-acs-configure-adobe-io.md) intégration des E/S Adobe pour Microsoft Dynamics 365 est l&#39;étape suivante de la configuration de l&#39;intégration
* [Commencez avec l’](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) application d’intégration en libre-service et suivez la liste complète des étapes nécessaires pour que l’intégration soit opérationnelle.