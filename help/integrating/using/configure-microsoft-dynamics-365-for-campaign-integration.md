---
title: Configuration de Microsoft Dynamics 365 pour Campaign intégration
description: Découvrez comment configurer Microsoft Dynamics 365 pour Campaign intégration.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e05dafb087c43a13c60d6bb2f54d0e44455ea8d

---


# Configuration de Microsoft Dynamics 365 pour Campaign intégration

Découvrez comment configurer l&#39;intégration de Microsoft Dynamics 365 et activer vos données de gestion de la relation client lors d&#39;une communication entre avec   Standard.

## Présentation

 Adobe Campaign Standard - L&#39;intégration de Microsoft Dynamics 365 est décrite dans [cette page](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Trois systèmes doivent être configurés pour cette intégration :

1.  Adobe Campaign Standard - [En savoir plus](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 pour les ventes - Décrit ci-dessous
1. Unifi - [En savoir plus](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)

Une fois configurés, ces systèmes doivent être configurés par un administrateur.

Cet article décrit les étapes, côté Microsoft Dynamics 365, requises lors de la post-mise en service pour permettre à un client d&#39;utiliser l&#39;intégration  Adobe Campaign Standard - Microsoft Dynamics 365.

## Prérequis

Avant d’exécuter les étapes de post-mise en service dans ce  de, on suppose que vous avez déjà configuré et que vous disposez d’un accès administrateur à l’instance Microsoft Dynamics 365 de votre entreprise.  Si cela ne s&#39;est pas produit, vous devrez contacter le service clientèle de Microsoft pour terminer l&#39;approvisionnement de Dynamics 365.

## Configuration de l’application et des autorisations

Un OAuth permet à Unifi de s&#39;authentifier auprès de votre instance Microsoft Dynamics 365 par le biais d&#39;API Web afin de publier Campaign Standard ducontenu de l&#39; de la chronologie de l&#39;interface Microsoft Dynamics 365.

Les principales étapes sont décrites dans la vidéo suivante :

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Pour générer le  OAuth, suivez les étapes décrites ci-dessous.

### Enregistrement d’une nouvelle application

1. Sous votre connexion administrateur, connectez-vous à portal.azure.com.

1. Cliquez sur **[!UICONTROL Azure Active Directory]** dans le menu de gauche ; cliquez ensuite **[!UICONTROL App registrations]** sur le sous-menu qui s&#39;affiche.

1. Cliquez **[!UICONTROL New registration]** en haut de l’écran.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Renseignez l’écran d’enregistrement de l’application :

   * Nom : adobe campaign
   * Type de compte pris en charge : **[!UICONTROL Accounts in this organizational directory only]** (valeur par défaut)

Pour plus d&#39;informations sur la création d&#39;une application, reportez-vous à [cette section](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Azure AD affecte un ID d&#39;application (client) unique à votre application. Vous aurez besoin de cet ID plus tard dans la configuration de Dynamics 365, ainsi que lorsque vous effectuerez les étapes de mise en service de publication Unifi.

### Générer le secret client

1. Dans l’écran de présentation de l’application, dans le sous-menu de gauche, cliquez sur **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Entrez une description, définissez la durée et cliquez sur **[!UICONTROL OK]**.

Votre secret client est maintenant créé.  Conservez la valeur pour terminer les étapes de post-mise en service Unifi.

>[!CAUTION]
>
>Conservez cette valeur, car vous en aurez besoin pour terminer l’étape de post-mise en service Unifi. Il ne peut pas être récupéré par la suite.

Pour plus d’informations sur la génération d’un secret client, reportez-vous à cette section.

### Configuration des autorisations

1. Dans cet écran ou dans l’écran de présentation de l’application, cliquez sur **[!UICONTROL API permissions]** dans le sous-menu de gauche.  Après avoir cliqué **[!UICONTROL Add a permission]**, vous devez sélectionner **[!UICONTROL Dynamics CRM]** dans le menu.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Cochez ensuite la case **[!UICONTROL user_impersonation]**, puis cliquez sur le **[!UICONTROL Add permissions]** bouton.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Pour plus d&#39;informations sur la configuration des autorisations, reportez-vous à [cette section](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Création de l’utilisateur de l’application

Ce nouvel utilisateur est un utilisateur générique. Elle sera utilisée par l’application : toute modification apportée à Microsoft Dynamics 365 à l&#39;aide de l&#39;API sera effectuée par cet utilisateur. Pour le créer, procédez comme suit :

1. Accédez à votre instance Dynamics 365 et connectez-vous en tant qu’administrateur.

1. Cliquez sur l&#39;icône en forme d&#39;engrenage dans le coin supérieur droit et cliquez sur **[!UICONTROL Advanced Settings]**. Dans la bannière supérieure, cliquez sur la liste déroulante en regard de **[!UICONTROL Settings]**, cliquez sur **[!UICONTROL Security > Users]**.

1. Cliquez sur le menu déroulant pour accéder à **[!UICONTROL Application Users]**. Clics **[!UICONTROL New]**.

1. Vérifiez que le menu déroulant en regard de l’icône utilisateur indique **[!UICONTROL USER:APPLICATION USER]**.

   Renseignez l’écran du nouvel utilisateur.  Suggestions de paramètres :

   * **[!UICONTROL User Name]** (adresse électronique) : adobeapi@`<hostname>`, où `<hostname>` est le nom d&#39;hôte de votre instance Dynamics 365
   * **[!UICONTROL Application ID]**: ID de l&#39;application que vous avez enregistrée dans Azure AD (obligatoire)
   * Vous pouvez laisser vide **[!UICONTROL Application ID URI]** et **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API Adobe
   * **[!UICONTROL Email]**: identique à **[!UICONTROL User Name]** (ou à l’adresse électronique de l’administrateur si vous le souhaitez)
   Pour plus d’informations sur la création d’utilisateurs d’applications, reportez-vous à [cette section](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Cliquez sur l’icône de l’utilisateur et téléchargez une icône  Adobe Campaign ; il s’agit de l’icône qui s’affichera dans le de chronologie lorsque de nouveaux Adobe apparaissent dans Dynamics 365.

<!-- ***getfile*** adobe campaign logo-->

1. Ouvrez le des rôles utilisateur en cliquant **[!UICONTROL MANAGE ROLES]** sur dans le ruban supérieur.

1. Faites défiler l’écran vers le bas et sélectionnez **[!UICONTROL System administrator]** l’accès pour cet utilisateur.

1. Clics **[!UICONTROL OK]**.

### Obtention de l’ID de client

Suivez les instructions du lien suivant pour trouver votre ID de client.  Vous aurez besoin de cet ID lors de la post-mise en service dans Unifi : [https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id).

## Installation Campaign Standard pour Microsoft Dynamics 365

Pour intégrer l&#39;application Dynamics 365 à votre Campaign Standard , suivez les étapes ci-dessous :

1. Accédez au lien suivant : [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) et recherchez _Adobe Campaign pour Dynamics 365_ dans la barre de recherche.
Vous pouvez également accéder à ce [lien](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Suivez les instructions pour installer l&#39;application pour votre instance Dynamics 365.
1. Une fois installé, accédez à votre instance Dynamics 365 et connectez-vous en tant qu’administrateur.
1. Cliquez sur l&#39;icône en forme d&#39;engrenage dans le coin supérieur droit et cliquez sur **[!UICONTROL Advanced Settings]**. Dans la bannière supérieure, cliquez sur le menu déroulant en regard de **[!UICONTROL Settings]**, cliquez **[!UICONTROL Processes]** sous **[!UICONTROL Process Center]**.
1. Recherchez **[!UICONTROL Adobe Campaign Email Bounce]** et cliquez dessus.
1. Sur l’ **[!UICONTROL Administration]** onglet, remplacez le propriétaire par l’utilisateur de l’application API Adobe créé précédemment en cliquant **[!UICONTROL Actions]** sur dans le ruban supérieur, puis sélectionnez **[!UICONTROL Assign to another User]** l’option, sélectionnez **[!UICONTROL Adobe API application user]** dans la liste déroulante à affecter.
1. Réactivez le processus.
1. Faites de même pour le **[!UICONTROL Adobe Campaign Email Click]** .

>[!NOTE]
>
>Si vous souhaitez désactiver ces processus à tout moment, vous pouvez le faire dans cet **[!UICONTROL Processes]** écran.

Une fois cette configuration terminée, vous pouvez configurer la configuration Unifi. Pour plus d’informations à ce propos, consultez cette [page](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

**Rubriques connexes :**

* [Campaign Standard - Intégration de Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configuration de l’intégration d’Adobe IO pour Microsoft Dynamics 365](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Configuration d&#39;Unifi pour Campaign - Intégration de Microsoft Dynamics 365](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)
