---
solution: Campaign Standard
product: campaign
title: Créer un email de test A/B
description: Découvrez la fonctionnalité de test A/B et suivez ces étapes pour créer un email depuis un modèle de test A/B dans Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 100%

---


# Créer un email de test A/B{#designing-an-a-b-test-email}

La fonctionnalité de test A/B dans Adobe Campaign vous permet de définir de deux à trois variantes d&#39;un email. Chaque variante est envoyée à des échantillons de population afin de déterminer celle qui entraîne les meilleurs résultats. Une fois déterminée, la variante gagnante est alors envoyée à la population ciblée restante.

Vous pouvez choisir de faire varier le contenu, le sujet ou l&#39;expéditeur de l&#39;email.

>[!NOTE]
>
>Il est impossible de réaliser des tests A/B sur des emails créés dans Adobe Experience Manager.

## Créer un email de test A/B     {#creating-an-a-b-test-email}

La création d&#39;un email de type test A/B peut être réalisée à l&#39;aide de l&#39;assistant de création d&#39;un email standard, auquel est ajoutée une étape de paramétrage du test A/B. La création d&#39;un email standard est présentée dans la section [Créer un email](../../channels/using/creating-an-email.md).

Dans le cadre spécifique d&#39;un test A/B :

1. Créez un email à partir de l&#39;un des trois modèles spécifiques à l&#39;A/B testing, en fonction de l&#39;élément que vous souhaitez faire varier :

   * Test A/B sur l&#39;expéditeur
   * Test A/B sur le contenu
   * Test A/B sur l&#39;objet

   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >Les modèles de relance et de test A/B sont masqués par défaut. Cochez la case Test A/B située à gauche (au niveau du panneau latéral **[!UICONTROL Filtrer]**) pour les afficher.

1. Définissez les propriétés générales et l&#39;audience cible de l&#39;email de la même manière que pour un email standard. Consultez la section [Créer une audience](../../audiences/using/creating-audiences.md).
1. A la quatrième étape de l&#39;assistant de création, définissez les paramètres du test A/B :

   * **[!UICONTROL Nombre de variantes]** : vous pouvez choisir d&#39;utiliser deux ou trois variantes. Si vous choisissez trois variantes, ce choix n&#39;est plus modifiable après validation de cette étape de l&#39;assistant.
   * **[!UICONTROL Stratégie gagnante]** : sélectionnez le critère à utiliser pour déterminer la variante gagnante.
   * **[!UICONTROL Répartition de la cible]** : choisissez quel pourcentage de la cible recevra chaque variante. Le pourcentage restant recevra la variante gagnante une fois qu&#39;elle sera déterminée. La sélection est réalisée aléatoirement parmi les profils de la cible.
   * **[!UICONTROL Méthode d&#39;envoi du gagnant]** : choisissez si vous souhaitez que la variante gagnante soit automatiquement envoyée une fois déterminée ou si vous souhaitez confirmer manuellement l&#39;envoi à la population restante.
   * **[!UICONTROL Durée du test]** : indiquez la durée du test. La variante gagnante est déterminée automatiquement à l&#39;issue de cette durée. Vous pouvez choisir manuellement la variante gagnante avant la fin du test depuis le tableau de bord de l&#39;email.

      Le test doit avoir une durée supérieure ou égale à une heure afin que des données de tracking puissent être collectées et correctement prises en compte pour le choix de la variante gagnante.
   ![](assets/ab_parameters.png)

1. Une fois les paramètres du test A/B définis, passez à l&#39;étape suivante de l&#39;assistant et définissez le contenu de l&#39;email. En fonction du modèle que vous avez choisi, vous pouvez définir plusieurs objets, plusieurs noms d&#39;expéditeurs ou plusieurs contenus différents. Utilisez le carrousel afin de naviguer entre les différentes variantes de l&#39;élément. Pour plus d&#39;informations, consultez la section relative à l&#39;[éditeur de contenu](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/create_ab_testing2.png)

1. Validez la création de l&#39;email. Le tableau de bord de l&#39;email s&#39;affiche.
1. Planifiez l&#39;envoi. La date définie indique le début du test A/B.
1. Vérifiez les paramètres du test A/B affichés au niveau du bloc **[!UICONTROL Paramètres du test A/B]**. Vous pouvez les modifier jusqu&#39;à la confirmation de l&#39;envoi du test (étape 9) en sélectionnant le bloc.

   ![](assets/create_ab_testing3.png)

1. Préparez l&#39;envoi de l&#39;email afin d&#39;analyser la cible et le nombre de messages à envoyer. Consultez la section [Préparer l&#39;envoi](../../sending/using/preparing-the-send.md).
1. Avant d&#39;envoyer le test A/B, vérifiez votre email en envoyant des BAT.
1. Une fois la préparation terminée, confirmez l&#39;envoi du test. Après la confirmation, les paramètres de test A/B ne sont plus modifiables.

   Le test A/B démarre à la date définie dans le **[!UICONTROL Planing d&#39;envoi]**. Vous pouvez tracker son avancement à l&#39;aide des blocs **[!UICONTROL Test A/B]** et **[!UICONTROL Déploiement]**.

   Vous pouvez à tout moment sélectionner manuellement la variante gagnante si vous souhaitez écourter la durée du test.

   Une fois le test terminé, un tableau récapitulatif s&#39;affiche sur le bloc **[!UICONTROL Test A/B]**, qui permet de visualiser les différents indicateurs relatifs aux différentes variantes testées.

1. Si vous avez sélectionné **[!UICONTROL Envoi après confirmation]** comme méthode d&#39;envoi, vous devez sélectionner manuellement la variante gagnante pour commencer à l&#39;envoyer à la population restante. Si vous avez sélectionné **[!UICONTROL Automatique]**, la variante gagnante est envoyée automatiquement à la population restante dès qu&#39;elle a été déterminée par le système.

   >[!NOTE]
   >
   >En cas d&#39;égalité, la variante gagnante doit être sélectionnée manuellement. Vous pouvez avertir l&#39;auteur de l&#39;email, ainsi que la ou les personnes l&#39;ayant modifié, qu&#39;une variante a été sélectionnée ou doit l&#39;être. Voir [Notifications d’Adobe Campaign](../../administration/using/sending-internal-notifications.md).

Votre email est maintenant défini et envoyé. Vous pouvez accéder à ses logs et rapports pour mesurer le succès de votre campagne.

## A propos des indicateurs de test A/B {#about-a-b-test-indicators}

Dans le tableau de bord des emails, plusieurs indicateurs sont proposés pour vous aider à mesurer votre test A/B : nombre de clics, ouvertures, bounces, etc.

Notez que l&#39;indicateur **[!UICONTROL Réactivité estimée des destinataires]** est un taux comparant le nombre de destinataires ayant cliqué au nombre de destinataires ayant ouvert l&#39;email. Par exemple, si 10 destinataires ont ouvert l&#39;email et si 5 d&#39;entre eux ont cliqué dessus, le taux de réactivité est de 50 %.
