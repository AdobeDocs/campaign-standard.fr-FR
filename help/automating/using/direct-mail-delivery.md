---
solution: Campaign Standard
product: campaign
title: Diffusion courrier
description: L'activité Diffusion courrier permet de paramétrer l'envoi d'un courrier unique ou récurrent dans un workflow.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: directMail,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 100%

---


# Diffusion courrier{#direct-mail-delivery}

## Description {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

L&#39;activité **[!UICONTROL Diffusion courrier]** permet de configurer et de préparer un fichier contenant les données de profil que vous souhaitez utiliser pour une campagne courrier. Il peut s’agir d’un courrier unique qui n’est envoyé qu’une seule fois ou d’un courrier récurrent.

* **Les courriers classiques ne sont envoyés qu’une seule fois.**
* **Les courriers récurrents permettent d’envoyer plusieurs fois sur une période définie un même courrier à des cibles différentes.** Vous pouvez agréger les diffusions par période afin d’obtenir des rapports adaptés.

## Contexte d&#39;utilisation {#context-of-use}

En règle générale, l&#39;activité **[!UICONTROL Diffusion courrier]** est utilisée pour automatiser la préparation d&#39;un fichier contenant des données de profil. Ce fichier peut ensuite être envoyé à un partenaire/prestataire en charge de l&#39;envoi.

Lorsque la diffusion courrier est associée à un planificateur, il est possible de définir des courriers de type récurrent.

Les destinataires du courrier sont définis en amont de l&#39;activité dans le même workflow, grâce à des activités de ciblage telles que requêtes, intersections, etc. Les profils dont l&#39;adresse postale n&#39;est pas renseignée sont automatiquement exclus lors de la préparation du courrier.

La préparation du message est déclenchée selon les paramètres d&#39;exécution du workflow. Depuis le tableau de bord du message, vous pouvez choisir de demander ou non une confirmation manuelle pour envoyer le message (requise par défaut). Vous pouvez lancer manuellement le workflow ou bien placer une activité de planification afin d&#39;en automatiser l&#39;exécution.

**Rubriques connexes :**

* [Cas pratique : diffusions conjointes d’emails et de courriers](../../automating/using/coupling-email-direct-mail.md)
* [A propos du canal Courrier](../../channels/using/about-direct-mail.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Diffusion courrier]** dans votre workflow.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.

   >[!NOTE]
   >
   >Les propriétés générales et les options avancées de l&#39;activité (et non de la diffusion elle-même) sont disponibles à l&#39;aide du bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité. Ce bouton est spécifique aux activités de ce canal. Les propriétés du courrier sont disponibles via la barre d&#39;actions du tableau de bord du courrier.

1. Sélectionnez le mode d&#39;envoi du courrier :

   * **[!UICONTROL Courrier]** : le courrier est envoyé une seule fois. Vous pouvez définir à cet endroit si vous souhaitez ou non ajouter une transition en sortie de l&#39;activité. Les différents types de transition sont détaillés à l&#39;étape 7 de cette procédure.
   * **[!UICONTROL Courrier récurrent]** : le courrier est envoyé plusieurs fois, à une fréquence définie dans une activité **[!UICONTROL Planificateur]**. Choisissez la période d&#39;agrégation des envois. Cela permet de regrouper tous les envois ayant eu lieu dans la période définie dans un seul courrier, aussi appelé **exécution récurrente** et accessible depuis la liste des activités marketing de l&#39;application.

      Par exemple, pour un courrier récurrent d&#39;anniversaire, traité chaque jour, vous pouvez choisir d&#39;agréger les envois par mois. Vous obtiendrez ainsi des rapports sur votre diffusion mois par mois alors que le courrier est traité chaque jour.

      >[!NOTE]
      >
      >Pour les courriers récurrents, un nouveau fichier est généré à chaque exécution du workflow. La période d&#39;agrégation sélectionnée n&#39;a aucun impact sur ce comportement.

1. Sélectionnez un type de courrier. Les types de courrier sont issus des modèles définis dans le menu **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]**.
1. Renseignez les propriétés générales du courrier. Vous pouvez également rattacher l&#39;activité à une campagne existante. Le libellé de l&#39;activité de diffusion dans le workflow est mis à jour avec le libellé du courrier.
1. Définissez le contenu du courrier. Consultez la section concernant l&#39;[édition de contenu](../../designing/using/personalization.md).
1. Par défaut, l&#39;activité **[!UICONTROL Diffusion courrier]** ne possède aucune transition sortante. Si vous souhaitez ajouter une transition sortante à votre activité de **[!UICONTROL Diffusion courrier]**, accédez à l&#39;onglet **[!UICONTROL Général]** des options avancées de l&#39;activité (bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité), puis cochez l&#39;une des options suivantes :

   * **[!UICONTROL Ajouter une transition sortante sans la population]** : permet de générer une transition sortante contenant la même population que la transition entrante. Cette transition contient le fichier généré par l&#39;activité Diffusion courrier et la population initiale reçue par l&#39;activité Diffusion courrier.
   * **[!UICONTROL Ajouter une transition sortante avec la population]** : permet de générer une transition sortante contenant la population à qui le courrier sera envoyé. La population ciblée exclue pendant la préparation du courrier (quarantaine, adresses non valides, etc.) est exclue de cette transition. La transition contient également le fichier généré par le courrier.

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

Lorsque vous ouvrez à nouveau l&#39;activité par la suite, vous accédez au tableau de bord du courrier. Seul son contenu reste modifiable.

Par défaut, le démarrage d&#39;un workflow de diffusion déclenche uniquement la préparation des messages. L&#39;envoi des messages créés depuis un workflow doit toujours être confirmé après le démarrage du workflow. Dans le tableau de bord des messages, vous pouvez toutefois désactiver l&#39;option **[!UICONTROL Demander confirmation avant d&#39;envoyer les messages]** si les messages ont été créés depuis un workflow. Lorsque cette option est décochée, les messages sont envoyés sans autre préavis une fois la préparation terminée.

## Remarques       {#remarks}

Les diffusions créées à partir d&#39;un workflow sont accessibles dans la liste des activités marketing de l&#39;application. Vous pouvez visualiser l&#39;état d&#39;exécution du workflow depuis le tableau de bord. Des liens dans le volet de résumé du courrier vous permettent d&#39;accéder directement aux éléments liés (workflow, campagne, diffusion parente dans le cas d&#39;un courrier récurrent).

![](assets/wkf_display_parent_elements_direct_mail.png)

Les exécutions des diffusions récurrentes sont masquées par défaut. Pour les afficher, cochez l&#39;option **[!UICONTROL Afficher les exécutions récurrentes]** dans le volet de recherche des activités marketing.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

Depuis les diffusions parentes, accessibles depuis la liste des activités marketing ou directement via les exécutions récurrentes associées, vous pouvez visualiser l&#39;ensemble des courriers ayant été traités (en fonction de la période d&#39;agrégation définie lors du paramétrage de l&#39;activité de **[!UICONTROL Diffusion courrier]**). Pour cela, accédez au détail du bloc **[!UICONTROL Déploiement]** de la diffusion parente en sélectionnant le bouton ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
