---
title: Fonctionnalités prédictives d’engagement client
description: Découvrez comment utiliser l’heure d’envoi et le scoring d’engagement prédictifs.
audience: sending
content-type: reference
topic-tags: ai-powered-emails
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: e1cb04e6-eb38-4bcc-b071-321cc11ccc7e
source-git-commit: 75628ed8a2f9b21def23e5b257a3592e1a721536
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 100%

---

# Fonctionnalités prédictives d’engagement client {#journey-ai}

Grâce à Campaign, vous pouvez optimiser la conception et la diffusion des parcours client afin de prédire les préférences d’engagement de chaque individu. Perfectionnés par l’IA et le machine learning, l’optimisation de l’heure d’envoi et le score prédictif de l’engagement d’Adobe Campaign peuvent analyser et estimer les taux d’ouverture, les heures d’envoi optimaux et l’attrition probable en fonction des mesures d’engagement historiques.

>[!IMPORTANT]
>
>Cette fonctionnalité ne fait pas partie des paramètres d’usine du produit. La mise en œuvre nécessite l’implication d’Adobe Consulting. Veuillez contacter votre représentant Adobe pour en savoir plus.

Adobe Campaign offre deux nouveaux modèles de machine learning : **optimisation prédictive de l’heure d’envoi** et **score prédictif de l’engagement**. Ces deux modèles sont des modèles d’apprentissage automatique spécifiques à la conception et à la diffusion de meilleurs parcours clients.

* **L’optimisation de l’heure d’envoi prédictive** estime la meilleure heure d’envoi pour chaque profil de destinataire en ce qui concerne les ouvertures d’e-mails ou les clics et les ouvertures de messages push. Pour chaque profil de destinataire, les scores indiquent la meilleure heure d’envoi pour chaque jour de la semaine et le jour de la semaine le plus approprié à l’envoi afin d’obtenir les meilleurs résultats.

* **Score prédictif de l’engagement** : estime la probabilité qu’un(e) destinataire interagisse avec un message, ainsi que la probabilité de se désinscrire dans les 7 jours suivant l’envoi du prochain e-mail. Les probabilités sont divisées en compartiments en fonction du niveau d’engagement estimé pour votre contenu : élevé, moyen ou faible. Ces modèles fournissent également le rang centile du risque de désabonnement pour les clients, afin de comprendre où se situe le rang d’un certain client par rapport aux autres.

## Optimisation de l’heure d’envoi prédictive{#predictive-send-time}

L’optimisation de l’heure d’envoi prédictive estime la meilleure heure d’envoi pour chaque profil de destinataire en ce qui concerne les ouvertures d’e-mails ou les clics et les ouvertures de messages push. Pour chaque profil de destinataire, les scores indiquent la meilleure heure d’envoi pour chaque jour de la semaine et le jour de la semaine le plus approprié à l’envoi afin d’obtenir les meilleurs résultats.

Dans le modèle d’optimisation de l’heure d’envoi prédictive, il existe deux sous-modèles :

* **L’heure d’envoi prédictive pour les ouvertures** est le meilleur moment pour envoyer une communication au client ou à la cliente afin de maximiser les ouvertures.

* **L’heure d’envoi prédictive pour les clics** est le meilleur moment pour envoyer une communication au client ou à la cliente afin de maximiser les clics.

**Entrée du modèle** : logs de diffusion, logs de tracking et attributs de profil (autres que PII)

**Sortie du modèle** : meilleur moment pour envoyer un message (pour les ouvertures et les clics)

Détails de la sortie

* Calcule la meilleure heure d’envoi de l’e-mail pendant les 7 jours de la semaine avec des intervalles d’une heure (p. ex. : 9 h, 10 h, 11 h).
* Le modèle indique le meilleur jour de la semaine et la meilleure heure de la journée.
* Chaque heure optimale est calculée deux fois : une fois pour maximiser le taux d’ouverture et une fois pour maximiser le taux de clics
* 16 champs sont proposés (14 pour les jours de la semaine et 2 pour toute la semaine) :

* Meilleure heure pour envoyer un e-mail afin d’optimiser les clics pour le lundi - Valeurs comprises entre 0 et 23.

* Meilleure heure pour envoyer un e-mail afin d’optimiser les ouvertures pour le lundi - Valeurs comprises entre 0 et 23.
* ...
* Meilleure heure pour envoyer un e-mail afin d’optimiser les clics pour le dimanche - Valeurs comprises entre 0 et 23.
* Meilleure heure pour envoyer un e-mail afin d’optimiser les ouvertures pour le dimanche - Valeurs comprises entre 0 et 23.
* ...
* Meilleur jour pour envoyer un e-mail afin d’optimiser les ouvertures pour toute la semaine - Du lundi au dimanche.
* Meilleure heure pour envoyer un e-mail afin d’optimiser les ouvertures pour toute la semaine - Valeurs comprises entre 0 et 23.

