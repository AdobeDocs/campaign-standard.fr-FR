---
title: Marques
description: Découvrez tous les outils disponibles pour gérer les identités de la marque.
page-status-flag: never-activated
uuid: d66ac5a2-2ae1-4870-b48e-7f276744ffdd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32bf8
context-tags: branding,overview;branding,main
translation-type: tm+mt
source-git-commit: 100f7eef03d10a66832920708ad415f8f0d3883c
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 94%

---


# Marques{#branding}

## A propos de l&#39;identité d&#39;une marque {#about-brand-identity}

Chaque entreprise dispose de directives visuelles et techniques en ce qui concerne la marque. Avec Adobe Campaign, vous pouvez définir un ensemble de spécifications pour présenter à vos clients une marque cohérente, depuis les logos jusqu&#39;aux aspects techniques, tels que l&#39;expéditeur de l&#39;email, l&#39;URL ou les domaines.

Les administrateurs techniques peuvent définir une ou plusieurs marques afin de renseigner de manière centralisée les paramètres qui touchent à l&#39;identité d&#39;une marque, par exemple : le logo de la marque, le domaine d&#39;URL d&#39;accès aux landing pages ainsi que les paramètres du tracking des messages. Avec Adobe Campaign, vous pouvez créer ces marques et les associer à des messages ou des landing pages. Cette configuration est gérée dans des modèles.

## Configuration et utilisation des marques       {#configuring-and-using-brands}

Le principe général de paramétrage et d&#39;utilisation des marques est le suivant :

1. Créer et configurer la marque : cette opération requiert des permissions spécifiques et est réalisée par l&#39;administrateur technique Adobe Campaign. Les étapes pour obtenir une nouvelle marque dans Campaign sont détaillées [dans cette section](#creating-a-brand).
1. Créer un ou plusieurs modèles de diffusion et de landing pages pour cette marque. Voir la section [Créer un modèle](../../start/using/marketing-activity-templates.md).
1. Créer des messages et des landing pages à partir de ce modèle. Voir les sections [Créer un email](../../channels/using/creating-an-email.md) et [Créer une landing page](../../channels/using/designing-a-landing-page.md).

