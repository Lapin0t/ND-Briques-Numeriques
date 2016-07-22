
l'OpenUI
<small>*les briques d'interface utilisateur*</small>
===

## L'objectif

- Toute personnes peut y accéder et répliquer l'information.

## Outils

- [Riotjs](http://riotjs.com/fr/)
- OnsenUI

## Proposition

- Implémenter de serveur de tuile (eg. OpenStreetMap) pour les agendas, forums, actions, projets, etc...

- Proposer aux développeur des composants génériques web
préconfigurer pour communiquer avec les données et favoriser
ainsi la l'accés centralisé des données

  - > **Note** Ces élément sont extrême lié aux type définis dans l'OpenData

  - L'élément `<discussion>` doit offrir les fonctionnalité
 d'accés aux forum

  - L'élément `<vote>` permetterais de visualiser et/ou
  enregistrer son vote que ce soit pour post de forum ou
  pour la délibaration d'une loi.

  - L'élément `<graph>`

  - L'élément `<article>`

  - L'élément `<description>`

  - L'élément `<document>`

  - L'élément `<Citoyen>`

  - L'élément `<Groupe>`

  - L'élément `<Debat>`




> Voir la poposition: [formatage de l'élément Ecrit](OpenUI-Ecrit.md)

---

## Liens entre APIs

Cette API est une retranscription de objets de l'openData.
Elle est donc absolument pas intéropérable.

De même elle est extrêment lié au protocole de communication.

Ces forte contrainte justifit ça présence. Elle permet, aux yeux
des dévellopeur UX de paraitre interopérable...

---

## Outils

- React.js
- Angular.js
- Polymer
- WebComponent
- Knockout.js

---

## A faire

- [ ] Definir les liens avec les autres API
- [ ] Créer des sénarios d'utilisation
- [ ] Implémentation pc (eg. React, Angular)
- [ ] Implémentation pour Android
- [ ] Implémentation pour iOS
- [ ] Implémentation spécifique IoT (eg. Raspberry)
- [ ] ~~Implementation .Net WPF~~

# Conclusion

Vue le nombre d'implementation et la dépendence forte
aux autres API, il vas faloir penssé a une génération
de code automatique...
(eg. [codova](http://cordova.apache.org/))

---