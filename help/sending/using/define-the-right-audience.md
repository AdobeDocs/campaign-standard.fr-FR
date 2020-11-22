---
solution: Campaign Standard
product: campaign
title: Définir l’audience appropriée
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 100%

---


# Définir l’audience appropriée {#define-the-right-audience}

La population ciblée est essentielle : créez soigneusement vos listes, testez vos emails sur les clients de messagerie et les appareils mobiles les plus utilisés et vérifiez que vos listes email sont à jour (sans adresses inconnues ou obsolètes). Vous pouvez également envoyer des bons à tirer permettant de configurer un cycle de validation complet.

En savoir plus sur les populations ciblées [dans cette section](../../audiences/using/selecting-an-audience-in-a-message.md)

## Cibler la bonne audience {#target-the-right-audience}

Lorsque votre contenu est prêt, vous devez soigneusement définir qui recevra votre message.

Pour réussir votre diffusion, vous devez envoyer le contenu personnalisé le plus pertinent aux bons destinataires. Adobe Campaign vous permet de créer la cible la plus précise qui soit : vous pouvez sélectionner les destinataires selon leur âge, leur emplacement géographique, leurs achats ou selon qu’ils ont cliqué ou non sur un lien dans une diffusion précédente, par exemple. Avec Adobe Campaign, vous pouvez également définir des profils de test, des populations témoins et des adresses de contrôle pour vérifier que votre cible est correcte.

## Mappings de ciblage {#target-mappings}

Par défaut, les modèles de diffusion ciblent les **profils**. Adobe Campaign propose d’autres mappings de ciblage pour vos diffusions, que vous pouvez modifier selon vos besoins.

Ces mappings sont présentés [dans cette section](../../automating/using/query.md#targeting-dimensions-and-resources).

Vous pouvez également créer et utiliser un mapping de ciblage personnalisé. Voir à ce propos [cette section](../../administration/using/target-mappings-in-campaign.md).

## Données externes {#external-data}

Vous pouvez effectuer une diffusion aux destinataires qui sont stockés dans un fichier externe plutôt qu&#39;enregistrés dans la base de données. Pour ce faire, concevez un workflow qui chargera des données dans votre base de données à partir d’un fichier et créez une audience associée.  En savoir plus [sur ce cas pratique](../../automating/using/use-case-calling-workflow.md). Voir aussi [Appel d’un workflow avec des paramètres](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Envoyer des messages à vos abonnés {#send-to-subscribers}

Pour envoyer des messages aux abonnés d&#39;une newsletter, vous pouvez directement cibler les abonnés du service d&#39;information correspondant. En savoir plus dans [cette section](../../audiences/using/about-subscriptions.md).

**Conseil** : créez une audience de type Liste qui cible les abonnés à votre newsletter à l’aide d’un workflow. Vous pouvez ensuite sélectionner cette audience dans une diffusion. Voir à ce propos la section [Création d’une audience de type Liste](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Bons à tirer, profils de test et populations témoins {#proofs-test-control-groups}

Pour tester votre diffusion, utilisez des bons à tirer avant l&#39;envoi à la cible principale.
Veillez à sélectionner les destinataires du BAT appropriés, car ils valident le formulaire et le contenu du message. Les étapes d&#39;envoi des BAT sont présentées [dans cette section](../../sending/using/sending-proofs.md).

En savoir plus sur les profils de test [dans cette section](../../audiences/using/managing-test-profiles.md).

Vous pouvez utiliser des [Populations témoins](../../sending/using/control-group.md) pour mesurer l’impact de vos campagnes en excluant une partie de leur audience. Vous pourrez ensuite comparer le comportement de la population cible qui a reçu le message avec celui des contacts qui n’ont pas été ciblés. En fonction des logs d’envoi, vous pourrez également cibler une population témoin dans les prochaines campagnes.

## Dédupliquer les adresses {#deduplicate-addresses}

Il est important d&#39;éviter d&#39;avoir des adresses email en double, car cela peut avoir un impact sur votre cible.

* Un même message peut être envoyé plusieurs fois lorsqu&#39;une une cible est partagée.

* Si une personne se désabonne suite à la réception d&#39;un message, son profil en double recevra toujours les prochains messages.

Pour garantir votre réputation et assurer une bonne gestion des quarantaines, dédupliquez les adresses.

En savoir plus [sur ce cas pratique](../../automating/using/deduplicating-data-imported-file.md).
