---
title: Retour à l'expéditeur
seo-title: Retour à l'expéditeur
description: Retour à l'expéditeur
seo-description: Découvrez comment être informé d'une adresse incorrecte et l'exclure des prochaines communications.
page-status-flag: never-activated
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: ht
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Retour à l'expéditeur{#return-to-sender}

Les échanges de fichiers plats avec les opérateurs de services postaux intégrant les informations de retour à l'expéditeur sont pris en charge. Les adresses postales correspondantes peuvent être ainsi exclues des communications futures. Vous pourrez également être averti si une adresse est incorrecte, interagir avec le client à travers d'autres canaux ou l'inciter à mettre à jour son adresse postale.

Par exemple, un contact a déménagé sans vous indiquer sa nouvelle adresse. L'opérateur récupère la liste des adresses erronées et l'envoie à Adobe Campaign qui blackliste automatiquement ces adresses.

Pour permettre cette fonctionnalité, le modèle de diffusion courrier par défaut inclut l'identifiant du log de diffusion au sein du contenu. Adobe Campaign peut ainsi synchroniser le profil et les données de diffusion avec les informations renvoyées par l'opérateur.

![](assets/direct_mail_return_sender_1.png)

Un modèle d'import est disponible sous **[!UICONTROL Adobe Campaign &gt; Ressources &gt; Modèles &gt; Modèles d'import &gt; Mettre à jour les logs de diffusion et les mises en quarantaine Courrier]**. Dupliquez ce modèle de manière à créer le vôtre. Pour plus d'informations sur l'utilisation des modèles d'import, voir [Utilisation des modèles d'import](../../automating/using/defining-import-templates.md).

![](assets/direct_mail_return_sender_2.png)

Une fois l'import effectué, Adobe Campaign réalise automatiquement les actions suivantes :

* Les adresses incorrectes sont blacklistées au niveau des profils.
* Les principaux indicateurs de diffusion (KPI) sont mis à jour.
* Les logs de diffusion sont mis à jour.

