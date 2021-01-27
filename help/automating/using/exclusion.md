---
solution: Campaign Standard
product: campaign
title: Exclusion
description: L'activité Exclusion permet d'exclure des éléments d'une population selon certains critères.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: exclusion,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 100%

---


# Exclusion{#exclusion}

## Description {#description}

![](assets/exclusion.png)

L&#39;activité **[!UICONTROL Exclusion]** permet d&#39;exclure des éléments d&#39;une population selon certains critères.

## Contexte d’utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Exclusion]** est essentiellement utilisée afin de réaliser un filtrage supplémentaire sur les populations des transitions entrantes.

Un ensemble principal est défini parmi les transitions entrantes. Les membres des autres transitions entrantes sont exclus de l&#39;ensemble principal. La transition sortante de l&#39;activité d&#39;exclusion contient uniquement les membres de l&#39;ensemble principal non rencontrés dans les autres transitions entrantes.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Exclusion]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Sélectionnez l&#39;**[!UICONTROL Ensemble principal]** parmi les transitions entrantes. C&#39;est l&#39;ensemble à partir duquel des éléments sont exclus. Les autres ensembles correspondent aux éléments devant être exclus de l&#39;ensemble principal.

   >[!NOTE]
   >
   >Les transitions entrantes doivent contenir le même type de population. Par exemple, si l&#39;ensemble principal contient des profils de test, les autres transitions doivent aussi contenir des profils de test.

1. Si besoin, gérez les [Transitions](../../automating/using/activity-properties.md) de l&#39;activité afin d&#39;accéder à des options avancées sur la population transmise en sortie.
1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Exemple {#example}

L&#39;exemple suivant montre le paramétrage de deux activités de requête visant à filtrer les profils de la base Adobe Campaign dont l&#39;âge est compris entre 18 et 27 ans et dont l&#39;adresse email n&#39;est pas valide. Ceux dont l&#39;email n&#39;est pas valide sont ensuite exclus du premier ensemble. Cela permet par exemple d&#39;envoyer un email par la suite.

![](assets/wkf_exclusion_example.png)

