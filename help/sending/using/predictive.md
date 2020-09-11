---
title: Fonctionnalités d’engagement prédictives des utilisateurs
description: Découvrez comment utiliser le temps d’envoi prédictif et le score d’engagement.
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: ai-powered-emails
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: acaa07b3e40d0bcbf7c44f866ede141b992015a1
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---


# Optimisation de la conception et de la diffusion avec les courriers électroniques optimisés par IA{#journey-ai}

## Get started with AI-powered emails{#journey-ai-ovv}

Grâce à Campaign, vous pouvez optimiser la conception et la diffusion des voyages des clients afin de prédire les préférences d’engagement de chaque individu. Optimisé par l’IA de parcours, Adobe Campaign peut analyser et estimer les taux d’ouverture, les temps d’envoi optimaux et l’attrition probable en fonction des mesures d’engagement historiques.

**Modèles d&#39;apprentissage automatique**

adobe campaign standard offre deux nouveaux modèles d&#39;apprentissage automatique : **Optimisations** de temps d’envoi prédictive et score **d’engagement** prédictif. Ces deux modèles sont ensemble appelés Journey AI qui est une classe de modèles d&#39;apprentissage automatique qui sont spécifiques à la conception et à la prestation de meilleurs voyages client.

* **Optimisation** prédictive du temps d&#39;envoi : L’optimisation prédictive de l’heure d’envoi prédit la meilleure heure d’envoi pour chaque profil destinataire pour les ouvertures ou les clics par courrier électronique. Pour chaque profil de destinataire, les scores indiquent la meilleure heure d’envoi pour chaque jour de la semaine et le jour de semaine le plus approprié à envoyer pour obtenir les meilleurs résultats.

* **Évaluation** prédictive de l’engagement : Le score d’engagement prédictif prédit la probabilité qu’un destinataire s’engage avec un message, ainsi que la probabilité de s’exclure (de se désabonner) dans les 7 jours qui suivent l’envoi du prochain courrier électronique. Les probabilités sont divisées en compartiments selon le risque spécifique de désengagement, moyen ou faible. Le modèle permet également aux clients de déterminer le niveau de risque par rapport aux autres.

>[!CAUTION]
>Cette fonctionnalité n&#39;est pas disponible en standard dans le cadre du produit. La mise en oeuvre nécessite l’engagement de Adobes Consulting. Veuillez contacter votre représentant Adobe pour en savoir plus.
>
>Séparément, la fonction exigeait l&#39;utilisation d&#39;un enregistrement Azure qui doit être fourni par le client.

## Predictive send time optimization{#predictive-send-time}

### Optimiser les clics et les ouvertures{#about-predictive-send-time}

L’optimisation prédictive de l’heure d’envoi prédit la meilleure heure d’envoi pour chaque profil destinataire pour les ouvertures et les clics de courrier électronique. Pour chaque profil de destinataire, les scores indiquent la meilleure heure d’envoi pour chaque jour de la semaine et le jour de semaine le plus approprié à envoyer pour obtenir les meilleurs résultats.

Dans le modèle d’optimisation du temps d’envoi prédictif, il existe deux sous-modèles :
* Le délai d&#39;envoi anticipé pour l&#39;ouverture est le meilleur moment pour envoyer une communication au client afin d&#39;optimiser les ouvertures
* Le temps d&#39;envoi prédictif des clics est le meilleur moment pour envoyer une communication au client afin d&#39;optimiser les clics

**Entrée** du modèle : Attributs de logs de diffusion, de logs de tracking et de profil (non PII)

**Sortie** du modèle : Meilleur moment pour envoyer un message (pour les ouvertures et les clics)


Détails de la sortie

* Calculez la meilleure heure d&#39;envoi du courriel pendant les 7 jours de la semaine avec des intervalles d&#39;une heure (p. ex. : 9 h, 10 h, 11 h)
* Le modèle indique le meilleur jour de la semaine et la meilleure heure de la journée.
* Chaque heure optimale est calculée deux fois : une fois pour maximiser le taux ouvert et une fois pour maximiser le taux de clics
* 16 champs sont indiqués (14 pour les jours de la semaine et 2 pour toute la semaine) :
   * meilleur moment pour envoyer un courriel afin d’optimiser les clics pour le lundi - valeurs comprises entre 0 et 23
   * meilleur moment pour envoyer un courriel pour optimiser les ouvertures du lundi - valeurs comprises entre 0 et 23
   * meilleur moment pour envoyer un courriel afin d’optimiser les clics pour le mardi - valeurs comprises entre 0 et 23
   * ...
   * meilleur moment pour envoyer un courriel afin d’optimiser les clics pour le dimanche - valeurs comprises entre 0 et 23
   * meilleur moment pour envoyer un courriel afin d’optimiser les ouvertures pour le dimanche - valeurs comprises entre 0 et 23
   * ...
   * meilleure journée pour envoyer un courriel afin d&#39;optimiser les ouvertures pour toute la semaine - du lundi au dimanche
   * meilleur moment pour envoyer un courriel afin d’optimiser les ouvertures pour toute la semaine - valeurs comprises entre 0 et 23

