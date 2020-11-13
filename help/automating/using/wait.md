---
title: Attente
description: L'activité Attente permet de suspendre momentanément l'exécution d'une partie d'un workflow.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '308'
ht-degree: 100%

---


# Attente{#wait}

## Description {#description}

![](assets/wait.png)

L&#39;activité **[!UICONTROL Attente]** permet de suspendre momentanément l&#39;exécution d&#39;une partie d&#39;un workflow. Elle active sa transition sortante après un délai pouvant aller de quelques secondes à plusieurs mois, permettant l&#39;exécution des activités placées à la suite.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Attente]** est utilisée pour permettre qu&#39;un certain temps s&#39;écoule entre l&#39;exécution de deux activités. Par exemple, attendre plusieurs jours après une activité de diffusion par email puis analyser les ouvertures et les clics générés pendant ce laps de temps avant d&#39;appliquer d&#39;autres traitements (email de rappel, création d&#39;audience, etc.).

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Attente]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Définissez la **[!UICONTROL Durée]** de l&#39;attente entre l&#39;activation de la transition entrante et l&#39;activation de la transition sortante de l&#39;activité.

   Vous pouvez saisir manuellement la durée ou utiliser le sélecteur disponible au niveau du champ.

   ![](assets/wait_duration.png)

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Exemple {#example}

L&#39;exemple suivant illustre l&#39;activité **[!UICONTROL Attente]** dans un cas typique. Un email d&#39;invitation à un événement est envoyé. 24 heures après l&#39;envoi, les journaux de la diffusion email sont analysés et un email de rappel est envoyé aux personnes ayant reçu le premier email mais qui ne se sont pas inscrits.

Le workflow se présente comme suit :

![](assets/wait_example_workflow.png)

* Une première **[!UICONTROL Requête]** permettant de cibler les profils à qui envoyer l&#39;email d&#39;invitation.
* Une **[!UICONTROL Diffusion email]** permettant d&#39;envoyer une première fois l&#39;invitation aux profils sélectionnés.
* Une **[!UICONTROL Attente]** de 24 h permettant d&#39;attendre entre l&#39;envoi de l&#39;invitation et la suite du workflow.
* Une seconde **[!UICONTROL Requête]** permettant de cibler les profils ayant reçus le premier email mais n&#39;ayant pas cliqué sur le lien d&#39;inscription à l&#39;intérieur.
* Une seconde **[!UICONTROL Diffusion email]** permettant d&#39;envoyer le rappel d&#39;invitation aux personnes sélectionnées.

