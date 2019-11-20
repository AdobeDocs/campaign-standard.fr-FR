---
title: DataModel
description: En savoir plus sur le modèle de données
page-status-flag: never-activated
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
context-tags: delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 18d9b33e36db628ef1fc014e4abe6a4a7eef48b3

---


# landingPage (nms:landingPage)

## Description de l’objet

<table>
      <tr>
         <th>Nom</th>
         <th>Libellé</th>
         <th>Type (longueur)</th>
         <th>Valeurs d'énumération</th>
      </tr>
      <tr>
         <td>PKey</td>
         <td>Identifiant principal de la ressource</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalData</td>
         <td>Données additionnelles</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalLanguages</td>
         <td>Autres langues</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Autoriser les visiteurs non identifiés</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>branding (brandingBase)</td>
         <td>Marque</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>buildingIn</td>
         <td>Objet d’application intégré</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>cache</td>
         <td>Cache</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>campaign (campaignBase)</td>
         <td>Campaign</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>closeLog</td>
         <td>Journal de la page d’entrée fermée</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>created</td>
         <td>Créé</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>createdBy (userBase)</td>
         <td>Créé par</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>cryptKey</td>
         <td>Clé de chiffrement AES</td>
         <td>string (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Langue par défaut</td>
         <td>énumération (chaîne) (255)</td>
         <td>
            <ul>
               <li>Grec - el - el</li>
               <li>Anglais - en - en</li>
               <li>Chinois - zh - zh</li>
               <li>Français (France) - fr_FR - fr_FR</li>
               <li>Vietnamien - vi - vi</li>
               <li>Portugais (Portugal) - pt_PT - pt_PT</li>
               <li>Italien (Italie) - it_IT - it_IT</li>
               <li>Italien - it - it</li>
               <li>Néerlandais (Belgique) - nl_BE - nl_BE</li>
               <li>Norvégien (Norvège) - no_NO - no_NO</li>
               <li>Néerlandais (Pays-Bas) - nl_NL - nl_NL</li>
               <li>Arabe - ar - ar</li>
               <li>Anglais (États-Unis) - en_US - en_US</li>
               <li>Irlandais - ga - ga</li>
               <li>Tchèque - cs - cs</li>
               <li>Estonien - et - et</li>
               <li>Indonésien - id - id</li>
               <li>Espagnol - es - es</li>
               <li>Russe - ru - ru</li>
               <li>Néerlandais - nl - nl</li>
               <li>Walloon - wa - wa</li>
               <li>Portugais - pt - pt</li>
               <li>Français (Belgique) - fr_BE - fr_BE</li>
               <li>Letton - lv - lv</li>
               <li>Lituanien - lt - lt</li>
               <li>Thai - th - th</li>
               <li>Anglais (Royaume-Uni) - en_GB - en_GB</li>
               <li>Français - fr</li>
               <li>Portugais (Brésil) - pt_BR - pt_BR</li>
               <li>Allemand - de - de</li>
               <li>Danois - da - da</li>
               <li>Finnois - fi - fi</li>
               <li>Hongrois - hu - hu</li>
               <li>Suédois (Finlande) - sv_FI - sv_FI</li>
               <li>Japonais - ja - ja</li>
               <li>Hébreu - lui - lui</li>
               <li>Coréen - ko - ko</li>
               <li>Suédois - sv - sv</li>
               <li>Suède (Suède) - sv_SE - sv_SE</li>
               <li>Slovaque - sk - sk</li>
               <li>Maltais - mt - mt</li>
               <li>Italien (Suisse) - it_CH - it_CH</li>
               <li>Polonais - pl</li>
               <li>Slovène - sl - sl</li>
               <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin (remise)</td>
         <td>Source de trafic</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>desc</td>
         <td>Description</td>
         <td>string (512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>Langue de conception</td>
         <td>énumération (chaîne) (255)</td>
         <td>
            <ul>
               <li>Grec - el - el</li>
               <li>Anglais - en - en</li>
               <li>Chinois - zh - zh</li>
               <li>Français (France) - fr_FR - fr_FR</li>
               <li>Vietnamien - vi - vi</li>
               <li>Portugais (Portugal) - pt_PT - pt_PT</li>
               <li>Italien (Italie) - it_IT - it_IT</li>
               <li>Italien - it - it</li>
               <li>Néerlandais (Belgique) - nl_BE - nl_BE</li>
               <li>Norvégien (Norvège) - no_NO - no_NO</li>
               <li>Néerlandais (Pays-Bas) - nl_NL - nl_NL</li>
               <li>Arabe - ar - ar</li>
               <li>Anglais (États-Unis) - en_US - en_US</li>
               <li>Irlandais - ga - ga</li>
               <li>Tchèque - cs - cs</li>
               <li>Estonien - et - et</li>
               <li>Indonésien - id - id</li>
               <li>Espagnol - es - es</li>
               <li>Russe - ru - ru</li>
               <li>Néerlandais - nl - nl</li>
               <li>Walloon - wa - wa</li>
               <li>Portugais - pt - pt</li>
               <li>Français (Belgique) - fr_BE - fr_BE</li>
               <li>Letton - lv - lv</li>
               <li>Lituanien - lt - lt</li>
               <li>Thai - th - th</li>
               <li>Anglais (Royaume-Uni) - en_GB - en_GB</li>
               <li>Français - fr</li>
               <li>Portugais (Brésil) - pt_BR - pt_BR</li>
               <li>Allemand - de - de</li>
               <li>Danois - da - da</li>
               <li>Finnois - fi - fi</li>
               <li>Hongrois - hu - hu</li>
               <li>Suédois (Finlande) - sv_FI - sv_FI</li>
               <li>Japonais - ja - ja</li>
               <li>Hébreu - lui - lui</li>
               <li>Coréen - ko - ko</li>
               <li>Suédois - sv - sv</li>
               <li>Suède (Suède) - sv_SE - sv_SE</li>
               <li>Slovaque - sk - sk</li>
               <li>Maltais - mt - mt</li>
               <li>Italien (Suisse) - it_CH - it_CH</li>
               <li>Polonais - pl</li>
               <li>Slovène - sl - sl</li>
               <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>Service dynamique</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>end</td>
         <td>Durée de validité</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Page d'erreur</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>Entité géographique</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>Pages</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>identificationByUrlParam</td>
         <td>Identification par paramètres d’URL</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>URL de redirection</td>
         <td>string (4096)</td>
         <td> </td>
      </tr>
      <tr>
         <td>isExternal</td>
         <td>Est une ressource externe</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>isTemplate</td>
         <td>Modèle</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>job</td>
         <td>Traitement</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLogs</td>
         <td>Logs</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>label</td>
         <td>Libellé</td>
         <td>string (128)</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>Dernière modification</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter (queryFilterBase)</td>
         <td>Clé de chargement</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>Paramètres de la clé de chargement</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>logicalStatus</td>
         <td>Statut de l'exécution</td>
         <td>énumération (chaîne) (255)</td>
         <td>
            <ul>
               <li>En cours - commencé - commencé</li>
               <li>Edition - édition - édition</li>
               <li>Terminé - terminé - terminé</li>
               <li>Avertissement - avertissement</li>
               <li>Erroné - erreur - erreur</li>
               <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>Commencer à envoyer un message</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>Message transactionnel</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>modifyBy (userBase)</td>
         <td>Modification par</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>name</td>
         <td>id</td>
         <td>string (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>Entité organisationnelle</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>préremplissage</td>
         <td>Précharger les données du visiteur</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>program (programBase)</td>
         <td>Programme</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>URL publique</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>Date de publication</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>réconciliationFilter (queryFilterBase)</td>
         <td>Clé de réconciliation</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>réconciliationFilterMapping</td>
         <td>Paramètres clés de réconciliation</td>
         <td>collection </td>
         <td> </td>
      </tr>
      <tr>
         <td>réconciliationUpdateStrategy</td>
         <td>Mettre à jour la stratégie</td>
         <td>énumération (octet) </td>
         <td>
            <ul>
               <li>Mise à jour - updateTarget - 1</li>
               <li>Non autorisé - non autorisé - 0</li>
               <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>Service d'abonnement</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>Action spécifique</td>
         <td>énumération (octet) </td>
         <td>
            <ul>
               <li>Liste noire - liste noire - 3</li>
               <li>Aucune action spécifique - aucun - 0</li>
               <li>Désabonnement - désabonnement - 2</li>
               <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
               <li>Abonnement - abonnement - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>start</td>
         <td>Date de déploiement</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>état</td>
         <td>Status</td>
         <td>énumération (octet) </td>
         <td>
            <ul>
               <li>Modification - modifier - 0</li>
               <li>Echec de la publication - échec - 99</li>
               <li>Fermé - fermé - 20</li>
               <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
               <li>En ligne - ouvert - 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>Dimension de ciblage</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>template (landingPage)</td>
         <td>Modèle de page d’entrée</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>URL de test</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>miniature</td>
         <td>Miniature</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>timezone</td>
         <td>Fuseau horaire</td>
         <td>énumération (chaîne) (64)</td>
         <td>
            <ul>
               <li>(GMT-02:00) Centre-Atlantique - Atlantic_South_Georgia - Atlantic/South_Georgia</li>
               <li>(GMT+02:00) Amman - Asia_Amman - Asia/Amman</li>
               <li>(GMT-03:00) Brasi - America_Sao_Paulo - America/Sao_Paulo</li>
               <li>(GMT+06:00) Astana, Dhaka - Asia_Dhaka - Asia/Dhaka</li>
               <li>(GMT+06:00) Novossibirsk - Asie_Novosibirsk - Asie/Novosibirsk</li>
               <li>(GMT+02:00) Windhoek - Africa_Windhoek - Africa/Windhoek</li>
               <li>(GMT+04:00) Caucase, Erevan - Asie_Erevan - Asie/Erevan</li>
               <li>(GMT-04:00) Manaus - Amérique_Manaus - Amérique/Manaus</li>
               <li>(GMT+03:30) Téhéran - Asie_Téhéran - Asie/Téhéran</li>
               <li>(GMT+12:00) Auckland, Wellington - Pacific_Auckland - Pacific/Auckland</li>
               <li>(GMT+02:00) Jérusalem - Asie_Jérusalem - Asie/Jérusalem</li>
               <li>(GMT+03:00) Moscou, Saint-Pétersbourg, Volgograd - Europe_Moscou - Europe/Moscou</li>
               <li>(GMT+09:30) Adelaïde - Australia_Adelaide - Australia/Adelaide</li>
               <li>(GMT+10:00) Canberra, Melbourne, Sydney - Australia_Canberra - Australia/Canberra</li>
               <li>(GMT+08:00) Perth - Australia_Perth - Australia/Perth</li>
               <li>(GMT+09:00) Iakoutsk - Asie_Iakoutsk - Asie/Iakoutsk</li>
               <li>(GMT-10:00) Hawaï - Pacifique_Honolulu - Pacifique/Honolulu</li>
               <li>(GMT+04:00) Bakou - Asie_Bakou - Asie/Bakou</li>
               <li>(GMT+10:00) Vladivostok - Asia_Vladivostok - Asia/Vladivostok</li>
               <li>(GMT+09:00) Séoul - Asie_Séoul - Asie/Séoul</li>
               <li>(GMT+01:00) Sarajevo, Skoplje, Sofia, Varsovie, Zagreb - Europe_Sarajevo - Europe/Sarajevo</li>
               <li>Fuseau horaire du serveur - _server_ - _server_</li>
               <li>(GMT+04:00) Abu Dhabi, Mascate - Asie_Mascate - Asie/Mascate</li>
               <li>(GMT+08:00) Kuala Lumpur, Singapour - Asie_Kuala_Lumpur - Asie/Kuala_Lumpur</li>
               <li>(GMT+09:00) Osaka, Sapporo, Tokyo - Asie_Tokyo - Asie/Tokyo</li>
               <li>(GMT+10:00) Brisbane - Australia_Brisbane - Australia/Brisbane</li>
               <li>(GMT+05:30) Sri Jayawardenepura - Asie_Colombo - Asie/Colombo</li>
               <li>(GMT+02:00) Harare, Pretoria - Africa_Harare - Africa/Harare</li>
               <li>(GMT+08:00) Oulan-Bator - Asia_Ulan_Bator - Asia/Ulan_Bator</li>
               <li>(GMT-02:00) Temps moyen de Greenwich moins 2 heures - Gmt_m2 - Etc/GMT+2</li>
               <li>(GMT-03:00) Temps moyen de Greenwich moins 3 heures - Gmt_m3 - Etc/GMT+3</li>
               <li>(GMT-01:00) Temps moyen de Greenwich moins 1 heure - Gmt_m1 - Etc/GMT+1</li>
               <li>(GMT-06:00) Temps moyen de Greenwich moins 6 heures - Gmt_m6 - Etc/GMT+6</li>
               <li>(GMT-07:00) Temps moyen de Greenwich moins 7 heures - Gmt_m7 - Etc/GMT+7</li>
               <li>(GMT-04:00) Temps moyen de Greenwich moins 4 heures - Gmt_m4 - Etc/GMT+4</li>
               <li>(GMT) Casablanca - Africa_Casablanca - Africa/Casablanca</li>
               <li>(GMT+05:30) Calcutta, Chennai, Mumbai, New Delhi - Asie_Calcutta - Asie/Calcutta</li>
               <li>(GMT-11:00) Heure de Greenwich Moyenne moins 11 heures - Gmt_m11 - Etc/GMT+11</li>
               <li>(GMT-09:00) Temps moyen de Greenwich moins 9 heures - Gmt_m9 - Etc/GMT+9</li>
               <li>(GMT-03:30) Terre-Neuve - America_St_Johns - America/St_Johns</li>
               <li>Valeur par défaut - _héritage_ - _héritage_</li>
               <li>(GMT+03:00) Heure moyenne de Greenwich plus 3 heures - Gmt_p3 - Etc/GMT-3</li>
               <li>(GMT-04:30) Caracas - America_Caracas - America/Caracas</li>
               <li>(GMT+01:00) Amsterdam, Berlin, Berne, Rome, Stockholm, Vienne - Europe_Berlin - Europe/Berlin</li>
               <li>(GMT-07:00) Chihuahua, La Paz, Mazatlan - America_Chihuahua - America/Chihuahua</li>
               <li>(GMT+03:00) Nairobi - Afrique_Nairobi - Afrique/Nairobi</li>
               <li>(GMT-04:00) Asunción - America_Asuncion - America/Asuncion</li>
               <li>(GMT+03:00) Bagdad - Asie_Bagdad - Asie/Bagdad</li>
               <li>(GMT-10:00) Temps moyen de Greenwich moins 10 heures - Gmt_m10 - Etc/GMT+10</li>
               <li>(GMT-03:00) Groenland - America_Godthab - America/Godthab</li>
               <li>(GMT+02:00) Damas - Asie_Damas - Asie/Damas</li>
               <li>(GMT-11:00) Samoa - Pacifique_Samoa - Pacifique/Samoa</li>
               <li>(GMT-05:00) Bogota, Lima, Quito - America_Bogota - America/Bogota</li>
               <li>(GMT+01:00) Bruxelles, Copenhague, Madrid, Paris - Europe_Paris - Europe/Paris</li>
               <li>(GMT+08:00) Pékin, Chongqing, Hong Kong, Urumqi - Asie_Shanghai - Asie/Shanghai</li>
               <li>(GMT+12:00) Fidji - Pacifique_Fidji - Pacifique/Fidji</li>
               <li>(GMT+02:00) Athènes, Istanbul, Minsk - Europe_Athènes - Europe/Athènes</li>
               <li>(GMT+04:00) Tbilissi - Asie_Tbilissi - Asie/Tbilissi</li>
               <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
               <li>(GMT+05:45) Katmandou - Asie_Katmandou - Asie/Katmandou</li>
               <li>(GMT-05:00) Indiana (Est) - America_Indianapolis - Amérique/Indianapolis</li>
               <li>(GMT-01:00) Îles du Cap-Vert - Atlantique_Cap-Vert - Atlantique/Cap-Vert</li>
               <li>(GMT+04:00) Port Louis - Indien_Maurice - Indien/Maurice</li>
               <li>(GMT+08:00) Taipei - Asie_Taipei - Asie/Taipei</li>
               <li>Fuseau horaire de la base de données - _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30) Rangoon - Asia_Rangoon - Asia/Rangoon</li>
               <li>(GMT+11:00) Magadan, Îles Salomon, Nouvelle Calédonie - Pacific_Guadalcanal - Pacifique/Guadalcanal</li>
               <li>(GMT+02:00) Le Caire - Afrique_Le Caire - Afrique/Le Caire</li>
               <li>(GMT+05:00) Iekaterinbourg - Asie_Ekaterinbourg - Asie/Ekaterinbourg</li>
               <li>(GMT+08:00) Irkoutsk - Asie_Irkoutsk - Asie/Irkoutsk</li>
               <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacifique/Guam</li>
               <li>(GMT-04:00) Heure normale de l'Atlantique (Canada) - America_Halifax - America/Halifax</li>
               <li>(GMT) Greenwich - GMT - GMT</li>
               <li>(GMT-04:00) La Paz - America_La_Paz - America/La_Paz</li>
               <li>Fuseau horaire de l’opérateur - _login_ - _login_</li>
               <li>(GMT-06:00) Guadalajara, Mexique, Monterrey - America_Mexico_City - America/Mexico_City</li>
               <li>(GMT+09:30) Darwin - Australia_Darwin - Australia/Darwin</li>
               <li>(GMT-05:00) Est (États-Unis et Canada) - Amérique_New_York - Amérique/New_York</li>
               <li>(GMT-05:00) Temps moyen de Greenwich moins 5 heures - Gmt_m5 - Etc/GMT+5</li>
               <li>(GMT+05:00) Islamabad, Karachi, Tachkent - Asia_Karachi - Asia/Karachi</li>
               <li>(GMT+00:00) Riyad (3), Riyad - Asie_Riyad - Asie/Riyad</li>
               <li>(GMT-08:00) Temps moyen de Greenwich moins 8 heures - Gmt_m8 - Etc/GMT+8</li>
               <li>(GMT-01:00) Les Açores - Atlantique_Açores - Atlantique/Açores</li>
               <li>(GMT+07:00) Bangkok, Hanoï, Djakarta - Asia_Bangkok - Asia/Bangkok</li>
               <li>(GMT) Monrovia - Africa_Monrovia - Africa/Monrovia</li>
               <li>(GMT-09:00) Alaska - America_Anchorage - America/Anchorage</li>
               <li>(GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague - Europe_Belgrade - Europe/Belgrade</li>
               <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
               <li>(GMT+02:00) Bucarest - Europe_Bucarest - Europe/Bucarest</li>
               <li>(GMT+05:00) Heure moyenne de Greenwich plus 5 heures - Gmt_p5 - Etc/GMT-5</li>
               <li>(GMT+04:00) Temps moyen de Greenwich plus 4 heures - Gmt_p4 - Etc/GMT-4</li>
               <li>(GMT+07:00) Heure moyenne de Greenwich plus 7 heures - Gmt_p7 - Etc/GMT-7</li>
               <li>(GMT+06:00) Temps moyen de Greenwich plus 6 heures - Gmt_p6 - Etc/GMT-6</li>
               <li>(GMT+01:00) Heure moyenne de Greenwich plus 1 heure - Gmt_p1 - Etc/GMT-1</li>
               <li>(GMT-08:00) Pacifique (États-Unis et Canada) - Amérique_Los_Angeles - Amérique/Los_Angeles</li>
               <li>(GMT+02:00) Temps moyen de Greenwich plus 2 heures - Gmt_p2 - Etc/GMT-2</li>
               <li>(GMT+07:00) Krasnoïarsk - Asie_Krasnoïarsk - Asie/Krasnoïarsk</li>
               <li>(GMT+09:00) Heure de Greenwich Moyenne plus 9 heures - Gmt_p9 - Etc/GMT-9</li>
               <li>(GMT+08:00) Temps moyen de Greenwich plus 8 heures - Gmt_p8 - Etc/GMT-8</li>
               <li>(GMT+10:00) Hobart - Australia_Hobart - Australia/Hobart</li>
               <li>(GMT+13:00) Nuku'alofa - Pacific_Tongatapu - Pacific/Tongatapu</li>
               <li>(GMT-06:00) Amérique centrale - America_Regina - Amérique/Regina</li>
               <li>(GMT-03:00) Buenos Aires, Cayenne, Fortaleza - America_Buenos Aires - America/Buenos Aires</li>
               <li>(GMT-07:00) Montagnes Rocheuses (États-Unis et Canada) - Amérique_Denver - Amérique/Denver</li>
               <li>(GMT+01:00) Afrique centrale - Ouest - Afrique_Luanda - Afrique/Luanda</li>
               <li>(GMT+02:00) Helsinki, Kiev, Riga, Sofia, Tallinn, Vilnius - Europe_Helsinki - Europe/Helsinki</li>
               <li>(GMT) Heure moyenne de Greenwich : Dublin, Édimbourg, Lisbonne, Londres - Europe_Londres - Europe/Londres</li>
               <li>(GMT-07:00) Arizona - America_Phoenix - America/Phoenix</li>
               <li>(GMT+02:00) Beyrouth - Asie_Beyrouth - Asie/Beyrouth</li>
               <li>(GMT+04:30) Kaboul - Asie_Kaboul - Asie/Kaboul</li>
               <li>(GMT-06:00) Centre (États-Unis et Canada) - America_Chicago - Amérique/Chicago</li>
               <li>(GMT+11:00) Heure moyenne de Greenwich plus 11 heures - Gmt_p11 - Etc/GMT-11</li>
               <li>(GMT+10:00) Temps moyen de Greenwich plus 10 heures - Gmt_p10 - Etc/GMT-10</li>
               <li>(GMT+13:00) Heure moyenne de Greenwich plus 13 heures - Gmt_p13 - Etc/GMT-13</li>
               <li>(GMT+12:00) Heure moyenne de Greenwich plus 12 heures - Gmt_p12 - Etc/GMT-12</li>
               <li>(GMT-04:00) Santiago - America_Santiago - America/Santiago</li>
               <li>(GMT-03:00) Montevideo - America_Montevideo - America/Montevideo</li>
               <li>(GMT-04:00) Cuiaba - America_Cuiaba - America/Cuiaba</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>title</td>
         <td>landing page</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>Consigner les réponses</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>Nom de l’URL de suivi</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>type</td>
         <td>Type</td>
         <td>énumération (octet) </td>
         <td>
            <ul>
               <li>Générique - générique - 0</li>
               <li>Désabonnement d'un service - désabonnement - 3</li>
               <li>Liste noire - liste noire - 4</li>
               <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
               <li>Acquisition - acquisition - 1</li>
               <li>Abonnement à un service - abonnement - 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>ID de sécurité</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Activer le suivi Web</td>
         <td>boolean </td>
         <td> </td>
      </tr>
   </table>

## Filtres

Par état logique (parLogicalStatus)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>état</td>
    <td>enumeration</td>
    </tr>
</table>

Par nom ou étiquette (parTexte)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>texte</td>
    <td>string</td>
    </tr>
</table>

Par état (par état)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>état</td>
    <td>enumeration</td>
    </tr>
</table>

Par ressource de ciblage (parTargetResource)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>

Inclure les pages d'entrée avancées (avec Advanced)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>advanced</td>
    <td>boolean</td>
    </tr>
</table>

Inclure les livraisons continues à partir d’une liste hétérogène (avec Continuous)

<table>
        <tr>
        <th>Nom</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>boolean</td>
        </tr>
    </table>

Présente pendant une période donnée (parCalendar)

<table>
        <tr>
        <th>Nom</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>startDate</td>
        <td>date</td>
        </tr>
        <tr>
        <td>endDate</td>
        <td>date</td>
        </tr>
    </table>

Publié pendant une période donnée (parPlanning)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>
