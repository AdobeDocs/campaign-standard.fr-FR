---
title: Retour à l'expéditeur
description: Découvrez comment être informé d'une adresse incorrecte et l'exclure des prochaines communications.
page-status-flag: never-activated
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 100%

---


# Retour à l&#39;expéditeur{#return-to-sender}

Les échanges de fichiers plats avec les opérateurs de services postaux intégrant les informations de retour à l&#39;expéditeur sont pris en charge. Les adresses postales correspondantes peuvent être ainsi exclues des communications futures. Vous pourrez également être averti si une adresse est incorrecte, interagir avec le client à travers d&#39;autres canaux ou l&#39;inciter à mettre à jour son adresse postale.

Par exemple, un contact a déménagé sans vous indiquer sa nouvelle adresse. L’opérateur récupère la liste des adresses erronées et l’envoie à Adobe Campaign qui place automatiquement ces adresses dans la liste bloquée.

Pour permettre cette fonctionnalité, le modèle de diffusion courrier par défaut inclut l&#39;identifiant du log de diffusion au sein du contenu. Adobe Campaign peut ainsi synchroniser le profil et les données de diffusion avec les informations renvoyées par l&#39;opérateur.

![](assets/direct_mail_return_sender_1.png)

Un modèle d&#39;import est disponible sous **[!UICONTROL Adobe Campaign > Ressources > Modèles > Modèles d&#39;import > Mettre à jour les logs de diffusion et les mises en quarantaine Courrier]**. Dupliquez ce modèle de manière à créer le vôtre. Pour plus d&#39;informations sur l&#39;utilisation des modèles d&#39;import, voir [Utilisation des modèles d&#39;import](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Une fois l&#39;import effectué, Adobe Campaign réalise automatiquement les actions suivantes :

* Les adresses incorrectes sont ajoutées à la liste bloquée au niveau du profil.
* Les principaux indicateurs de diffusion (KPI) sont mis à jour.
* Les logs de diffusion sont mis à jour.
