---
title: 'Liste des composants '
description: Cette section contient la liste de tous les composants disponibles dans les rapports dynamiques et leur définition.
page-status-flag: never-activated
uuid: a2403806-8df4-4bb1-bac2-2689dc584ae0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 17cf126a-7ce1-4e11-bb5e-2bdce01cfded
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Liste des composants {#list-of-components}

Pour plus d'informations sur la compatibilité entre les dimensions et les mesures, consultez ce [tableau](https://docs.campaign.adobe.com/doc/standard/en/Technotes/dynamic_report_compatibility.pdf). Si deux composants ne sont pas compatibles, la cellule affiche la valeur **Aucun**.

[![image](/help/reporting/using/assets/dynamic_report_compatibility.png)](https://docs.campaign.adobe.com/doc/standard/en/Technotes/dynamic_report_compatibility.pdf)

## Dimensions {#dimensions}

Le tableau ci-dessous contient la liste des dimensions utilisées dans les différents rapports et leur définition.

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Définition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Navigateur<br /> </td> 
   <td> Navigateur dans lequel le message a été ouvert ou a fait l'objet d'un clic.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign<br /> </td> 
   <td> Libellé et identifiant de votre campagne.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ville<br /> </td> 
   <td> Ville enregistrée dans le profil du destinataire.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pays/zone géographique<br /> </td> 
   <td> Pays enregistré dans le profil du destinataire.<br /> </td> 
  </tr> 
  <tr> 
   <td> Diffusion<br /> </td> 
   <td> Libellé et identifiant de la diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Appareil<br /> </td> 
   <td> Appareil sur lequel l'email/le SMS/la notification push ont été ouverts/vus ou ont fait l'objet d'un clic.<br /> </td> 
  </tr> 
  <tr> 
   <td> Raison de l'échec<br /> </td> 
   <td> Types d’erreurs qui provoquaient des retours pour chaque remise, par exemple : utilisateur inconnu, domaine non valide ou boîte aux lettres pleine.<br /> </td> 
  </tr> 
  <tr> 
   <td> Genre<br /> </td> 
   <td> Genre du destinataire (masculin ou féminin). Si le champ Genre est vide dans le profil du destinataire, la valeur sera aucune.<br /> </td> 
  </tr> 
  <tr> 
   <td> Actions de message In-App<br /> </td> 
   <td> Actions sur le message In-App diffusé, par exemple actions sur le bouton 1 ou 2 ou masquage.<br /> </td> 
  </tr> 
  <tr> 
   <td> Type de message<br /> </td> 
   <td> Canal utilisé pour la diffusion, par exemple email, SMS, notification push ou In-App.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nom de l'application mobile<br /> </td> 
   <td> Nom de l'application mobile.<br /> </td> 
  </tr> 
  <tr> 
   <td> Plate-forme<br /> </td> 
   <td> Plateforme de l'appareil sur lequel le message a été ouvert/vu ou a fait l'objet d'un clic.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profils<br /> </td> 
   <td> Regroupe les champs de paramètres d'usine et de profil personnalisé créés lors de l'extension de la ressource de profil. Pour plus d'informations, consultez cette <a href="../../developing/using/key-steps-to-add-a-resource.md">page</a> ou cet <a href="../../reporting/using/creating-a-custom-profile-dimension.md">exemple</a>.<br /> Notez que les données de cette dimension sont récupérées dès la publication de la ressource personnalisée liée au champ de profil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Plateforme push<br /> </td> 
   <td> Plateforme de l'appareil sur lequel la notification push a été ouverte (iOS ou Android, par exemple).<br /> </td> 
  </tr> 
  <tr> 
   <td> Domaine du destinataire<br /> </td> 
   <td> Domaine utilisé pour ouvrir l'email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Diffusion récurrente<br /> </td> 
   <td> Libellé et identifiant de la diffusion récurrente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Domaine de l'expéditeur<br /> </td> 
   <td> Domaine utilisé pour envoyer l'email.<br /> </td> 
  </tr> 
  <tr> 
   <td> IP de l'expéditeur<br /> </td> 
   <td> Adresse IP utilisée pour envoyer l'email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Etat<br /> </td> 
   <td> Etat enregistré dans le profil du destinataire.<br /> </td> 
  </tr> 
  <tr> 
   <td> l'URL de tracking<br /> </td> 
   <td> URL sur laquelle a cliqué l'utilisateur dans le message.<br /> </td> 
  </tr> 
  <tr> 
   <td> Catégorie de l'URL de tracking<br /> </td> 
   <td> Catégorie affectée à l'URL de tracking.<br /> </td> 
  </tr> 
  <tr> 
   <td> Libellé de l'URL de tracking<br /> </td> 
   <td> Libellé de l'URL (page miroir, contactez-nous ou ouvrir, par exemple).<br /> </td> 
  </tr> 
  <tr> 
   <td> Diffusion transactionnelle<br /> </td> 
   <td> Libellé et identifiant de la diffusion transactionnelle.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variante<br /> </td> 
   <td> Variante de l'email en cas de test A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Mesures    {#metrics}

Les tableaux ci-dessous contiennent la liste des mesures utilisées dans les différents rapports et leur définition.

### Mesures des emails et SMS    {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mesure<br /> </th> 
   <th> Définition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Blacklisted<br /> </td> 
   <td> Nombre de destinataires ayant déclaré un email comme étant un spam ou un courrier indésirable.<br /> </td> 
  </tr> 
  <tr> 
   <td> Blacklisted rate<br /> </td> 
   <td> Pourcentage de diffusions marquées comme blacklistées.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounces + Errors<br /> </td> 
   <td> Nombre total d'erreurs cumulées lors des diffusions et du traitement automatique des retours par rapport au nombre total de messages envoyés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br /> </td> 
   <td> Pourcentage d'emails qui ont fait l'objet d'un bounce par rapport au nombre d'emails envoyés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliquez sur<br /> </td> 
   <td> Nombre de clics sur un contenu dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de clics publicitaires<br /> </td> 
   <td> Pourcentage de clics dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivrés<br /> </td> 
   <td> Nombre de messages envoyés avec succès, par rapport au nombre total de messages envoyés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br /> </td> 
   <td> Pourcentage de messages envoyés avec succès.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hard bounce<br /> </td> 
   <td> Nombre total d'erreurs permanentes, telles qu'une adresse email incorrecte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de hard bounce<br /> </td> 
   <td> Pourcentage de diffusions en erreur en raison d'erreurs permanentes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror page<br /> </td> 
   <td> Nombre de destinataires ayant cliqué sur le lien de la page miroir.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror page rate<br /> </td> 
   <td> Pourcentage de clics sur le lien de la page miroir par rapport au nombre total de messages de la diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics sur une offre<br /> </td> 
   <td> Nombre de clics sur une offre dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de clics de l'offre<br /> </td> 
   <td> Pourcentage de clics sur une offre.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures<br /> </td> 
   <td> Nombre d’ouvertures d’un message dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux d'ouverture<br /> </td> 
   <td> Pourcentage de messages ouverts.<br /> </td> 
  </tr> 
  <tr> 
   <td> Traités/envoyés<br /> </td> 
   <td> Nombre total d'envois pour la diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantine<br /> </td> 
   <td> Nombre de messages qui ont fait l'objet d'un bounce et qui ont entraîné la mise en quarantaine de l'adresse.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantine rate<br /> </td> 
   <td> Pourcentage de mises en quarantaine par rapport au nombre de messages envoyés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Refusée<br /> </td> 
   <td> Nombre de messages classés comme spam par les serveurs SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejected rate<br /> </td> 
   <td> Pourcentage de messages marqués comme rejetés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Soft bounce<br /> </td> 
   <td> Nombre total d'erreurs permanentes, telles qu'une boîte de réception pleine.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de soft bounce<br /> </td> 
   <td> Pourcentage de diffusions en erreur pour une raison temporaire.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics uniques<br /> </td> 
   <td> Nombre de destinataires ayant cliqué sur un contenu dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures uniques<br /> </td> 
   <td> Nombre de destinataires ayant ouvert la diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribe rate<br /> </td> 
   <td> Pourcentage de désinscriptions par destinataire par rapport au nombre de messages délivrés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Désabonné<br /> </td> 
   <td> Nombre de clics sur le lien de désinscription.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Mesures des notifications push    {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mesure<br /> </th> 
   <th> Définition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Bounces + erreurs<br /> </td> 
   <td> Nombre total d'erreurs cumulées lors des diffusions par rapport au nombre total de messages envoyés, par exemple erreurs du MCPNS ou du fournisseur.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Taux d'erreurs<br /> </td> 
   <td> Pourcentage de notifications push qui ont fait l'objet d'un bounce par rapport au nombre de notifications push envoyées.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic<br /> </td> 
   <td> Nombre de fois qu'une notification push a été diffusée sur l'appareil et a fait l'objet d'un clic par l'utilisateur. L'utilisateur souhaitait afficher la notification, qui sera déplacée vers le tracking Ouverture push, ou l'ignorer.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de clics publicitaires<br /> </td> 
   <td> Pourcentage d'utilisateurs ayant interagi avec la notification push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivrés<br /> </td> 
   <td> Nombre de notifications push envoyées avec succès, par rapport au nombre total de notifications push envoyées.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de délivrabilité<br /> </td> 
   <td> Pourcentage de notifications push envoyées avec succès.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br /> </td> 
   <td> Nombre de fois qu'une notification push a été diffusée sur l'appareil et laissée intacte dans le centre de notification. Dans la plupart des cas, le nombre d'impressions doit être similaire au nombre délivrés. Cela garantit que l'appareil reçoit le message et transmet cette information au serveur.<br /> </td> 
  </tr> 
  <tr> 
   <td> Traités/envoyés<br /> </td> 
   <td> Nombre total de notifications push envoyées.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures<br /> </td> 
   <td> Nombre total de notifications push diffusées sur l'appareil et ayant fait l'objet d'un clic par les utilisateurs ouvrant l'application. Cette mesure est similaire au Clic push, sauf qu'une Ouverture push ne sera pas déclenchée si la notification a été ignorée.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux d'ouverture<br /> </td> 
   <td> Pourcentage de notifications push ouvertes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic unique<br /> </td> 
   <td> Nombre de fois où un utilisateur unique interagit avec la notification push, par exemple clics sur la notification ou le bouton.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions uniques<br /> </td> 
   <td> Nombre d'impressions par destinataire.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures uniques<br /> </td> 
   <td> Nombre de destinataires ayant ouvert la diffusion.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Mesures In-App    {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mesure<br /> </th> 
   <th> Définition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Delivrés<br /> </td> 
   <td> Nombre total de messages In-App remis à l'appareil par le fournisseur.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br /> </td> 
   <td> Nombre total de messages In-App vus par les destinataires selon que le critère de déclenchement a été rempli ou non.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics In-App <br /> </td> 
   <td> Nombre total de destinataires ayant cliqué sur le bouton 1 ou le bouton 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de clics In-App<br /> </td> 
   <td> Pourcentage d'utilisateurs ayant cliqué sur le bouton 1 ou le bouton 2 par rapport au nombre d'utilisateurs ayant vu le message.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejet In-App<br /> </td> 
   <td> Nombre total de messages que les destinataires ont ignoré en cliquant sur le bouton de fermeture ou en l'ignorant automatiquement.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de rejet In-App<br /> </td> 
   <td> Pourcentage de messages In-App ignorés par les destinataires.<br /> </td> 
  </tr> 
  <tr> 
   <td> Traités/envoyés<br /> </td> 
   <td> Nombre total de messages In-App envoyés depuis Adobe Campaign dans le cadre du processus d'envoi de la diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions uniques<br /> </td> 
   <td> Nombre d'impressions par un destinataire unique.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics In-App uniques<br /> </td> 
   <td> Nombre de fois où les destinataires ont cliqué sur le bouton 1 ou le bouton 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejets In-App uniques<br /> </td> 
   <td> Nombre de fois où les destinataires ont ignoré un message In-App.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segments {#segments}

>[!NOTE]
>
>Par défaut, le segment Exclure la preuve **** est déjà sélectionné pour filtrer vos rapports, mais il peut être modifié si nécessaire.

Le tableau ci-dessous contient la liste des segments utilisés dans les différents rapports et leur définition.

<table> 
 <thead> 
  <tr> 
   <th> Segment<br /> </th> 
   <th> Définition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Age : baby boomers 1<br /> </td> 
   <td> Destinataires nés entre 1946 et 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : baby boomers 2<br /> </td> 
   <td> Destinataires nés entre 1955 et 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : de 18 à 25 ans<br /> </td> 
   <td> Destinataires âgés de 18 à 25 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : de 26 à 30 ans<br /> </td> 
   <td> Destinataires âgés de 26 à 30 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : de 31 à 40 ans<br /> </td> 
   <td> Destinataires âgés de 31 à 40 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : de 41 à 50 ans<br /> </td> 
   <td> Destinataires âgés de 41 à 50 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : génération X<br /> </td> 
   <td> Destinataires nés entre 1966 et 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : génération Y (enfants du millénaire)<br /> </td> 
   <td> Destinataires nés entre 1977 et 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : génération Z<br /> </td> 
   <td> Destinataires nés entre 1995 et aujourd'hui.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : plus de 50 ans<br /> </td> 
   <td> Destinataires dont l'âge est supérieur à 50 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : moins de 25 ans<br /> </td> 
   <td> Destinataires dont l'âge est inférieur à 25 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : moins de 30 ans<br /> </td> 
   <td> Destinataires dont l'âge est inférieur à 30 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : moins de 40 ans<br /> </td> 
   <td> Destinataires dont l'âge est inférieur à 40 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : moins de 50 ans<br /> </td> 
   <td> Destinataires dont l'âge est inférieur à 50 ans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Age : génération silencieuse<br /> </td> 
   <td> Destinataires nés en 1945 ou avant.<br /> </td> 
  </tr> 
  <tr> 
   <td> Toutes les visites<br /> </td> 
   <td> Tous les destinataires<br /> </td> 
  </tr> 
    <tr> 
   <td> Exclure la preuve<br /> </td> 
   <td> Exclure les preuves de vos rapports (à partir de la version 19.4 uniquement)<br /> </td> 
  </tr> 
 </tbody> 
</table>

