---
title: Création et mise à jour des informations de profil en fonction des données d'application mobile
description: Découvrez comment créer et mettre à jour les informations de profil en fonction des données d'application mobile.
page-status-flag: never-activated
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '1090'
ht-degree: 100%

---


# Création et mise à jour des informations de profil en fonction des données d&#39;application mobile

## Présentation

Cette page décrit les étapes d&#39;élaboration d&#39;un workflow qui crée/met à jour les données de profil après l&#39;envoi par une application mobile de données de collecte de PII, selon une planification.

* Les **PII** (Personally Identifiable Information) sont des données personnelles. Il peut s&#39;agir de n&#39;importe quelles données, notamment d&#39;informations qui n&#39;apparaissent pas dans la table des profils de la base de données Campaign (par exemple, les [points ciblés](../../integrating/using/about-campaign-points-of-interest-data-integration.md) Analytics pour les applications mobiles). Les données de PII sont définies par le développeur d&#39;applications mobiles, généralement avec un marketeur.
* La **collecte des PII** est une opération HTTP-POST vers une API REST dans Adobe Campaign Standard à partir d&#39;une application mobile.

L&#39;objectif de ce cas pratique est de créer ou de mettre à jour un profil Campaign Standard si les données de PII renvoyées par une application mobile contiennent des données liées au profil.

## Prérequis

Avant que les profils puissent être créés ou mis à jour en fonction des données d&#39;abonnement aux applications mobiles, vous devez suivre plusieurs étapes de configuration pour activer les notifications push dans Campaign Standard :

