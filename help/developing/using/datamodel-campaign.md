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
source-git-commit: 8f47bf0cc1d5f694df1e1829ccd03c72df28d7de

---


# Campaign (nms:campaign)

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
                  <td>activités</td>
                  <td>Activités</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>buildingIn</td>
                  <td>Objet d’application intégré</td>
                  <td>boolean </td>
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
                  <td>durée</td>
                  <td>Durée de la campagne</td>
                  <td>nombre </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>end</td>
                  <td>Date de fin</td>
                  <td>date </td>
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
                  <td>isTemplate</td>
                  <td>Modèle</td>
                  <td>boolean </td>
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
                  <td>program (programBase)</td>
                  <td>Programme</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Rapports en temps réel</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Date de début</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>status</td>
                  <td>Status</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Démarré - démarré - 1</li>
                        <li>Modification - édition - 0</li>
                        <li>Terminé - terminé - 2</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>template (campaign)</td>
                  <td>Modèle de campagne</td>
                  <td>link </td>
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
                  <td>Campaign</td>
                  <td>string (255)</td>
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

Par période (par période)

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
    <td>timePeriod</td>
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

Planifiée pour la période donnée (parPlanning)

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