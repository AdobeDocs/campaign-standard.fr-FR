---
title: DataModel
description: En savoir plus sur le modèle de données
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# Profil (nms:destinataire)

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
                  <td>âge</td>
                  <td>Âge</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>appSubscription</td>
                  <td>Abonnements à une application</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>Date de naissance</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackList</td>
                  <td>Ne plus contacter (tous canaux)</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>Ne plus contacter par email</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>Plus de contact par fax</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>Ne plus contacter par SMS</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>Plus de contact par téléphone</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>Plus de contact par courrier électronique</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>Plus de contact par notification Push</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pays (pays)</td>
                  <td>Pays</td>
                  <td>link </td>
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
                  <td>cryptedId</td>
                  <td>ID chiffré</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>Date de dernière transaction</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>Transactions</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>domain</td>
                  <td>Domaine de l'email</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Email</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Format des emails</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Texte - Texte - 1</li>
                        <li>HTML - html - 2</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Inconnu - inconnu - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>emailStatus (addressStatus)</td>
                  <td>Informations sur le courrier électronique</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Exclus</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>Prénom</td>
                  <td>string (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>gender</td>
                  <td>Genre</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Non spécifié - inconnu - 0</li>
                        <li>Homme - Homme - 1</li>
                        <li>Femme - Femme - 2</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Est une ressource externe</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Dernière modification</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastName</td>
                  <td>Nom</td>
                  <td>string (50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emplacement</td>
                  <td>Localisation</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>journaux</td>
                  <td>Logs de diffusion </td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>Deuxième prénom</td>
                  <td>string (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Mobile</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifyBy (userBase)</td>
                  <td>Modification par</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>phone</td>
                  <td>Téléphone</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>place</td>
                  <td>Localisations</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>postalAddress</td>
                  <td>Adresse postale</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>salutation</td>
                  <td>Titre</td>
                  <td>string (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
                  <td>Etat</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subHisto</td>
                  <td>Applications mobiles</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abonnements</td>
                  <td>Abonnements</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniature</td>
                  <td>Miniature</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>timeZone</td>
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
                        <li>(GMT+06:30) Rangoon - Asia_Rangoon - Asia/Rangoon</li>
                        <li>(GMT+11:00) Magadan, Îles Salomon, Nouvelle Calédonie - Pacific_Guadalcanal - Pacifique/Guadalcanal</li>
                        <li>(GMT+02:00) Le Caire - Afrique_Le Caire - Afrique/Le Caire</li>
                        <li>(GMT+05:00) Iekaterinbourg - Asie_Ekaterinbourg - Asie/Ekaterinbourg</li>
                        <li>(GMT+08:00) Irkoutsk - Asie_Irkoutsk - Asie/Irkoutsk</li>
                        <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacifique/Guam</li>
                        <li>(GMT-04:00) Heure normale de l'Atlantique (Canada) - America_Halifax - America/Halifax</li>
                        <li>(GMT) Greenwich - GMT - GMT</li>
                        <li>Par défaut - aucun - aucun</li>
                        <li>(GMT-04:00) La Paz - America_La_Paz - America/La_Paz</li>
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
                  <td>Profil</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracking</td>
                  <td>Tracking</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
            </table>


## Filtres


Anniversaire (anniversaire)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>includeStart</td>
<td>boolean</td>
</tr>
<tr>
<td>previousUnitsValue</td>
<td>integer</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>integer</td>
</tr>
<tr>
<td>endDay</td>
<td>date</td>
</tr>
<tr>
<td>précision</td>
<td>enumeration</td>
</tr>
<tr>
<td>relativeValue</td>
<td>string</td>
</tr>
<tr>
<td>mois</td>
<td>date</td>
</tr>
<tr>
<td>opérateur</td>
<td>enumeration</td>
</tr>
<tr>
<td>includeEnd</td>
<td>boolean</td>
</tr>
<tr>
<td>endMonth</td>
<td>date</td>
</tr>
<tr>
<td>type</td>
<td>enumeration</td>
</tr>
<tr>
<td>jour</td>
<td>date</td>
</tr>
</table>

Par courriel (par courriel)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>email</td>
<td>string</td>
</tr>
</table>

Par clés (parKeysProfile)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>email</td>
<td>string</td>
</tr>
</table>

Par nom ou adresse électronique (parTexte)

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

Par audience statique (byStaticAudience)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>audience</td>
<td>link</td>
</tr>
</table>

Clicked (hasClickedDelivery)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>livraison</td>
<td>link</td>
</tr>
</table>

Ouvert (hasOpenedDelivery)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>livraison</td>
<td>link</td>
</tr>
</table>

Profil (profil)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>profil</td>
<td>link</td>
</tr>
</table>

Reçu (hasReceivedDelivery)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>livraison</td>
<td>link</td>
</tr>
</table>

Abonnés (abonnés)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>service</td>
<td>link</td>
</tr>
</table>