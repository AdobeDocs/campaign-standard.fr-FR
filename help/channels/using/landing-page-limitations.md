---
title: Limites de la page d'entrée
seo-title: Limites de la page d'entrée
description: Limites de la page d'entrée
seo-description: Découvrez les landing pages Campaign et leur cycle de vie.
page-status-flag: jamais activé
uuid: b 316 bf 47-7 d 98-46 fa-ab 4 f -67 ff 50 de 8095
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canaux
content-type: référence
topic-tags: landing-pages
discoiquuid: ca 8 d 1698-6 e 8 a -4 f 5 a-b 017-74 a 152 e 14286
context-tags: Landingpage, assistant ; Landingpage, overview ; Landingpage, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0b2377a2bfdb8745ec9c3e418d8bed00e18447ff

---


# Landing page limitations{#landing-page-limitations}

**Rédaction et mise à jour des données**

* Landing pages are limited to **[!UICONTROL Profile]** and **[!UICONTROL Subscription]** resources only. Record can be saved and updated from **[!UICONTROL Profile]** and a subscription/unsubscription to a **[!UICONTROL Service]**.
To learn more on resources configuration, see [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).

[!CAUTION]
> A landing page cannot display or update data from any other resource than **[!UICONTROL Profile]** and **[!UICONTROL Subscription]**.

**Préchargement**

* La page d'entrée ne peut pas afficher automatiquement une liste d'enregistrements. Elle ne peut pas répertorier les services auxquels les profils déjà s'abonnent. For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* La page d'entrée avec un formulaire prérempli (les données sont préchargées avec la page) ne peut être accessible qu'à partir d'un courrier électronique Adobe Campaign. Il est impossible d'accéder à un tel formulaire à partir d'une page de site Web.

**Réconciliation**

* Le comportement de réconciliation est le suivant : dès qu'une correspondance est trouvée, le processus de réconciliation s'arrête. Cela signifie que la réconciliation ne peut être effectuée que sur un enregistrement de profil et non sur plusieurs enregistrements lorsqu'il existe des doublons.

Par exemple, vous souhaitez envoyer la page d'entrée d'acquisition suivante à vos profils afin de mettre à jour votre base de données Campaign avec les numéros mobiles de vos profils.

![](assets/landing_page_limitation_1.png)

Si l'un de vos profils remplit votre page d'entrée avec de nouvelles informations mais a déjà un profil dupliqué, le profil correspondant avec la date de création la plus ancienne est mis à jour puisque les profils sont prioritaires, selon leur date de création uniquement.

Ici seul le premier profil a été mis à jour puisqu'il s'agit de l'entrée la plus ancienne.

![](assets/landing_page_limitation_2.png)

**Test de la page d'entrée**

* Les pages d'entrée ne fonctionnent que sur les profils et ne peuvent pas tester les profils de test, signifiant que les pages d'entrée ne peuvent pas être testées dans le cadre d'un courrier électronique.
