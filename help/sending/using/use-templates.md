---
title: Utiliser des modèles de diffusion
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: true
description: Les modèles de diffusion accroissent l’efficacité en offrant des configurations prêtes à l’emploi pour les types d’activité les plus courants.
feature: Deliverability
role: User
level: Intermediate
exl-id: ca134a7f-9035-4885-b4cb-1170b6ec10cc
source-git-commit: ac925ec5f59f1bb57b56b430fd175a27b08c3bfe
workflow-type: ht
source-wordcount: '838'
ht-degree: 100%

---

# Utilisation de modèles {#use-templates}

Les modèles de diffusion accroissent l’efficacité en offrant des configurations prêtes à l’emploi pour les types d’activité les plus courants. Grâce aux modèles, les spécialistes marketing peuvent déployer plus rapidement de nouvelles campagnes avec une personnalisation minimale.

En savoir plus sur les modèles de diffusion dans [cette section](../../start/using/marketing-activity-templates.md).

## Prise en main des modèles de diffusion {#gs-templates}

Un [modèle de diffusion](../../start/using/marketing-activity-templates.md#creating-a-new-template) vous permet de définir une fois un ensemble de propriétés techniques et fonctionnelles qui répond à vos besoins et qui peut être réutilisé pour de prochaines diffusions. Vous pouvez ensuite gagner du temps et normaliser les diffusions si nécessaire.

Si vous gérez plusieurs marques dans Adobe Campaign, Adobe recommande de disposer d’un sous-domaine par marque. Une banque peut, par exemple, avoir plusieurs sous-domaines qui correspondent à chacune de ses agences régionales. Si une banque possède le domaine bluebank.com, ses sous-domaines peuvent être @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, etc. Disposer d’un modèle de diffusion par sous-domaine vous permet de toujours utiliser les paramètres préconfigurés adéquats pour chaque marque et d’éviter ainsi des erreurs tout en gagnant du temps.

**Conseil** : afin d’éviter toute erreur de paramétrage dans Campaign, il est recommandé de dupliquer un modèle natif et d’en modifier les propriétés plutôt que d’en créer un nouveau.

## Configurer les adresses

* L&#39;adresse de l&#39;expéditeur est obligatoire pour permettre l&#39;envoi d&#39;un email.

* Certains FAI vérifient la validité de l’adresse de l’expéditeur avant d’accepter les messages.

* Une adresse erronée peut causer un refus de la part du serveur receveur. Vous devez vous assurer qu’une adresse correcte est bien renseignée.

* L’adresse doit identifier explicitement l’expéditeur ou l’expéditrice.Le domaine doit appartenir à l’expéditeur ou à l’expéditrice et être enregistré en son nom.

* Adobe recommande de créer des comptes e-mail qui correspondent aux adresses indiquées pour les diffusions et les réponses.Parlez-en avec l’administrateur ou l’administratrice de votre messagerie.

Dans la section **[!UICONTROL Paramètres avancés]** des propriétés d’un modèle d’e-mail, le champ **[!UICONTROL De (adresse e-mail)]** correspond à l’adresse de l’expéditeur ou de l’expéditrice.

![](assets/template-parameters.png)

Le domaine de l&#39;adresse doit être identique au sous-domaine que vous avez configuré.

Les champs **[!UICONTROL Répondre à]** correspondent à l&#39;adresse email et au nom utilisés pour les réponses.

**Conseil** : Adobe recommande toutefois d’utiliser une adresse réelle existante, comme l’assistance clientèle de votre marque.Ainsi, si une personne destinataire envoie une réponse, l’assistance clientèle sera en mesure de la traiter.

Pour modifier le nom de l’expéditeur ou de l’expéditrice qui apparaîtra dans l’en-tête des messages envoyés, accédez à l’onglet **[!UICONTROL Propriétés]** de la page d’accueil du concepteur d’e-mail (accessible par le biais de l’icône Accueil) et cliquez sur le bloc **[!UICONTROL Nom de l’expéditeur ou de l’expéditrice par défaut]**.

![](assets/template-content.png)

Pour accroître le taux d&#39;ouverture de vos diffusions, Adobe vous recommande d&#39;utiliser un nom facilement identifiable par les destinataires comme le nom de votre marque.

**Conseil** : pour améliorer davantage l&#39;expérience des destinataires, vous pouvez ajouter le nom d&#39;une personne, par exemple « Emma de Megastore ».

Pour plus d&#39;informations sur la personnalisation du nom de l&#39;expéditeur, voir [Expéditeur d&#39;un email](../../designing/using/subject-line.md#email-sender).

## Personnaliser le nom de l&#39;expéditeur de SMS

Dans la section **Paramètres avancés** des propriétés d’un modèle de SMS, l’option **De** vous permet de personnaliser le nom de la personne qui envoie le SMS à l’aide d’une chaîne de caractères.C’est le nom qui s’affichera dans le champ correspondant à l’expéditeur ou l’expéditrice du SMS sur le téléphone mobile de la personne destinataire.

Si ce champ est vide, c’est le numéro source renseigné dans le compte externe qui sera utilisé.Si aucun numéro source n’y figure, c’est le numéro court qui sera utilisé.Pour plus d’informations, consultez la section [Configuration des SMS](../../administration/using/configuring-sms-channel.md).

**Conseil** : vérifiez la loi en vigueur dans votre pays concernant la modification de l’adresse d’expédition.Vérifiez également auprès de votre fournisseur de service SMS s’il propose cette fonctionnalité.

## Configurer une population témoin

Une fois que la diffusion est envoyée, vous pouvez comparer le comportement des destinataires exclus à celui des destinataires qui ont reçu la diffusion. Vous pouvez ensuite mesurer l’efficacité de vos campagnes. En savoir plus sur les populations témoins dans [cette section](../../sending/using/control-group.md).

## Utiliser des typologies pour appliquer des filtres ou des règles de contrôle

Une typologie contient les règles de vérification qui sont appliquées lors de la phase d’analyse, avant tout envoi.

Dans la section **[!UICONTROL Paramètres avancés]** > **[!UICONTROL Préparation]** des propriétés du modèle, changez la typologie par défaut en fonction de vos besoins.

Pour mieux contrôler le trafic sortant, par exemple, vous pouvez définir quelles adresses IP peuvent être utilisées en spécifiant une affinité par sous-domaine et en créant une typologie par affinité.Celles-ci sont définies dans le fichier de configuration de l’instance.Contactez votre administrateur ou administratrice Adobe Campaign.

Pour plus d’informations sur les typologies, consultez [cette section](../../sending/using/managing-typologies.md).

## Associer une marque à un modèle

Les paramètres des e-mails envoyés relatifs à l’identité d’une marque (le logo de la marque et l’adresse d’expédition, par exemple) sont gérés de manière centralisée dans Adobe Campaign.Vous pouvez créer une ou plusieurs marques et les associer à des modèles de diffusion.

Pour plus d&#39;informations sur l&#39;utilisation et la configuration des marques dans Adobe Campaign, voir Marques.

Pour afficher ou modifier la marque affectée à un modèle de diffusion, cliquez sur le bouton Editer les propriétés du modèle et accédez aux détails de la marque.

![](assets/template-brand.png)

Pour plus d&#39;informations sur l&#39;association d&#39;une marque à un modèle, voir [Affecter une marque à un email](../../administration/using/branding.md#assigning-a-brand-to-an-email).

Découvrez comment créer et configurer une marque [dans cette section](../../administration/using/branding.md#creating-a-brand).
