---
title: Obtenir l'accès à l'intégration Adobe Campaign Standard avec l'application en libre-service Dynamics 365
description: Intégration d'Adobe Campaign Standard avec l'application en libre-service Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---


# Accès à l&#39;intégration Adobe Campaign Standard avec l&#39;application en libre-service Microsoft Dynamics 365

Cette configuration nécessite que vous travailliez avec un administrateur Experience Cloud (EC) pour votre entreprise. Il s’agit des étapes initiales nécessaires pour vous donner accès à l’interface de l’application d’intégration en libre-service. Une fois que vous avez accès à l&#39;outil, vous allez configurer des connexions à vos données et configurer le flux de données entre Adobe Campaign et Microsoft Dynamics 365.

>[!NOTE]
>
>Vous devez contacter votre représentant Adobe et fournir l&#39;organisation Adobe Campaign Standard et les noms d&#39;instances. Un ticket sera consigné afin de demander que l’application d’intégration soit activée pour votre organisation.

## Ajouter un profil de produit

Dans cette section, vous apprendrez comment accorder l&#39;accès à l&#39;intégration Adobe Campaign Standard avec l&#39;application en libre-service Microsoft Dynamics 365. Les utilisateurs qui ont accès à votre organisation dans Adobe Experience Cloud n’auront pas accès à l’application en libre-service d’intégration, sauf si vous suivez les étapes ci-dessous pour leur accorder l’accès.

>[!IMPORTANT]
>
> Ces étapes nécessitent un rôle **Administrateur** dans l&#39;Experience Cloud de votre organisation.


1. Accédez à https://experience.adobe.com/ et connectez-vous au Adobe Experience Cloud.
1. Accédez au **Admin Console**.

   ![](assets/d365-to-acs-access-3.png)

1. Cliquez sur **[!UICONTROL Produits]** pour accéder à vos solutions Experience Cloud.

   ![](assets/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >Les étapes restantes de cette section seront effectuées pour chacune de vos instances Campaign (développement, texte, production).

1. Cliquez sur la première instance à configurer.

   ![](assets/d365-to-acs-access-6.png)

   La page d’instance doit se présenter comme suit :

   ![](assets/d365-to-acs-access-8.png)

1. Cliquez sur le bouton **[!UICONTROL Nouveau Profil]** et ajoutez une nouvelle entrée nommée : **Campaign Standard - votre-nom-instance-prod - Intégration D365/ACS**

   * Si vous voyez cette entrée dans la liste, vous n&#39;avez pas besoin de continuer. Cliquez sur **Adobe Campaign Standard** dans le menu de gauche et vérifiez les autres instances Campaign.

   * Veillez à remplacer &quot;votre-prod-instance-name&quot; par le nom réel de votre instance.

1. Vous pouvez laisser la liste déroulante **[!UICONTROL Groupe d’autorisations]** avec la valeur par défaut.

1. Si vos entrées se présentent comme suit, cliquez sur le bouton **[!UICONTROL Terminé]**.

   ![](assets/d365-to-acs-access-14.png)

   Le nouveau profil de produits a été ajouté.

   ![](assets/d365-to-acs-access-15.png)

## Accorder l&#39;accès aux utilisateurs {#add-users-to-profile}

Dans la page **[!UICONTROL Produits]**, sélectionnez votre instance Campaign et procédez comme suit :

1. Cliquez sur le nouveau profil que vous avez créé précédemment :  **Campaign Standard - votre-nom-instance-prod - Intégration D365/ACS**

   ![](assets/d365-to-acs-access-15.png)

1. Cliquez sur l&#39;onglet **[!UICONTROL Developers]**.

   ![](assets/d365-to-acs-access-18.png)

1. Cliquez sur le bouton **[!UICONTROL Ajouter le développeur]**.

1. Entrez le nom ou l&#39;adresse électronique de l&#39;utilisateur à ajouter.  Sélectionnez le résultat correspondant à l’utilisateur.

   Si c’est la première fois que l’utilisateur est ajouté à l’organisation, entrez des détails.

1. Cliquez sur **[!UICONTROL Enregistrer]** pour valider.
