---
title: Règles de fatigue
seo-title: Règles de fatigue
description: Règles de fatigue
seo-description: Créez des règles de fatigue afin de gérer la sur-sollicitation des profils en matière de communication.
page-status-flag: jamais activé
uuid: fa 5 e 3 ded -36 c 2-4 f 16-b 97 a -119 b 85 adf 679
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: référence
topic-tags: working-with-tyloy-rules
discoiquuid: 4337 a 80 b -0 fb 9-4 a 37-bce 3-fe 2121 a 66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Règles de fatigue{#fatigue-rules}

## A propos des règles de fatigue {#about-fatigue-rules}

Les règles de fatigue permettent aux marketeurs de définir des règles métier cross-canal globales qui excluront automatiquement les profils sur-sollicités des campagnes.

Pour implémenter une règle de fatigue, vous devez définir un nombre maximum de messages par profil et sélectionner une période pendant laquelle s'appliquera la règle. Lors de la préparation de la diffusion, les profils sont exclus ou non de la diffusion, selon le nombre de messages qui leur ont déjà été adressés.

>[!NOTE]
>
>Pour que les règles de fatigue soient appliquées, vous devez définir une date de contact pour votre diffusion. Si vous choisissez d'envoyer immédiatement les messages, la règle de fatigue ne sera pas appliquée.

Rubriques connexes :

* [Préparation](../../administration/using/configuring-email-channel.md#preparation)
* [Gestion des typologies](../../administration/using/about-typology-rules.md#managing-typologies)
* [Règles de typologie](../../administration/using/about-typology-rules.md#typology-rules)

## Créer une règle de fatigue {#creating-a-fatigue-rule}

Pour créer et paramétrer une règle de typologie de type **[!UICONTROL Fatigue], les étapes sont les suivantes :**

1. Click the Adobe Campaign logo, in the top left corner of the interface, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. Depuis la liste des règles de typologie, cliquez sur **[!UICONTROL Créer]**.

   ![](assets/fatigue.png)

1. Dans le champ **[!UICONTROL Type de règle]**, sélectionnez **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. Dans le champ **[!UICONTROL Canal], sélectionnez le canal auquel s'appliquera la règle.** Vous pouvez choisir un seul canal (Email, SMS, Courrier, Application mobile) ou sélectionner **[!UICONTROL Tous les canaux]**. Voir [Choisir le canal](../../administration/using/fatigue-rules.md#choosing-the-channel).

   ![](assets/fatigue5.png)

1. Dans l'onglet **[!UICONTROL Général], définissez la méthode de calcul du nombre maximum de messages par profil.** Vous pouvez choisir un seuil constant ou variable. Vous pouvez également affiner le seuil sur les profils et diffusions. Voir à ce sujet la section [Définir le seuil](../../administration/using/fatigue-rules.md#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Sélectionnez une **[!UICONTROL Période glissante]pendant laquelle la règle doit s'appliquer.** Consultez à ce sujet la section [Définir la période glissante](../../administration/using/fatigue-rules.md#setting-the-sliding-period).

   ![](assets/fatigue6.png)

   Dans cet exemple (voir les captures d'écran précédentes), nous avons choisi d'envoyer un nombre maximum de 4 messages sur une période glissante de 15 jours.

1. Dans l'onglet **[!UICONTROL Critères d'application], vous pouvez choisir d'appliquer cette règle à toutes les diffusions ou limiter l'application de la règle selon le message à envoyer.** La règle ne s'exécutera que si la condition d'application est remplie. Vous pouvez par exemple appliquer uniquement la règle aux messages dont le libellé commence par un mot donné ou dont l'identifiant contient certaines lettres. Voir [Restreindre la portée d'une règle de filtrage](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule).

   ![](assets/fatigue20.png)

1. Sélectionnez l'onglet **[!UICONTROL Typologies]et associez votre règle de typologie à la typologie utilisée pour vos diffusions.** Voir [Gestion des typologies](../../administration/using/about-typology-rules.md#managing-typologies) et [Règles de typologie](../../administration/using/about-typology-rules.md#typology-rules).

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >La typologie peut être définie au niveau du modèle de diffusion afin de l'appliquer automatiquement à toutes les diffusions créées à partir de ce modèle.

Lors de la préparation de la diffusion, les profils sont exclus ou non de la diffusion, selon le nombre de diffusions qui leur ont déjà été adressées. Vous pouvez consulter les résultats de l'exécution des règles de fatigue dans les logs de diffusion. Voir [Consulter les résultats de la fatigue](../../administration/using/fatigue-rules.md#viewing-the-fatigue-results).

![](assets/fatigue16.png)

>[!CAUTION]
>
>Pour que les règles de fatigue fonctionnent, vous devez définir une date de contact pour votre diffusion. Si vous choisissez d'envoyer immédiatement les messages, la règle de fatigue ne sera pas appliquée.

## Choisir le canal {#choosing-the-channel}

Les règles de fatigue sont disponibles pour divers canaux. Le canal est défini dans le champ **[!UICONTROL Canal]des paramètres des règles de typologie.** Vous pouvez sélectionner un seul canal ou **[!UICONTROL Tous les canaux]**.

![](assets/fatigue5.png)

**Canaux disponibles**

Les canaux suivants sont disponibles :

* email
* Mobile (SMS)
* Canal Courrier
* Application mobile : ce canal permet d'envoyer des notifications push à des profils ou des abonnés de l'application. Si vous choisissez d'envoyer des notifications push à des profils, ils seront compatibles avec les règles de fatigue multicanal.

   >[!CAUTION]
   >
   >Les règles de fatigue sont incompatibles avec les notifications push envoyées aux abonnés de l'application. Si vous envoyez des messages aux abonnés de l'application, les règles de fatigue ne s'appliqueront pas.

* Tous les canaux : cette option permet d'appliquer la règle à tous les canaux. Vous pouvez par exemple décider d'envoyer un maximum de 3 messages par mois sur n'importe quel canal. Si vous avez envoyé 2 emails à un profil la semaine dernière et que vous essayez d'envoyer une notification push aujourd'hui, ce profil sera exclu.

**Types de diffusions**

Les règles de fatigue sont compatibles avec tous les types de diffusions : diffusions ponctuelles, diffusions récurrentes, diffusions de workflow et messages transactionnels.

Les **messages transactionnels** peuvent être utilisés pour envoyer des messages de service ciblant un événement (rtEvent) et des messages de remarketing (ciblant des profils). Les règles de fatigue sont compatibles uniquement avec les messages marketing (ciblant des profils). Les messages transactionnels basés sur un événement ne contiennent pas d'informations sur les profils. Ils ne sont donc pas compatibles avec les règles de fatigue (même dans le cas d'un enrichissement avec des profils). Grâce à la prise en charge des messages marketing dans les messages transactionnels, vous pouvez **appliquer une règle de fatigue à tous les canaux, notamment les messages transactionnels de marketing**.

## Définir le seuil {#defining-the-threshold}

Chaque règle de fatigue définit un seuil, c'est-à-dire le nombre maximum de messages pouvant être envoyés à chaque profil sur une période. Une fois ce seuil atteint, aucune diffusion ne sera envoyée jusqu'à la fin de la période concernée. Ce mode de fonctionnement permet d'exclure automatiquement un profil d'une diffusion si l'envoi du message provoquait le dépassement du seuil défini, et ainsi une sur-sollicitation.

La valeur de ce seuil peut être constante ou variable. Pour une même période, le seuil peut donc varier d'un profil à l'autre, et même pour un même profil.

**Utiliser un seuil fixe**

Le seuil représente le nombre maximum de messages pouvant être envoyés à un même profil pendant la période concernée.

Par défaut, le seuil est constant et vous devez indiquer le nombre maximum de messages autorisés par la règle.

![](assets/fatigue2.png)

**Utiliser un seuil variable**

Pour définir un seuil variable, sélectionnez la valeur **[!UICONTROL Dépend du destinataire]** dans le champ **Type de seuil[!UICONTROL .]**

![](assets/fatigue15.png)

Vous avez ensuite deux possibilités :

* sélectionner un champ de profil : le seuil variera pour chaque profil en fonction du champ sélectionné. Par exemple, si vous avez étendu la ressource Profiles avec un champ 'Fréquence des communications', cliquez sur le bouton situé à droite du champ **[!UICONTROL Formule de calcul du seuil]et sélectionnez votre champ.** Pour chaque profil, le seuil prendra la valeur du champ 'Fréquence des communications'.

   ![](assets/fatigue21.png)

* définir une formule : cliquez sur le second bouton situé à droite du champ **[!UICONTROL Formule de calcul du seuil]pour définir une formule sophistiquée de calcul du seuil.** Par exemple, vous pouvez faire dépendre le nombre de messages autorisés en fonction du segment auquel appartient le profil. Ainsi, un profil répertorié dans un segment 'Web' pourrait recevoir plus de messages que les autres profils. Une formule de type **[!UICONTROL Iif (@origin='Web', 5, 3)]permet d'autoriser l'envoi de 5 messages à ces profils contre seulement 3 messages pour les profils des autres segments.**

   ![](assets/fatigue14.png)

**Affiner le seuil sur les profils et diffusions**

Par défaut, tous les messages sont pris en compte pour le calcul du seuil. Cochez la case **[!UICONTROL Affiner le seuil sur les profils et diffusions]pour filtrer les profils et les diffusions à comptabiliser lors de la préparation de la diffusion.**

Dans l'exemple ci-après, seuls les profils masculins et les diffusions dont le libellé commence par **Newsletters** sont comptabilisés.

![](assets/fatigue13.png)

Affiner le seuil sur les diffusions est différent de limiter l'application de la règle entière (onglet **[!UICONTROL Critères d'application]) :**

* **[!UICONTROL Critères d'application]** : vous choisissez d'exécuter ou non la règle en fonction de critères spécifiques. Par exemple, si votre condition d'application est 'Libellé commence par Newsletter', la règle ne s'appliquera qu'aux diffusions respectant cette condition. Si le libellé de la diffusion commence par 'Promotion', la règle ne s'exécutera pas.
* **[!UICONTROL Affiner le seuil sur les profils et diffusions &gt; Diffusions à comptabiliser]** : toutes les diffusions utilisant cette règle de typologie exécuteront la règle, mais vous décidez quelles diffusions sont à comptabiliser parmi celles déjà envoyées et celles planifiées. Par exemple, si votre restriction est 'Libellé commence par Newsletter', la règle sera exécutée même si le libellé de la diffusion commence par 'Promo'. Sur la période glissante, elle comptabilisera le nombre de diffusions dont le libellé commence par 'Newsletter'.

## Définir la période glissante {#setting-the-sliding-period}

Les règles de fatigue sont définies par périodes glissantes de n jours. La période est configurée dans la section **[!UICONTROL Période glissante], par exemple 2 semaines, 7 jours ou 5 heures.**

![](assets/fatigue6.png)

Lors de l'exécution de la règle, les diffusions déjà envoyées et les diffusions planifiées sont prises en compte. Ainsi, le seuil n'est jamais dépassé pendant une période glissante donnée.

For example, if you define a 48-hour period, the system will be looking 48 hours **before the contact date ** and 48 hours **after the contact date**. La période sélectionnée est donc doublée afin de permettre l'intégration des diffusions à venir ainsi que celles déjà envoyées.

Pour limiter à une période de 15 jours la prise en compte des diffusions, entrez **Jour** et **7** ou 1 semaine dans la section **Période glissante.** Les diffusions envoyées jusqu'à 7 jours avant la date de diffusion et planifiées jusqu'à 7 jours après la date de diffusion à laquelle la règle est appliquée seront prises en compte dans le calcul.

## Consulter les résultats de la fatigue {#viewing-the-fatigue-results}

Lors de la préparation de la diffusion, les profils sont exclus ou non de la diffusion, selon le nombre de diffusions qui leur ont déjà été adressées. Pour consulter les résultats de l'exécution de la règle de fatigue, cliquez sur le bouton situé en bas à droite du bloc **[!UICONTROL Déploiement].**

![](assets/fatigue22.png)

Trois onglets sont disponibles. Ils indiquent les détails des résultats de l'exécution de la fatigue, notamment le nom de la règle qui a été appliquée :

* Logs de diffusion :

   ![](assets/fatigue17.png)

* Exclus :

   ![](assets/fatigue18.png)

* Exclusions appliquées :

   ![](assets/fatigue19.png)

## Affichage du rapport Synthèse des règles de fatigue {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign propose un rapport dédié sur les règles de fatigue afin de vous aider à comprendre la façon dont elles sont appliquées à vos campagnes. Vous pouvez ainsi déterminer l'incidence que vos campagnes ont les unes sur les autres et effectuer les réglages nécessaires.

Le rapport **[!UICONTROL Synthèse des règles de fatigue]** est accessible à partir du bouton **Rapports], dans le coin supérieur droit de chaque programme, campagne et message.[!UICONTROL **

![](assets/fatigue27.png)

Dans la partie gauche de l'écran, vous pouvez filtrer les données du rapport en fonction de la date de contact des diffusions. Par défaut, la période sélectionnée démarre 15 jours avant la date courante et se termine 15 jours après. Vous pouvez également appliquer un filtre d'après une règle de fatigue spécifique.

Le graphique en secteurs présente les informations suivantes sur la période sélectionnée :

* **[!UICONTROL Total ciblé]** : cible totale avant préparation du message
* **[!UICONTROL Exclu]** : nombre total d'exclusions en raison de l'application de la règle de fatigue
* **[!UICONTROL Autres exclusions]** : nombre total d'exclusions en raison d'autres règles de typologie
* **[!UICONTROL Pour diffuser]**: nombre total de messages à diffuser après préparation des messages ( **[!UICONTROL livraison]** = **[!UICONTROL Total ciblé]** - **[!UICONTROL Exclus]** - **[!UICONTROL Autres exclusions]** )

A droite du graphique, vous trouverez le nombre d'exclusions, répartis par règle de fatigue.

La table du bas présente toutes les diffusions au cours de la période sélectionnée. Pour chaque diffusion, vous pouvez voir les règles de fatigue appliquées et les exclusions correspondantes. Les diffusions sans date de contact sont également affichées dans la table.

* **[!UICONTROL 0]** signifie que la règle de fatigue s'appliquait, mais sans exclusion.
* **[!UICONTROL -N]** signifie que N exclusions ont été réalisées.
* Un champ vide signifie que la règle de fatigue ne s'appliquait pas.

>[!NOTE]
>
>Les données affichées ne dépendent pas du contexte du programme, du message ou de la campagne à partir duquel vous accédez au rapport. Ce rapport affiche toutes les règles de fatigue et diffusions pour l'ensemble des entités organisationnelles. Vous obtenez ainsi une vue globale de toutes les diffusions afin de comprendre la façon dont vos campagnes s'influencent entre elles.

## Exemples {#examples}

L'implémentation de la gestion de la fatigue offre de nombreuses possibilités. Voici quelques exemples de ce que vous pouvez faire :

* Créer une règle de fatigue qui utilise un **seuil constant** s'appliquant à **tous les canaux** :

   Imaginons que vous créez une règle multicanal avec un seuil constant de 3 sur une période glissante de 7 jours.

   La semaine dernière, les profils Premium ont reçu un email de promotion et un email de remarketing transactionnel. Vous avez également planifié un SMS qui sera envoyé la semaine prochaine. Vous décidez d'envoyer aujourd'hui une notification push ciblant tous vos profils. Les profils Premium seront exclus de la notification push d'aujourd'hui, car leur nombre maximum de messages sur une période de 15 jours a déjà été atteint.

   ![](assets/fatigue23.png)

* Créer une règle de fatigue qui utilise un **seuil variable** reposant sur un **champ de profil** :

   Vous avez étendu la ressource Profiles avec un champ 'Limiter les communications' afin de définir un seuil différent pour chaque profil. Dans la règle de fatigue, définissez un seuil variable qui repose sur ce champ et sélectionnez une période glissante de 2 jours. Prenons deux exemples de profil : la limite des communications de Jean est de 1 et le seuil de David est de 2. Jean et David ont déjà reçu un email de newsletter hier. Vous décidez de leur envoyer un autre email aujourd'hui. Seul David le recevra, car Jean a été exclu de la cible.

   ![](assets/fatigue24.png)

* Créer une règle de fatigue qui utilise une **formule de calcul du seuil** :

   Vous souhaitez changer le seuil selon l'âge de vos profils. Si un profil a moins de 40 ans, vous souhaitez définir une limite de 4. Pour les profils plus âgés, vous voulez une limite de 2. Au lieu de définir ce seuil pour chaque profil avec un champ étendu, vous pouvez créer une formule directement dans la règle de fatigue afin de calculer le seuil selon l'âge des profils. Dans cet exemple, la formule serait **[!UICONTROL Iif (@age&lt;40, 4, 2)]**.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >Cette section contient également un exemple détaillé de règle de fatigue utilisant une formule de calcul du seuil.

* Créer une règle de fatigue qui **affine le seuil** sur les profils et diffusions :

   Vous avez étendu la ressource Profiles avec un champ 'Score' et la ressource des diffusions avec un champ 'Type'. Vous voulez définir un seuil constant de 3, mais souhaitez exclure de la comptabilisation toutes les diffusions de type 'Alerte' ou 'Black Friday' et tous les profils dont le score est supérieur à 10. Lors de l'exécution de la règle, celle-ci comptabilisera, parmi les diffusions déjà envoyées et les diffusions planifiées, toutes les diffusions qui ne sont pas de type 'Alerte' ni 'Black Friday' envoyées aux profils dont le score est inférieur à 10.

   ![](assets/fatigue26.png)

Vous trouverez ci-dessous un exemple détaillé de règle de fatigue utilisant une formule de calcul du seuil.

Dans ce cas pratique, nous allons créer une règle de typologie afin de ne pas envoyer plus de 2 messages par semaine aux profils Premium et pas plus de 2 messages par semaine aux profils standards.

Pour identifier les clients et les prospects, nous avons étendu la ressource Profiles avec le champ **[!UICONTROL Statut], qui contient 0 pour les profils Premium et 1 pour les profils standards.**

Les étapes de création de cette règle sont les suivantes :

1. Créez une règle de typologie de type **Fatigue**.
1. Dans la section **[!UICONTROL Seuil], nous allons créer une formule de calcul du seuil qui dépendra de chaque profil.** Sélectionnez la valeur **[!UICONTROL Dépend du destinataire]** dans le champ **[!UICONTROL Type de seuil], puis cliquez sur le second bouton situé à droite du champ** Formule de calcul du seuil **.**

   ![](assets/fatigue7.png)

1. Dans la section **[!UICONTROL Liste des fonctions]**, double-cliquez sur la fonction **Iif** dans le nœud **Autres[!UICONTROL .]**

   ![](assets/fatigue8.png)

1. Sélectionnez ensuite le **Statut** du profil, dans la section **[!UICONTROL Champs disponibles].**

   ![](assets/fatigue9.png)

1. Saisissez les valeurs souhaitées pour créer la formule suivante :**Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   Cette formule permet d'attribuer la valeur 2 si le statut est égal à 0, et la valeur 4 pour tout autre statut.

1. Cliquez sur **[!UICONTROL Confirmer]pour valider cette formule.**
1. Indiquez la **[!UICONTROL Période glissante]pendant laquelle la règle doit s'appliquer : ici 7 jours pour limiter à 15 jours la prise en compte des diffusions.**

   ![](assets/fatigue11.png)

1. Vous devez maintenant associer la règle que vous venez de créer à une typologie afin de pouvoir l'appliquer à vos diffusions. Pour cela, sélectionnez l'onglet **[!UICONTROL Typologies]**, cliquez sur **Créer un élément], puis sélectionnez la typologie utilisée pour vos diffusions.[!UICONTROL **

   ![](assets/fatigue12.png)

1. Enregistrez la règle pour en valider la création.

La règle sera appliquée à toutes les diffusions selon la typologie.
