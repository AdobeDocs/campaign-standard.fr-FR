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


# Membre de semences (nms:seedMember)

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
                  <td>desc</td>
                  <td>Description</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Email</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailRendering</td>
                  <td>Rendu des emails</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Entité géographique</td>
                  <td>link </td>
                  <td> </td>
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
                  <td>emplacement</td>
                  <td>Localisation</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marketingCloudId</td>
                  <td>Identifiant Marketing Cloud</td>
                  <td>string (256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>Application mobile</td>
                  <td>item </td>
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
                  <td>name</td>
                  <td>id</td>
                  <td>string (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_Recipient</td>
                  <td>Profil</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>Evénement</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entité organisationnelle</td>
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
                  <td>preuve</td>
                  <td>Bon à tirer</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification</td>
                  <td>notification push</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registerToken</td>
                  <td>Jeton d'enregistrement</td>
                  <td>string (256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampleData</td>
                  <td>Exemple de données</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sms</td>
                  <td>Mobile</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
                  <td>Etat</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetData</td>
                  <td>Extension</td>
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
                  <td>title</td>
                  <td>Profil de test</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>piège</td>
                  <td>Piège</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
            </table>

## Filtres

Par type d’événement (byEventType)

<table>
        <tr>
        <th>Nom</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>eventType</td>
        <td>string</td>
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

Par utilisation (byUsage)

<table>
        <tr>
        <th>Nom</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>piège</td>
        <td>boolean</td>
        </tr>
        <tr>
        <td>emailRendering</td>
        <td>boolean</td>
        </tr>
        <tr>
        <td>preuve</td>
        <td>boolean</td>
        </tr>
    </table>

Profil de test (profil)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>seedMember</td>
    <td>link</td>
    </tr>
</table>