>[!NOTE]
>
>Ces fonctionnalités de prévision s’appliquent uniquement aux diffusions de messagerie électronique.
>
>Le modèle nécessite au moins un mois de données pour produire des résultats significatifs.


### Accéder aux scores du profil{#access-predictive-send-time-scores}

Une fois mise en oeuvre dans Campaign, les capacités d’apprentissage automatique enrichissent les données des profils avec de nouveaux onglets avec leurs meilleurs scores d’ouverture/clic. Les mesures sont calculées par Journey AI et elles sont introduites dans Campaign à l&#39;aide de workflows techniques.

Pour accéder à ces mesures, vous devez :

1. Ouvrez un profil et cliquez sur le bouton Modifier.

1. Cliquez sur l’onglet **Envoyer la note temporelle par clic** ou **Envoyer la note temporelle par ouverture** .

Par défaut, les scores du profil indiquent le meilleur moment de la journée pour chaque jour de la semaine et le meilleur moment global de la semaine.

![](assets/do-not-localize/SendTimeScore.png)

### Envoyer des messages au meilleur moment{#use-predictive-send-time}

Pour que les courriers électroniques sortent à l’heure optimale par profil, la diffusion doit être planifiée à l’aide de l’option **[!UICONTROL Envoyer à une date personnalisée définie par une formule]**.
Découvrez comment calculer la date d&#39;envoi [dans cette section](../../sending/using/computing-the-sending-date.md).

La formule doit être renseignée avec le meilleur moment du jour donné où la diffusion sortira.

![](assets/do-not-localize/ComputeSendingDate.png)

Exemple de formule :

```
AddHours([currentDelivery/scheduling/@contactDate], 
[cusSendTimeScoreByClickprofile_link/@EMAIL_BEST_TIME_TO_CLICK_WEDNESDAY])
```

![](assets/do-not-localize/SendingDateFormula.png)

>[!NOTE]
>
>Le modèle de données peut être différent selon votre implémentation.



## Évaluation prédictive de l’engagement {#predictive-scoring}

Le score d’engagement prédictif vous permet d’effectuer les opérations suivantes :

* **Sélectionnez une audience**: en utilisant l’activité de requête, vous pouvez sélectionner l’audience à utiliser pour un message spécifique.
* **Exclure une audience**: en utilisant l’activité de requête, vous pouvez supprimer l’audience de désabonnement.
* **Personnaliser**: personnaliser le message en fonction du niveau d’engagement (les utilisateurs très engagés recevront un message différent de celui des utilisateurs non engagés).

Ce modèle utilise plusieurs scores pour indiquer :

* **Ouvrez Score d’engagement / Cliquez sur Score** d’engagement : cette valeur correspond à la probabilité qu’un abonné interagisse avec un message spécifique (ouvrez ou cliquez). Les valeurs sont comprises entre 0,0 et 1,0.
* **Probabilité** de désinscription : cette valeur correspond à la probabilité pour le destinataire de se désabonner d’un canal de courriel à condition qu’un seul courriel soit ouvert. Les valeurs sont comprises entre 0,0 et 1,0.
* **Niveau** de rétention :  cette valeur classe les utilisateurs en trois niveaux : bas, moyen et élevé. Elevé étant le plus susceptible de rester avec la marque et faible valeur susceptible de se désabonner.
* **Rang de pourcentage de rétention**: profil classé en termes de probabilité de désinscription. Les valeurs sont comprises entre 0,0 et 1,0. Par exemple, si le pourcentage de rétention est de 0,953, ce destinataire est plus susceptible de rester avec la marque et moins susceptible de se désabonner que 95,3 % de tous les destinataires.

>[!NOTE]
>
>Ces fonctionnalités de prévision s’appliquent uniquement aux diffusions de messagerie électronique.
>
>Le modèle nécessite au moins un mois de données pour produire des résultats significatifs.


**Entrée** du modèle : Logs de diffusion, logs de tracking et attributs de profil spécifiques

**Sortie** du modèle : Attribut profil qui décrit le score et la catégorie du profil


### Utilisation du score d’engagement pour le canal de courrier électronique

Pour accéder à ces mesures, vous devez :

1. Ouvrez un profil et cliquez sur le bouton Modifier.

1. Cliquez sur l’onglet Scores **d’engagement pour le Canal** de courriel.

En utilisant une activité de requête dans un processus, vous pouvez utiliser le score pour optimiser votre audience.

Par exemple, avec les critères de niveau **de** rétention :

![](assets/do-not-localize/predictive_score_query.png)























