---
title: Attente
description: L'activité Attente permet de suspendre momentanément l'exécution d'une partie d'un workflow.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: wait,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2ddc1b2b-0df5-4c91-a381-451cc094f2eb
TQID: 'https://experienceleague.adobe.com/PnbExucfP9-JLJA-0krFYAkYXJYExhHxEl7TRu5efec'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 100%
---
# Attente{#wait}

## Description {#description}

![](assets/wait.png)

L&#39;activité **[!UICONTROL Attente]** permet de suspendre momentanément l&#39;exécution d&#39;une partie d&#39;un workflow. Elle active sa transition sortante après un délai pouvant aller de quelques secondes à plusieurs mois, permettant l&#39;exécution des activités placées à la suite.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Attente]** est utilisée pour permettre qu&#39;un certain temps s&#39;écoule entre l&#39;exécution de deux activités. Par exemple, attendre plusieurs jours après une activité de diffusion email puis analyser les ouvertures et les clics générés pendant ce laps de temps avant d&#39;appliquer d&#39;autres traitements (email de rappel, création d&#39;audience, etc.).

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Attente]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Définissez la **[!UICONTROL Durée]** de l&#39;attente entre l&#39;activation de la transition entrante et l&#39;activation de la transition sortante de l&#39;activité.

   Vous pouvez saisir manuellement la durée ou utiliser le sélecteur disponible au niveau du champ.

   ![](assets/wait_duration.png)

1. Validez le paramétrage de l’activité et enregistrez le workflow.

## Exemple {#example}

L’exemple suivant illustre l’activité **[!UICONTROL Attente]** dans un cas typique. Un e-mail d’invitation à un événement est envoyé. 24 heures après l&#39;envoi, les journaux de la diffusion email sont analysés et un email de rappel est envoyé aux personnes ayant reçu le premier email mais qui ne se sont pas inscrits.

Le workflow se présente comme suit :

![](assets/wait_example_workflow.png)

* Une première **[!UICONTROL Requête]** permettant de cibler les profils à qui envoyer l&#39;email d&#39;invitation.
* Une **[!UICONTROL Diffusion email]** permettant d&#39;envoyer une première fois l&#39;invitation aux profils sélectionnés.
* Une **[!UICONTROL Attente]** de 24 h permettant d&#39;attendre entre l&#39;envoi de l&#39;invitation et la suite du workflow.
* Une seconde **[!UICONTROL Requête]** permettant de cibler les profils ayant reçus le premier email mais n&#39;ayant pas cliqué sur le lien d&#39;inscription à l&#39;intérieur.
* Une seconde **[!UICONTROL Diffusion email]** permettant d&#39;envoyer le rappel d&#39;invitation aux personnes sélectionnées.