1. [Créer une application mobile](../../administration/using/configuring-a-mobile-application.md)
1. [Intégrer le SDK Adobe Mobile avec votre application mobile](https://helpx.adobe.com/fr/campaign/kb/integrate-mobile-sdk.html).
1. [Configurer Adobe Campaign pour envoyer des notifications push](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html).

## Etape 1 - Etendre la ressource Profil pour les notifications push/abonnements

Pour pouvoir créer ou mettre à jour la ressource Profil avec des données de PII, vous devez d&#39;abord l&#39;étendre avec les champs de votre choix. Pour cela :

* Identifiez les champs de PII envoyés par l&#39;application mobile.
* Identifiez le champ à utiliser pour la réconciliation afin d&#39;associer les données de PII aux données de profil.

![](assets/update_profile1.png)

Dans cet exemple, la section **[!UICONTROL Champs]** reflète les données de PII envoyées par l&#39;application mobile. La section **[!UICONTROL Lien vers les profils]** indique le champ utilisé pour associer les données de PII aux données de profil, où **cusEmail** est associé à **@email**.

L&#39;association des données de profil lors de l&#39;extension de la ressource **[!UICONTROL Abonnements à une application]** est en LECTURE SEULE. Elle est utilisée pour la réconciliation. Le profil doit être entré dans le système avec les données nécessaires pour réconcilier le profil avec les données de PII. Dans notre cas, une adresse email pour le profil doit correspondre à un email provenant de la collecte des PII pour que la réconciliation se produise :

* La collecte des PII est reçue d&#39;une application mobile pour un utilisateur dont le prénom est « Jane », le nom « Doe » et l&#39;adresse email janedoe@doe.com.
* Les données de profil doivent exister séparément (par exemple, les données doivent être saisies manuellement ou provenir déjà d&#39;une autre ressource) où l&#39;adresse email du profil est janedoe@doe.com.

**Rubriques connexes :**

* [Extension des abonnements à une ressource d&#39;application](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Création ou extension d&#39;une ressource existante](../../developing/using/key-steps-to-add-a-resource.md).

## Etape 2 - Créer le workflow

L&#39;utilisation d&#39;un workflow dans Campaign Standard permet à un administrateur d&#39;identifier et de synchroniser de manière unique les données entre les données AppSubscription (abonné) et de profil ou de destinataire. Bien qu&#39;une mise à jour à partir d&#39;un workflow ne synchronise pas les données de profil en temps réel, elle ne doit pas entraîner de verrouillage de base de données ni de surcharge indus.

Les étapes principales pour créer le workflow sont les suivantes :

1. Utilisez une activité de **[!UICONTROL Requête]** ou de **[!UICONTROL Requête incrémentale]** pour obtenir la liste des derniers abonnements.
1. Utilisez une activité de **[!UICONTROL Réconciliation]** pour associer les données de PII au profil.
1. Ajoutez un processus de vérification.
1. Utilisez une **[!UICONTROL Mise à jour de données]** pour mettre à jour ou créer le profil avec les données de PII.

Dans ce workflow, les conditions suivantes sont remplies :

* Tous les champs ayant été étendus doivent être disponibles pour créer/mettre à jour la table des profils.
* La table des profils peut être étendue pour prendre en charge les champs qui ne sont pas pris en charge de manière native (par exemple, la taille des T-shirts).
* Un champ vide de la table AppSubscription ne doit pas être mis à jour dans la table des profils.
* Un enregistrement mis à jour dans la table AppSubscription doit être inclus dans la prochaine exécution du workflow.

Pour créer le workflow, placez les activités suivantes dans l’espace de travail et reliez-les : **[!UICONTROL Démarrer]**, **[!UICONTROL Planificateur]**, **[!UICONTROL Requête incrémentale]**, **[!UICONTROL Mettre à jour les données]**.

![](assets/update_profile0.png)

Suivez ensuite les étapes ci-dessous pour configurer chaque activité.

### Configurez l&#39;activité **[!UICONTROL Planificateur]**

Dans l&#39;onglet **[!UICONTROL Général]**, définissez la **[!UICONTROL Fréquence d&#39;exécution]** (par exemple, &quot;Quotidienne&quot;), l&#39;**[!UICONTROL Heure]** (par exemple, &quot;13 h 00&quot;) et le **[!UICONTROL Début]** (par exemple, la date du jour).

![](assets/update_profile2.png)

### Configurez l&#39;activité de **[!UICONTROL Requête incrémentale]**.

1. Dans l&#39;onglet **[!UICONTROL Propriétés]**, cliquez sur l&#39;icône **[!UICONTROL Sélectionner un élément]** du champ **[!UICONTROL Ressource]**, puis sélectionnez l&#39;élément **[!UICONTROL Abonnements à une application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]**.

   ![](assets/update_profile3.png)

1. Dans l&#39;onglet **[!UICONTROL Cible]**, faites glisser le filtre **[!UICONTROL Application mobile]**, puis sélectionnez le nom d&#39;une application mobile.

   ![](assets/update_profile4.png)

1. Dans l&#39;onglet **[!UICONTROL Données traitées]**, sélectionnez **[!UICONTROL Utiliser un champ de date]**, puis ajoutez le champ **[!UICONTROL Dernière modification (lastModified)]** en tant que **[!UICONTROL Chemin d&#39;accès au champ de date]**.

   ![](assets/update_profile5.png)

### Configurez l&#39;activité **[!UICONTROL Mise à jour de données]**.

1. Dans l&#39;onglet **[!UICONTROL Identification]**, vérifiez que le champ **[!UICONTROL Dimension à mettre à jour]** est défini sur &quot;Profils (profil)&quot;, puis cliquez sur le bouton **[!UICONTROL Créer un élément]** pour ajouter un champ en tant que critère de réconciliation.

   ![](assets/update_profile_createelement.png)

1. Dans le champ **[!UICONTROL Source]**, sélectionnez un champ de la table appSubscrsiptionRcp en tant que champ de réconciliation. Il peut s&#39;agir de l&#39;email du profil, de crmId, de marketingCloudId, etc. Dans cet exemple, nous utiliserons le champ &quot;Email (cusEmail)&quot;.

1. Dans le champ **[!UICONTROL Destination]**, sélectionnez un champ dans la table des profils pour réconcilier les données de la table appSubscriptionRcp. Il peut s&#39;agir de l&#39;email du profil ou d&#39;un champ étendu tel que crmId, marketingCloudId, etc. Dans cet exemple, nous devons sélectionner le champ &quot;Email (email)&quot; pour l&#39;associer au champ &quot;Email (cusEmail)&quot; de la table appSubscriptionRcp.

   ![](assets/update_profile7.png)

1. Dans l&#39;onglet **[!UICONTROL Champs à mettre à jour]**, cliquez sur le bouton **[!UICONTROL Créer un élément]**, puis associez les champs provenant de la table appSubscriptionRcp (champ **[!UICONTROL Source]**) aux champs à mettre à jour dans la table des profils (champ **[!UICONTROL Destination]**).

1. Dans le champ **[!UICONTROL Activé si]**, ajoutez une expression pour que le champ correspondant dans la table des profils ne soit mis à jour que si le champ source contient une valeur. Pour cela, sélectionnez le champ dans la liste, puis ajoutez l&#39;expression &quot;!=&#39;&#39;&quot; (si le champ Source est `[target/@cusEmail]` dans l&#39;éditeur d&#39;expression, veillez à saisir `[target/@cusEmail] != ''"`).

   ![](assets/update_profile8.png)

>[!NOTE]
>
>Dans ce cas, le workflow effectue une opération UPSERT, mais comme il est basé sur une **[!UICONTROL requête incrémentale]**, les données sont uniquement insérées. La modification de la requête peut avoir un impact sur les données insérées ou mises à jour.
>En outre, les paramètres de l&#39;onglet Champs à mettre à jour déterminent quels champs sont insérés ou mis à jour dans des conditions spécifiques. Ces paramètres peuvent être uniques pour chaque application ou client.
>Faites attention lors de la configuration de ces paramètres, car elle peut avoir des conséquences inattendues. En effet, la mise à jour des enregistrements dans le profil en fonction des données appSubscriptionRcp peut modifier les informations personnelles des utilisateurs sans validation.

Lorsque tous les champs à insérer/mettre à jour dans le profil ont été ajoutés, cliquez sur **[!UICONTROL Confirmer]**.

![](assets/update_profile9.png)

Enregistrez le workflow, puis cliquez sur **[!UICONTROL Démarrer]** pour l’exécuter.

![](assets/update_profile10.png)
