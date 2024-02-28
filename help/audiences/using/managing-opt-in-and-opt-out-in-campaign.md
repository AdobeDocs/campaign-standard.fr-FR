---
title: Gestion des processus d'opt-in et d’opt-out dans Campaign
description: Découvrez la gestion des processus d'opt-in et d’opt-out dans Adobe Campaign
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: ht
source-wordcount: '329'
ht-degree: 100%

---

# Gestion des processus d&#39;opt-in et d&#39;opt-out dans Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Gestion des processus d&#39;opt-in et d’opt-out d&#39;un profil {#managing-opt-in-and-opt-out-from-a-profile}

Les utilisateurs peuvent être inscrits ou désinscrits par un opérateur, directement depuis l&#39;onglet **[!UICONTROL Général]** du profil.

Dans la section **[!UICONTROL Ne plus contacter (sur liste bloquée)]**, les cases à cocher sélectionnées correspondent aux canaux pour lesquels l’utilisateur ou l’utilisatrice a marqué son opt-out. Sélectionnez les canaux en fonction des besoins de l&#39;utilisateur.

![](assets/optin_landingpage_3.png)

## Configuration des landing pages d&#39;opt-in et d’opt-out      {#setting-up-opt-in-and-opt-out-landing-pages}

Pour que les utilisateurs et utilisatrices puissent donner leur opt-in ou opt-out, vous devez créer et publier une page de destination **[!UICONTROL Acquisition de profils]**. Ils seront ensuite en mesure de choisir les canaux en fonction de leurs besoins. Pour ce faire, suivez les étapes ci-après.

Vous pouvez également configurer une page de destination **[!UICONTROL Liste bloquée]**, qui permettra aux utilisateurs et utilisatrices de donner leur opt-out pour toutes les diffusions. Pour plus d&#39;informations, consultez [Configuration d&#39;une page de destination pour l’opt-out de toutes les diffusions](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Les landing pages peuvent également être utilisées pour activer l&#39;inscription aux services. Voir à ce propos [cette page](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Créez une landing page **[!UICONTROL Acquisition de profils]** (consulter [cette section](../../channels/using/getting-started-with-landing-pages.md)).
1. Ajoutez une case à cocher au contenu de la landing page pour chaque canal souhaité, et reliez-la au champ correspondant de la base de données de Campaign.

   ![](assets/optin_landingpage_1.png)

1. Enregistrez la landing page et publiez-la.
1. Dans la landing page, les cases à cocher sont déjà sélectionnées en fonction de l&#39;onglet **[!UICONTROL Général]** du profil. L’utilisateur peut sélectionner ou désélectionner les canaux en fonction de ses besoins et envoyer le formulaire.

   ![](assets/optin_landingpage_2.png)

1. Une fois le formulaire envoyé, l’onglet **[!UICONTROL Général]** du profil est mis à jour en fonction de la sélection de l’utilisateur.

   ![](assets/optin_landingpage_3.png)

### Configuration d&#39;une page de destination pour l’opt-out de toutes les diffusions {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Pour que les utilisateurs et utilisatrices puissent donner leur opt-in ou opt-out, vous devez créer et publier une page de destination **[!UICONTROL Liste bloquée]**. Pour plus d&#39;informations sur la création de landing pages, consultez [cette page](../../channels/using/getting-started-with-landing-pages.md).

Lorsqu&#39;un utilisateur clique sur le lien de la landing page, l&#39;option **[!UICONTROL Ne plus contacter (tous canaux)]** du profil est automatiquement sélectionnée.

![](assets/blocklisting_allchannels.png)
