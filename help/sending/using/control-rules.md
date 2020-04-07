---
title: RCas des règles de contrôle
description: Apprenez comment renforcer la vérification de la qualité des messages avec les règles de contrôle.
page-status-flag: never-activated
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 40de67f4c918b26de6d306ce6af5cb8832741d6f

---


# Cas des règles de contrôle {#control-rules}

Les règles de contrôle vous permettent de vérifier la validité et la qualité des messages avant leur envoi, tels que l&#39;affichage des caractères, la taille des messages SMS, le format d&#39;adresse, etc.

>[!NOTE]
>
>Pour des raisons de sécurité, les règles de contrôle sont en lecture seule et ne peuvent pas être modifiées.

## Règles de contrôle par défaut {#default-control-rules}

Un ensemble de règles par défaut garantit les contrôles standard. Le tableau ci-dessous fournit des informations sur ces règles, ainsi que sur leurs  de et phases [d’](#control-rules-execution-phases)exécution connexes.

| Libellé | Channel | Phase d&#39;exécution | Description |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | Email | Au début de la personnalisation | Extrait la population de tests pour un  avec un test A/B. |
| **[!UICONTROL Check delivery size]** | Tous | Après le ciblage | Vérifie la taille des messages. |
| **[!UICONTROL Check email content is not empty]** | Email | Après le ciblage | Génère une erreur si le contenu du message est vide. |
| **[!UICONTROL Check In-App content for broadcast template]** | In-App | À la personnalisation des  | Vérifie que le contenu/les déclencheurs in-app ne sont pas vides pour le modèle de diffusion. |
| **[!UICONTROL Check In-App content for profile template]** | In-App | Au début de la personnalisation | Vérifie que le contenu/les déclencheurs in-app ne sont pas vides pour le modèle de  de. |
| **[!UICONTROL Check In-App content for subscriber template]** | In-App | Au début de la personnalisation | Vérifie que le contenu/les déclencheurs in-app ne sont pas vides pour le modèle d’abonné. |
| **[!UICONTROL Check proof size]** | Tous | Après le ciblage | Génère un message d’erreur si la population  dépasse 100. |
| **[!UICONTROL Check social network sharing link]** | Email | Au début de la personnalisation | Vérifie la présence d’un lien vers un lors de l’inclusion d’un lien de partage de réseau social (ViralLinks) dans le contenu. |
| **[!UICONTROL Check subject]** | Email | Au début de la personnalisation | Vérifie que l&#39;objet et l&#39;adresse de l&#39;expéditeur ne contiennent pas de caractères spéciaux pouvant causer des problèmes à certains agents de transfert de courrier et vérifie que l&#39;objet du message a été rempli. |
| **[!UICONTROL Check unsubscription link]** | Email | Au début de la personnalisation | Vérifie la présence d’au moins une URL d’ (exclusion) du dans chaque contenu (HTML et texte). |
| **[!UICONTROL Check URL labels]** | Email | Au début de la personnalisation | Vérifie que chaque URL de suivi comporte une étiquette. |
| **[!UICONTROL Check URLs]** | Email | Au début de la personnalisation | Vérifie les URL de suivi (présence du caractère &quot;&amp;&quot;). |

## Phases d’exécution des règles de contrôle (phases d’exécution des règles de contrôle)

Les règles de contrôle peuvent être appliquées à différentes phases du cycle de vie  :

* **Au  du ciblage**: La règle de contrôle peut être appliquée à cette phase afin que l’étape de personnalisation ne soit pas exécutée dans le d’une erreur.

* **Après le ciblage**: L’exécution après le ciblage vous permet de connaître le volume de l’ afin d’appliquer la règle de contrôle.

   Par exemple, la règle de contrôle **Vérification de la taille des BAT** s&#39;applique obligatoirement après l&#39;étape de ciblage : cette règle permet de ne pas préparer la personnalisation des messages si les destinataires du BAT sont trop nombreux.

* **Au début de la personnalisation**: S’applique lorsque la vérification concerne l’approbation de la personnalisation des messages. La personnalisation des messages est réalisée au cours de la phase d&#39;analyse.

* **A la fin de l&#39;analyse**: Lorsqu’une vérification nécessite la personnalisation du message.
