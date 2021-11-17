---
title: Guide de Campaign Standard Mobile
description: Découvrez les instructions générales concernant les diffusions mobiles dans Adobe Campaign Standard, telles que la configuration de vos applications mobiles ou la création de notifications push et de messages In-App.
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 94%

---

# Prise en main des canaux mobiles {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>Découvrez comment configurer votre application mobile pour les notifications push </br><a href="#configuration-push">Cliquez ici</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>Découvrez comment configurer votre application mobile pour les messages In-App </br><a href="#configuring-mobile-app">Cliquez ici</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>Découvrez comment créer des notifications push </br><a href="#create-push">Cliquez ici</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>Découvrez comment créer des messages In-App</br><a href="#create-inapp">Cliquez ici</a></p></td></tr>
</table>

## À propos de la diffusion mobile {#about-mobile}

Adobe Campaign permet de créer et d&#39;envoyer des messages personnalisés sur différents canaux et d&#39;en mesurer l&#39;efficacité au travers de rapports dédiés.

Avec Adobe Campaign Standard, vous pouvez envoyer des diffusions mobiles par le biais de trois canaux différents :

* SMS, canal présenté dans la section À propos des SMS.
* Notifications push, canal présenté dans la section À propos des notifications push.
* Messages In-App, canal présenté dans la section À propos des messages In-App.

## Configuration de votre application mobile pour les notifications push {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configuration d’une application mobile à l’aide des SDK Adobe Experience Platform</strong></p>
    </div>
    <p>Pour envoyer des messages In-App et des notifications push, les applications mobiles doivent être configurées dans Adobe Campaign en utilisant les SDK Adobe Experience Platform.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Présentation de la structure de la payload des notifications push Campaign Standard</strong></p>
    </div>
    <p>Apprenez-en davantage sur la structure de la payload reçue dans une application mobile lorsqu'une notification push est envoyée avec succès à une application à partir d'Adobe Campaign Standard.</br><a href="../../administration/using/push-payload.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Implémentation du tracking des notifications locales</strong></p>
    </div>
    <p>Découvrez ici comment vérifier que le tracking des notifications locales a été correctement implémenté. </br><a href="../../administration/using/local-tracking.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implémentation du tracking des notifications push</strong></p>
    </div>
    <p>Découvrez comment vérifier que le tracking des notifications push a été correctement implémenté sur iOS et Android.</br><a href="../../administration/using/push-tracking.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
</tr>
</table>

## Configuration d&#39;une application mobile pour les messages In-App {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configuration d’une application mobile à l’aide des SDK Adobe Experience Platform</strong></p>
    </div>
    <p>Pour envoyer des messages In-App et des notifications push, les applications mobiles doivent être configurées dans Adobe Campaign en utilisant les SDK Adobe Experience Platform.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Cas pratiques mobiles pris en charge à l'aide des SDK Adobe Experience Platform</strong></p>
    </div>
    <p>Découvrez les cas pratiques mobiles pris en charge dans Adobe Campaign Standard en utilisant les SDK Adobe Experience Platform.</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Configuration des règles d'Adobe Experience Platform Launch pour la prise en charge des cas pratiques Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>Cliquez ici</strong></a> pour commencer à créer des éléments de données et des règles dans Adobe Experience Platform Launch afin d'envoyer des informations PII et d'autres données des applications mobiles vers Adobe Campaign Standard.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implémentation du tracking des notifications locales</strong></p>
    </div>
    <p>Découvrez ici comment vérifier que le tracking des notifications locales a été correctement implémenté. </br><a href="../../administration/using/local-tracking.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
</tr>
</table>

## Création d’une notification push {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Préparation et envoi d'une notification push</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>Découvrez ici</strong></a> comment préparer votre notification push et l'envoyer ensuite à votre audience ciblée.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personnalisation d’une notification push</strong></p>
    </div>
    <p>Pour parfaire votre diffusion, Adobe Campaign vous permet d'accéder à un ensemble d'options lors de la création d'une notification push.</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Création d'une notification push multilingue</strong></p>
    </div>
    <p>Personnalisez le contenu des notifications push en envoyant des messages selon les préférences linguistiques et de zone géographique des utilisateurs.</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Affichage d’une image à partir d’une notification push Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>Découvrez ici comment afficher une image à partir d’une notification push Adobe Campaign Standard sur un appareil iOS.</strong></a></p>
    <br>
  </td>
</tr>
</table>

## Création d’un message In-App {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Préparation et envoi d'un message In-App</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>Découvrez ici</strong></a> comment préparer vos messages In-App et les envoyer ensuite à votre audience ciblée.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personnalisation de vos messages In-App</strong></p>
    </div>
    <p>Pour parfaire votre diffusion, Adobe Campaign vous permet d'accéder à un ensemble d'options avancées lors de la création d'un message In-App.</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Personnalisation d’un type de message de notification locale</strong></p>
    </div>
    <p>Les notifications locales peuvent uniquement être déclenchées par une application à une heure spécifique et en fonction d’un événement. </br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Rapport In-App</strong></p>
    </div>
    <p>Le rapport In-App fournit des détails liés aux diffusions In-App.</br><a href="../../reporting/using/in-app-report.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
</tr>
</table>

## Création de SMS {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Créer un SMS</strong></p>
    </div>
    <p>La création d'une diffusion SMS est très similaire à celle d'un email classique. </br>Les étapes <a href="../../channels/using/creating-an-sms-message.md"><strong>détaillées ici</strong></a> présentent la configuration qui est spécifique à ce canal.</br></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personnalisation d’un SMS
</strong></p>
    </div>
    <p>Pour parfaire votre diffusion, Adobe Campaign vous permet d'accéder à un ensemble d'options avancées lors de la création d'un SMS.</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>Cliquez ici pour plus d'informations.</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong></p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Gestion des SMS entrants</strong></p>
    </div>
    <p>Lorsqu'un profil répond à un SMS qui a été envoyé via Campaign, vous pouvez configurer les messages qui lui sont automatiquement renvoyés, ainsi que l'action à effectuer. Personnaliser un type de message de notification locale</br><a href="../../channels/using/managing-incoming-sms.md"><strong>Cliquez ici pour plus d’informations.</br><a href="../../channels/using/managing-incoming-sms.md"><strong></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Rapport SMS</strong></p>
    </div>
    <p>Le rapport SMS fournit des détails sur les diffusions SMS tels que les débits de diffusion et les taux de bounce.</br><a href="../../reporting/using/sms-report.md"><strong>Cliquez ici</strong></a> pour plus d'informations.</p>
    <br>
  </td>
</tr>
</table>

## Résolution des problèmes mobiles {#mobile-troubleshooting}

Les pages suivantes permettent de résoudre les problèmes les plus courants qui se produisent lors de l&#39;utilisation de la diffusion mobile dans Adobe Campaign Classic.

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>FAQ sur les notifications push</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>Cliquez ici pour plus d'informations.</p>
  </td>
  <td>
    <div>
    <p><strong>FAQ sur la synchronisation d'Adobe Launch</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>Cliquez ici pour plus d'informations.</p>
  </td>
  <td>
    <div>
    <p><strong>FAQ sur les messages In-App</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>Cliquez ici pour plus d'informations.</p>
  </td>
</tr>
</table>