>[!NOTE]
>
>Le modèle nécessite au moins un mois de données pour produire des résultats significatifs.
>
>Ces fonctionnalités prédictives s’appliquent uniquement aux canaux e-mail et push.

Une fois mises en œuvre dans Campaign, les fonctionnalités de machine learning enrichissent les données des profils avec de nouveaux onglets contenant leurs meilleurs scores d’ouverture/de clic. Les mesures sont calculées et intégrées dans Campaign à l’aide de workflows techniques.

Pour accéder à ces mesures, vous devez effectuer les opérations suivantes :

1. Ouvrir un profil et cliquer sur le bouton Editer.

1. Cliquer sur l’onglet **Envoyer le score de l’heure par clic** ou **Envoyer le score de l’heure par ouverture**.

Par défaut, les scores du profil indiquent le meilleur moment de la journée pour chaque jour de la semaine et le meilleur moment général de la semaine.

![](assets/do-not-localize/SendTimeScore.png)

### Envoyer des messages au meilleur moment{#use-predictive-send-time}

Pour que les emails soient envoyés à l’heure optimale par profil, la diffusion doit être planifiée à l’aide de l’option **[!UICONTROL Envoyer à une date personnalisée définie par une formule]**.

Découvrez comment calculer la date d’envoi [dans cette section](../../sending/using/computing-the-sending-date.md).

La formule doit être renseignée avec le meilleur moment du jour donné où l’email sera envoyé.

![](assets/do-not-localize/ComputeSendingDate.png)

Exemple de formule :

```
AddHours([currentDelivery/scheduling/@contactDate],
[cusSendTimeScoreByClickprofile_link/@EMAIL_BEST_TIME_TO_CLICK_WEDNESDAY])
```

![](assets/do-not-localize/SendingDateFormula.png)

>[!NOTE]
>
>Le modèle de données peut être différent selon votre implémentation.

## Score prédictif de l&#39;engagement {#predictive-scoring}

Le score prédictif de l’engagement estime la probabilité qu’un(e) destinataire interagisse avec un message, ainsi que la probabilité de se désinscrire dans les 7 jours suivant l’envoi du prochain e-mail.

Les probabilités sont divisées en compartiments en fonction du niveau d’engagement estimé pour votre contenu : élevé, moyen ou faible. Ces modèles fournissent également le rang centile du risque de désabonnement pour les clients, afin de comprendre où se situe le rang d’un certain client par rapport aux autres.

Le score prédictif de l’engagement vous permet de :

* **Sélectionner une audience** : en utilisant l’activité de requête, vous pouvez sélectionner l’audience qui interagit avec un message spécifique.
* **Exclure une audience** : en utilisant l’activité de requête, vous pouvez supprimer l’audience la plus susceptible de se désinscrire.
* **Personnaliser** : personnalisez les messages en fonction du niveau d’engagement (les utilisateurs et utilisatrices à fort engagement recevront un message différent de celui des utilisateurs et utilisatrices à faible engagement).

Ce modèle utilise plusieurs scores pour indiquer :

* **Score d’engagement avec ouverture/Score d’engagement avec clic** : cette valeur correspond à la probabilité qu’un abonné interagisse avec un message spécifique (ouverture ou clic). Les valeurs sont comprises entre 0,0 et 1,0.
* **Probabilité de désabonnement** : cette valeur correspond à la probabilité pour le destinataire de se désabonner d’un canal email après l’ouverture d’un email. Les valeurs sont comprises entre 0,0 et 1,0.
* **Niveau de rétention** : cette valeur classe les utilisateurs et utilisatrices en trois niveaux : bas, moyen et élevé. Élevé indique que l’utilisateur est susceptible de rester fidèle à la marque et faible indique qu’il est susceptible de se désabonner.
* **Rang centile de rétention** : profil classé en termes de probabilité de désabonnement. Les valeurs sont comprises entre 0,0 et 1,0. Par exemple, si le rang de pourcentage de rétention est de 0,953, ce destinataire est plus susceptible de rester fidèle à la marque et moins susceptible de se désabonner que 95,3 % de tous les destinataires.

>[!NOTE]
>
>Ces fonctionnalités de prévision s’appliquent uniquement aux envois d’email.
>
>Le modèle nécessite au moins un mois de données pour produire des résultats significatifs.

**Entrée du modèle** : logs de diffusion, logs de tracking et attributs de profil spécifiques

**Sortie du modèle** : attribut de profil qui décrit le score et la catégorie du profil

Pour accéder à ces mesures, vous devez effectuer les opérations suivantes :

1. Ouvrir un profil et cliquer sur le bouton Editer.

1. Cliquer sur l’onglet **Scores d’engagement pour le canal email**.

En utilisant une activité de requête dans un workflow, vous pouvez utiliser le score pour optimiser votre audience. Par exemple, avec les critères de **niveau de rétention** :

![](assets/do-not-localize/predictive_score_query.png)