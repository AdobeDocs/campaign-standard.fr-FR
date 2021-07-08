---
solution: Campaign Standard
product: campaign
title: FAQ sur les messages In-App
description: Foire aux questions sur la messagerie In-App
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: Dans l'application
role: Business Practitioner
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: 8e418be1fa880a4c23cbe4aa4e1a72fc4112b16b
workflow-type: ht
source-wordcount: '676'
ht-degree: 100%

---


# FAQ sur les messages In-App {#in-app-faq}

## Quelles sont les suggestions de ressources utiles pour en savoir plus sur le canal In-App dans Adobe Campaign Standard ?  {#resources-inapp}

Consultez les ressources ci-dessous :

* [Tutoriels vidéos](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html?lang=fr)
* [Article de blog](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [Page de la communauté](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Quel est l’objectif des API des extensions Campaign setLinkageField et resetLinkageField ?  {#extensions-apis}

Puisque les messages In-App sont extraits par le SDK de Campaign, nous voulons fournir un mécanisme sécurisé pour nous assurer que les messages In-App contenant des données de PII ne tombent pas entre des mains malveillantes. À ce titre, nous avons mis en place le mécanisme suivant pour assurer la diffusion sécurisée des messages vers l&#39;appareil :

* Les clients marquent les champs de profil mobile (table appSubscriberRcp) comme étant Personnels et sensibles s’ils veulent s’assurer que ces informations spécifiques soient diffusées en toute sécurité.
* Les champs marqués comme tels ne peuvent être utilisés que dans le modèle Profil (et non dans le modèle appSubscriber ou le modèle Broadcast) qui comporte un mécanisme de sécurité supplémentaire intégré.
* Les messages créés à l’aide d’un modèle Profil ne peuvent être diffusés que lorsque l’utilisateur s’est connecté à l’application.
* Afin de faciliter cette authentification sécurisée, les développeurs d’applications mobiles doivent transmettre des détails d’authentification supplémentaires à l’aide de l’API setLinkageField. Notez que les champs de liaison sont ceux qui sont identifiés comme le lien entre le Profil mobile et le Profil CRM lors de l&#39;extension de la table appSubscriberRcp.
* Ils doivent vider les messages In-App stockés sur l’appareil et resetLinkagefields lorsque l’utilisateur se déconnecte de l’application à l’aide de resetLinkageField. Ainsi, si un autre utilisateur se connecte à l’application, il ne voit pas les messages destinés à l’utilisateur précédent.
* Reportez-vous aux [API SDK Mobile](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference) pour mettre en œuvre ce mécanisme de sécurité côté client.

## Que dois-je faire pour activer le reporting In-App Campaign ?  {#enable-inapp-reporting}

Vous devez configurer le postback de tracking In-App. Les instructions se trouvent [ici](https://helpx.adobe.com/fr/campaign/kb/config-app-in-launch.html#InApptrackingpostback).

Pour mettre en œuvre le tracking des notifications locales, reportez-vous à cette [page](../../administration/using/local-tracking.md).

## Quels rapports sont disponibles pour le canal In-App ?  {#report-inapp}

Un rapport d’usine est disponible dans Adobe Campaign pour le canal In-App. Consultez cette [documentation](../../reporting/using/in-app-report.md).

Consultez cette [page](../../reporting/using/indicator-calculation.md#in-app-delivery) pour comprendre comment est calculée chaque mesure In-App.

## Prenez-vous en charge des variantes de contenu multilingues pour In-App similaires à push ?  {#multilingual-inapp}

Aucun modèle multilingue n’est actuellement disponible pour les messages In-App.

Cependant, si l’objectif est d’envoyer un message In-App dans une langue autre que l’anglais, le contenu peut être directement collé dans les zones de texte disponibles.

![](assets/faq_inapp.png)

## Les champs de personnalisation Campaign peuvent-ils être ajoutés au code HTML personnalisé ?  {#custom-html-inapp}

Non, cela n’est pas encore pris en charge.

## J’ai configuré un message d’alerte mais il ne s’affiche pas sur l’appareil. {#alert-message}

Pour les messages d’alerte, au moins un bouton Ignorer (un bouton principal ou secondaire doit avoir une action Ignorer) est requis. Sinon, il est possible d’enregistrer le message mais il ne sera pas reçu.

## Si le son personnalisé iOS des notifications locales n’est pas lu, le son par défaut sera-t-il lu à la place ?  {#local-notification-sound}

Pour le son personnalisé sur iOS, vous devez fournir un nom de fichier avec son extension lors de la création d’une notification locale (par exemple, sound.caf). Si cette extension n&#39;est pas indiquée, le son par défaut est utilisé.

## Les URL de lien profond sont-elles prises en charge dans les messages In-App ?  {#inapp-deeplinks}

Oui, les URL de lien profond sont prises en charge dans les messages In-App. Les liens profonds doivent inclure les éléments suivants :

* Un langage indiquant que le tracking des diffusions doit être désactivé pour que les URL de lien profond fonctionnent.
* Apflyer avec Branch en tant que partenaires pouvant effectuer le tracking de liens profonds. Pour plus d&#39;informations sur l&#39;intégration de Branch et Adobe Campaign Standard, consultez cette [page](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## Un message In-App peut-il être déclenché lorsque l’utilisateur lance l’application à partir d’une notification push ?  {#inapp-push-trigger}

Oui, ces messages sont aussi appelés des messages en daisy chain. Suivez les étapes suivantes :

1. Créez un message In-App.

1. Définissez un événement personnalisé et sélectionnez-le en tant que déclencheur d’événement pour cet IAM, par exemple « Déclencheur du push de prévisualisation d’automne ».

1. Lors de la création de votre message push, définissez une variable personnalisée dont la valeur peut être définie comme un événement utilisé pour déclencher IAM, par exemple Clé = « inappkey » et Valeur = « Déclencheur du push de prévisualisation d’automne ».

1. Dans le code de l’application mobile, mettez en œuvre le déclencheur d’événement comme suit :

   ![](assets/faq_inapp_2.png)
