---
title: Modèles de landing page
description: En savoir plus sur les modèles de landing page.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: ht
source-wordcount: '241'
ht-degree: 100%

---


# A propos des modèles de landing page {#landing-page-templates}

Campaign intègre un jeu de modèles de landing page intégrés.

* **[!UICONTROL Acquisition]** : il s&#39;agit du modèle par défaut des landing pages. Il permet de capturer et de mettre à jour les données dans la base de données Campaign.
* **[!UICONTROL Inscription]** : ce modèle doit être utilisé pour proposer des inscriptions à un service.
* **[!UICONTROL Désinscription]** : ce modèle peut être lié à un email envoyé aux abonnés à un service afin de leur permettre de se désinscrire de celui-ci.
* **[!UICONTROL Liste bloquée]** : ce modèle doit être utilisé lorsqu’un profil ne souhaite plus être contacté par Campaign. Pour plus d’informations sur la gestion des listes bloquées, voir la section [À propos des processus d’opt-in et d’opt-out dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).s

Ces modèles sont proposés par défaut lors de la création d&#39;une nouvelle landing page.

![](assets/lp_creation_1.png)

Pour accéder aux modèles, cliquez sur le logo Adobe Campaign dans le coin supérieur gauche et sélectionnez **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de landing page]**.

>[!NOTE]
>
>Adobe vous recommande de créer vos propres modèles en dupliquant un modèle intégré. Certains paramètres peuvent seulement être définis dans les modèles de landing page et ne sont pas modifiables directement sur les landing pages.

Lors de la construction d&#39;un modèle, il est conseillé d&#39;ajouter un attribut **&#39;type&#39;** aux balises. Cette information sera interprétée par l&#39;éditeur et aidera l&#39;utilisateur à associer un champ de la base de données au champ du formulaire lors du paramétrage de l&#39;application Web.

Exemple de code HTML dans le modèle :

```
<input id="email" type="email" name="email"/>
```

La liste officielle des attributs &#39;type&#39; est disponible à l&#39;adresse suivante : [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)