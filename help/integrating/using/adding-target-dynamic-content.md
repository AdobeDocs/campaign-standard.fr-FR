---
title: Ajouter du contenu dynamique Target
description: Découvrez comment ajouter du contenu dynamique Adobe Target dans une de vos diffusions Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 100%

---

# Ajouter du contenu dynamique Target{#adding-target-dynamic-content}

Avec l&#39;intégration avec Adobe Target, des images dynamiques peuvent être ajoutées dans une diffusion afin de personnaliser le contenu selon les expériences.

Pendant l&#39;édition d&#39;un email, vous pouvez insérer depuis Adobe Target une image dynamique qui changera en fonction des destinataires.

Avant d&#39;accéder à l&#39;image dans Adobe Campaign, les tâches suivantes doivent être réalisées dans Adobe Target :

* créer une ou plusieurs [offres de redirection](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=fr), dans lesquelles vous devez spécifier l&#39;URL de l&#39;image que vous souhaitez utiliser.
* créer une ou plusieurs [audiences](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html?lang=fr), afin de définir la cible de votre activité.
* créer une activité de type [Compositeur d&#39;expérience d&#39;après les formulaires](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html?lang=fr), dans laquelle vous devez sélectionner un &quot;rawbox&quot; et définir plusieurs expériences, en fonction du nombre d&#39;offres de redirection créées. Pour chaque expérience, vous devez sélectionner une des offres de redirection créées.
* créer des segments à l&#39;aide des informations issues d&#39;Adobe Campaign pour spécifier des expériences. Si vous souhaitez utiliser des données issues d’Adobe Campaign dans les règles de sélection de l’offre, vous devez les spécifier au niveau du « rawbox » dans Adobe Target.

1. Créez une diffusion email.
1. Lors de l&#39;édition du contenu d&#39;un email ou d&#39;une landing page, placez-vous sur un bloc de type image, puis via le menu contextuel, sélectionnez **[!UICONTROL Image dynamique servie par Adobe Target]**.

   ![](assets/tar_insert_dynamic_image.png)

1. Sélectionnez l&#39;image qui s&#39;affichera par défaut dans l&#39;email. Vous pouvez indiquer directement l&#39;URL de l&#39;image ou sélectionner une image partagée via [Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   L&#39;intégration prend uniquement en charge les images statiques. Le reste du contenu n&#39;est pas personnalisable.

1. Saisissez le nom du &quot;rawbox&quot; défini dans Adobe Target.
1. Dans Adobe Target, si vous utilisez les autorisations Enterprise, ajoutez la propriété correspondante dans ce champ. Pour plus d&#39;informations sur les autorisations Enterprise Target, consultez [cette page](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=fr). Ce champ est facultatif et n’est pas obligatoire si vous n’utilisez pas les autorisations Enterprise dans Target.
1. Dans **[!UICONTROL Paramètres de décision additionnels]**, associez les champs définis dans les segments Adobe Target et les champs d&#39;Adobe Campaign.

   Les champs d’Adobe Campaign utilisés doivent avoir été spécifiés au niveau du « rawbox ». Dans cet exemple, définissez différentes expériences en fonction du sexe du destinataire.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Prévisualisez votre e-mail pour voir si, lorsque vous sélectionnez différents profils, l’image insérée change en fonction des paramètres définis dans l’activité Adobe Target et dans Adobe Campaign.

La diffusion contenant l&#39;image dynamique peut maintenant être envoyée. Ses résultats sont accessibles dans Adobe Target.

**Rubriques connexes :**

* [Portail d&#39;Adobe Target](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=fr)
* [À propos de la conception du contenu d&#39;un email](../../designing/using/designing-content-in-adobe-campaign.md)
* Vidéo [Personnaliser des images d&#39;email en temps réel](https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html)
