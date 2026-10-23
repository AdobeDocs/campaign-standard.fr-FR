---
title: Modèles de landing page
description: En savoir plus sur les modèles de landing page.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 29d1badf-9ce3-470c-9bdc-169586d2e943
TQID: 'https://experienceleague.adobe.com/vJyIRO33IjK6o3--ekx-Iw9K-GcIZMViLz9wEr-kxY0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%
---
# À propos des modèles de landing pages {#landing-page-templates}

Campaign intègre un jeu de modèles de landing page intégrés.

* **[!UICONTROL Acquisition]** : il s&#39;agit du modèle par défaut des landing pages. Il permet de capturer et de mettre à jour les données dans la base de données Campaign.
* **[!UICONTROL Inscription]** : ce modèle doit être utilisé pour proposer des inscriptions à un service.
* **[!UICONTROL Désinscription]** : ce modèle peut être lié à un email envoyé aux abonnés à un service afin de leur permettre de se désinscrire de celui-ci.
* **[!UICONTROL Liste bloquée]** : ce modèle doit être utilisé lorsqu’un profil ne souhaite plus être contacté par Campaign. Pour plus d’informations sur la gestion des listes bloquées, voir la section [À propos des processus d’opt-in et d’opt-out dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).s

Ces modèles sont proposés par défaut lors de la création d&#39;une nouvelle landing page.

![](assets/lp_creation_1.png)

Pour accéder aux modèles, cliquez sur le logo Adobe Campaign dans le coin supérieur gauche et sélectionnez **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de landing page]**.

>[!NOTE]
>
>Adobe vous recommande de créer vos propres modèles en dupliquant un modèle intégré. Certains paramètres peuvent seulement être définis dans les modèles de landing page et ne sont pas modifiables directement sur les landing pages.

Lors de la construction d&#39;un modèle, il est conseillé d&#39;ajouter un attribut **&#39;type&#39;** aux balises. Cette information sera interprétée par l&#39;éditeur et aidera l&#39;utilisateur à associer un champ de la base de données au champ du formulaire lors du paramétrage de l&#39;application Web.

Exemple de code HTML dans le modèle :

```
<input id="email" type="email" name="email"/>
```

La liste officielle des attributs &#39;type&#39; est disponible à l&#39;adresse suivante : [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)
