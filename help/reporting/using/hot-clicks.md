---
title: Hot clicks
description: Grâce au rapport d'usine Hot clicks, découvrez à quel endroit votre client a cliqué dans votre diffusion.
page-status-flag: never-activated
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,main
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '491'
ht-degree: 100%

---


# Hot clicks{#hot-clicks}

Ce rapport est consultable au niveau de chaque diffusion ou chaque message transactionnel, à partir du bouton **[!UICONTROL Rapports]**.

![](assets/delivery_reports_hot-clicks_4.png)

Il présente le contenu du message (HTML et/ou texte) avec, sur chaque lien, le pourcentage de clics sur ce lien.

![](assets/delivery_reports_10.png)

Si vous avez créé du contenu dynamique pour votre diffusion, vous pouvez afficher les pourcentages de chaque condition que vous avez définie. Pour plus d&#39;informations sur l&#39;insertion de contenu conditionnel dans une diffusion, voir [Définir un contenu dynamique](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Imaginez par exemple que vous avez créé une diffusion avec les conditions suivantes :

* Le lien de l&#39;image principale est différent selon que le destinataire est un homme ou une femme.
* Vous avez également ajouté un lien vers une offre spéciale visible uniquement par les destinataires de plus de 25 ans.

Une fois le message envoyé, sélectionnez **[!UICONTROL Rapports]** > **[!UICONTROL Hot clicks]** dans le tableau de bord des diffusions.

Par défaut, aucun profil n&#39;est sélectionné. Seuls les clics des destinataires dont le genre est inconnu et ceux âgés de moins de 25 ans ou dont l&#39;âge est inconnu sont affichés.

![](assets/delivery_reports_hot-clicks_1.png)

Pour afficher les clics des femmes, cliquez sur le bouton **[!UICONTROL Charger un profil]** et sélectionnez un profil de test féminin. Pour afficher les clics des hommes, procédez de façon identique et sélectionnez un profil de test masculin.

![](assets/delivery_reports_hot-clicks_2.png)

Pour afficher les clics des destinataires de plus de 25 ans, cliquez sur le bouton **[!UICONTROL Charger un profil]** et sélectionnez un profil de test dont la date de naissance correspond à cette condition.

Pour en savoir plus sur les profils de test, voir [Profils de test](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>Le nombre de clics sur un lien spécifique est un pourcentage du nombre total de clics pour tous les contenus conditionnels d&#39;une diffusion. Par conséquent, si vous avez défini du contenu dynamique, le total des pourcentages affichés pour un profil de test spécifique peut ne pas être égal à 100.

De même, pour les diffusions récurrentes et les messages transactionnels, vous pouvez sélectionner le profil de test correspondant au contenu dynamique que vous souhaitez afficher. Vous pouvez aussi afficher les pourcentages de clics selon la diffusion d&#39;exécution sélectionnée.

Une diffusion d&#39;exécution est un message technique non fonctionnel et non exploitable qui est créé dans les cas suivants :

* Chaque fois qu&#39;une diffusion récurrente est exécutée ou mise à jour.

   Par exemple, si le workflow qui gère cette diffusion est exécuté une fois par mois, il y aura une diffusion d&#39;exécution par mois. De plus, chaque fois que le contenu de la diffusion est mis à jour, une autre diffusion d&#39;exécution est créée.

   Pour plus d&#39;informations sur les diffusions email récurrentes, voir [Diffusion Email](../../automating/using/email-delivery.md).

* Par défaut, une fois par mois pour les messages transactionnels et chaque fois qu&#39;un message transactionnel est édité et republié.

   Pour plus d’informations sur les messages transactionnels, voir la section [Prise en main de la messagerie transactionnelle](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Dans la mesure où les identifiants des URL trackées sont différents pour chaque exécution, les données de hot clicks ne peuvent pas être agrégées pour toutes les diffusions d&#39;exécution d&#39;un message donné. Elles s&#39;affichent pour une seule diffusion d&#39;exécution à la fois.

Une fois le message envoyé, sélectionnez **[!UICONTROL Rapports]** > **[!UICONTROL Hot clicks]** dans le tableau de bord des diffusions.

Par défaut, la dernière diffusion d&#39;exécution est sélectionnée. Cliquez sur le bouton **[!UICONTROL Modifier la diffusion d&#39;exécution]** pour en sélectionner une autre.

![](assets/delivery_reports_hot-clicks_3.png)

Seuls les pourcentages de clics pour l&#39;exécution de la diffusion sélectionnée sont affichés.