>[!IMPORTANT]
>
>Les marques ne peuvent pas être créées ni modifiées par des utilisateurs finaux : ces opérations doivent être effectuées par l&#39;administrateur technique Adobe Campaign. Pour toute demande, contactez l&#39;assistance client Adobe.
>
>Le multi-branding ne peut pas être utilisé dans le contexte des messages transactionnels. Voir à ce propos la section [Messages transactionnels et marque](../../channels/using/transactional-messaging-limitations.md#permissions-and-branding).

Les marques figurent dans **[!UICONTROL Administration > Paramétrage de l&#39;instance > Paramétrage des marques]**.

Par défaut, la marque nouvellement créée est uniquement visible par les utilisateurs auxquels les droits correspondants ont été affectés par l&#39;administrateur.

Une **marque** est définie par les caractéristiques suivantes :

* Une **identité** qui permet d&#39;identifier et de personnaliser votre marque. Cette section contient les champs suivants :

   ![](assets/branding_01.png)

   * **Libellé**, visible dans l&#39;interface
   * **Nom de la marque**
   * **URL du site web** et **Libellé du site web** de la marque
   * **Logo de la marque**

* **[!UICONTROL Paramètres d&#39;en-tête des emails envoyés]** qui permettent de personnaliser les informations qui seront visibles par les destinataires de vos campagnes. Cette section contient les champs suivants :

   ![](assets/branding_04_header.png)

   * **Expéditeur (adresse email)** avec l&#39;adresse email de la marque
   * **Expéditeur (nom)** avec le nom de la marque
   * **Répondre à (adresse email)** avec l&#39;adresse email de réponse destinée au client
   * **Répondre à (nom)** avec le nom de la marque
   * **Erreur (adresse email)** avec l&#39;adresse email à utiliser en cas d&#39;erreur

   >[!IMPORTANT]
   >
   >Après avoir mis à jour les paramètres d&#39;en-tête des emails, si le nom et l&#39;adresse email de l&#39;expéditeur ne sont pas modifiés dans l&#39;email créé à partir du modèle, vérifiez les paramètres avancés de ce dernier.

* **Serveur(s) exposé(s) sur Internet** permet de définir les serveurs utilisés pour le tracking et l&#39;accès aux landing pages. Cette section contient les champs suivants :

   ![](assets/configure_branding_04.png)

   * **URL externe du serveur applicatif** utilisée pour héberger les différentes landing pages créées et y accéder
   * **URL externe du serveur de tracking** utilisée en tant qu&#39;URL trackée lors des diffusions
   * **URL externe du serveur de page miroir** utilisée en tant que page miroir par défaut dans vos diffusions

   >[!NOTE]
   >
   >Pour afficher l’aperçu de la landing page et le rendu de la page miroir dans l’interface utilisateur de Campaign, les URL du serveur applicatif et du serveur de page miroir doivent être sécurisées. Dans ce cas, utilisez https:// plutôt que http:// lors de la configuration de ces URL.

* **[!UICONTROL Paramétrage des URL de tracking (Web Analytics)]** qui permet de définir la configuration du tracking de vos URL pour votre marque.

   Les paramètres additionnels qui permettent de tracker les liens sur des systèmes externes tels que les outils de Web Analytics comme Adobe Analytics ou Google Analytics sont définis dans cette section.

   ![](assets/branding_05.png)

## Créer une nouvelle marque {#creating-a-brand}

Vous pouvez ajouter de nouvelles entités de votre organisation dans Campaign ou créer un nouveau type d’email que vous devez envoyer sous un autre sous-domaine. Pour ce faire, suivez les étapes ci-après :

1. **Configurer un nouveau sous-domaine** - Pour tout nouveau sous-domaine à utiliser par Adobe, la première étape consiste à le configurer. Vous pouvez effectuer cette opération via le [Panneau de contrôle Campaign](https://docs.adobe.com/content/help/fr-FR/control-panel/using/subdomains-and-certificates/subdomains-branding.html) ou contacter votre contact technique Adobe. Learn more about subdomain configuration [in this article](https://helpx.adobe.com/fr/campaign/kb/domain-name-delegation.html).

1. **Créer un ticket** - Une fois le sous-domaine configuré, l&#39;Adobe devra le configurer dans votre environnement de production. Pour ce faire, [créez un ticket pour l’assistance clientèle](https://helpx.adobe.com/fr/enterprise/using/support-for-experience-cloud.html) avec les informations suivantes :

   * Objet : configuration de la nouvelle marque ACS

   * Contenu : Un nouveau domaine a été configuré et nous aimerions l&#39;installer sur notre plateforme Campaign

   * Domaine : XXX

   * URL de production : XXX.campaign.adobe.com

1. **Créer un modèle de diffusion** - Une fois la nouvelle marque disponible, il est recommandé de créer au moins un modèle de diffusion vierge qui fait référence à cette nouvelle marque. [En savoir plus](#linking-a-brand-to-a-template).

1. **Vérifier les instructions relatives à la délivrabilité** : avant de commencer à utiliser le nouveau domaine, la stratégie doit être discutée avec l&#39;équipe Adobe chargée de la délivrabilité Elle aidera à définir les bonnes pratiques, si une nouvelle affinité doit être créée pour fractionner les adresses IP entre les domaines par exemple, et/ou si un plan de propagation doit être défini. Pour en savoir plus sur les bonnes pratiques en matière de délivrabilité, [consultez cette section](../../sending/using/about-deliverability.md).

## Affectation d&#39;une marque à un email       {#assigning-a-brand-to-an-email}

### Liaison d&#39;une marque à un modèle {#linking-a-brand-to-a-template}

Pour utiliser les paramètres définis pour une marque, elle doit être liée à un modèle de diffusion ou de landing page. Pour ce faire, vous devez créer, ou éditer, un modèle.

>[!NOTE]
>
>Pour plus d&#39;informations sur la création d&#39;un modèle, voir la section [Créer un modèle](../../start/using/marketing-activity-templates.md).

Une fois votre modèle créé, vous pouvez le lier à une marque. Pour cela :

1. Cliquez sur le bouton **[!UICONTROL Editer les propriétés]** pour accéder aux propriétés de votre modèle.

   ![](assets/branding_04.png)

1. Utilisez la liste déroulante pour sélectionner la marque que vous souhaitez lier au modèle.

   >[!NOTE]
   >
   >Par défaut, la marque **[!UICONTROL Marque par défaut (branding)]** est sélectionnée.

   ![](assets/branding_05.png)

   Pour visualiser le paramétrage de la marque sélectionnée, cliquez sur l&#39;icône **[!UICONTROL Naviguer vers le détail de l&#39;élément sélectionné]**.

   ![](assets/branding_06.png)

1. Validez votre sélection et enregistrez votre modèle.

Votre modèle est lié à la marque. Dans l&#39;éditeur d&#39;email, les éléments comme l&#39;**adresse email de l&#39;expéditeur par défaut**, le **nom de l&#39;expéditeur par défaut** ou le **logo** utiliseront les données paramétrées de la marque.

### Cas pratique de marque       {#branding-use-case}

Dans cet exemple, nous allons créer, et utiliser dans un email, une nouvelle marque sur le thème du voyage.

#### Configurer une nouvelle marque       {#configure-a-new-brand}

>[!IMPORTANT]
>
>La configuration des marques n&#39;est gérée que par Adobe, car elle nécessite des paramètres techniques et des permissions spécifiques.

1. L&#39;administrateur Adobe Campaign crée la marque dans **[!UICONTROL Administration > Paramétrage de l&#39;instance > Paramétrage des marques]**. il ajoute l&#39;élément **Voyages sous les tropiques** et configure l&#39;**[!UICONTROL identité]** et les **[!UICONTROL paramètres d&#39;en-tête des emails envoyés]** de la marque.

   ![](assets/branding_07.png)

1. Il configure ensuite l&#39;URL du **serveur exposé sur Internet** afin de permettre l&#39;utilisation de landing pages, puis les URL de tracking.

   Dans cet exemple, l&#39;outil de **Web Analytics** utilisé est **Google Analytics**. L&#39;administrateur paramètre les URL de tracking comme suit :

   ![](assets/branding_12.png)

La marque est correctement créée et paramétrée. Elle peut désormais être utilisée par les équipes marketing.

#### Mettre en œuvre une nouvelle marque       {#implement-a-new-brand}

En tant que chargé de diffusion, vous êtes responsable de la création des modèles de diffusion afin d&#39;utiliser la nouvelle marque. Pour ce faire, procédez comme suit :

1. Dans le menu avancé **[!UICONTROL Ressources > Modèles > Modèles de diffusion]**, dupliquez un modèle intégré afin de configurer un nouveau modèle de diffusion.

   ![](assets/branding_08.png)

1. Pour lier ce modèle à la marque **Voyages sous les tropiques**, éditez les propriétés du modèle et sélectionnez la marque dans la liste déroulante.

   ![](assets/branding_09.png)

1. Configurez ce modèle d&#39;email de sorte à refléter l&#39;identité de la marque.
1. Une fois le modèle terminé, vous pouvez l&#39;enregistrer.

   ![](assets/branding_10.png)

   Le modèle de diffusion peut désormais être utilisé pour créer des emails qui seront envoyés à une audience.

#### Utiliser la nouvelle marque dans une diffusion       {#use-the-new-brand-in-a-delivery}

Pour créer un email lié à une marque, procédez comme suit :

1. Cliquez sur le bouton **[!UICONTROL Créer]** dans le menu **[!UICONTROL Activités marketing]**.

   ![](assets/branding_14.png)

1. Sélectionnez l&#39;activité **[!UICONTROL Email]**, puis choisissez le modèle lié à la nouvelle marque.

   ![](assets/branding_15.png)

1. Votre email est déjà configuré. Vous pouvez en vérifier les informations avant de le tester grâce à des profils de test, puis de l&#39;envoyer à votre audience.

   ![](assets/branding_16.png)

