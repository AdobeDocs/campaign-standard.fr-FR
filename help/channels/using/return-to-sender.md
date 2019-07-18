---
title: Retour à l'expéditeur
seo-title: Retour à l'expéditeur
description: Retour à l'expéditeur
seo-description: Découvrez comment être informé d'une adresse incorrecte et l'exclure des prochaines communications.
page-status-flag: jamais activé
uuid: 11981 c 2 f -0 b 7 f -4166-9 daa-ec 6 a 6 b 4 d 5367
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canaux
content-type: référence
topic-tags: courrier direct
discoiquuid: 5 f 20 ff 3 f -8242-4735-8 c 60-c 57610 edff 52
internal: n
snippet: y
translation-type: tm+mt
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

