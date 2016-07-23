
L'interface utilisateurs / l'OpenUI
===

## Description

- Proposer aux intégrateur UX des composants génériques web préconfigurer pour communiquer avec les données et favoriser ainsi l'accès centralisé des données.
- Leurs réaliser la logique applicative et les laisser libre sur la représentation graphique des composants

  **Note** Ces élément sont extrêmement lié aux type définis dans l'OpenData

  - L'élément `<discussion>`
    Il doit offrir les fonctionnalités d'accès aux forums de discution

  - L'élément [`<Debat>`](Débats)

  - L'élément `<vote>`
    Permettrais de visualiser et/ou enregistrer son vote que ce soit pour post de forum ou pour la délibération d'une loi.

  - L'élément `<article>`
    Il le seule composant devant imposer une disposition graphique. Il doit permette de réaliser des article, documentation, manuel, description, etc…
    Voir [Formatage des données écrites](https://github.com/corbane/ND-Briques-Numeriques-api/blob/master/B-Les%20donn%C3%A9es/1-OpenSchema/Formatage%20des%20donn%C3%A9es%20%C3%A9crites.md) de l'OpenSchema.

  - L'élément `<Citoyen>`

  - L'élément `<Groupe>`

## Liens entre APIs

Cette API est une retranscription de objets de l'OpenSchema. Elle est donc absolument pas interopérable.

Cette forte contrainte justifie sa présence. Elle doit permettre, aux yeux des développeur UX de paraitre interopérable...

---
# Conclusion

Vue le nombre d'implementation et la dépendence forte
aux autres API, il vas faloir penssé a une génération
de code automatique...
(eg. [codova](http://cordova.apache.org/))

---

## A faire

- [ ] Inventorier les compétences avec les outils front-end de composants
      (eg, React.js, Riotjs, OnsenUI, Angular.js, Polymer, WebComponent, Knockout.js, Vue.js)
- [ ] Evalué la solution React.js [Radium(]http://stack.formidable.com/radium/) permettant de dissocier la logique du style des composants.
- [ ] Inventorier les compétences avec les outils de dev front-end
      (eg. cordova, ionic, xamarin, etc...)
