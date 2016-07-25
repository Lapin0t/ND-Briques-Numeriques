L'interface utilisateurs / l'OpenUI
===

## Objectifs

- Regroupe des librairies d'éléments, widgets, composants, etc, réutilisables pour créer les UX.

  > voir les besoins [Interface utilisateurs / OpenUI](https://github.com/corbane/ND-Briques-Numeriques/wiki/D-.L'interface-utilisateurs)

## Propositions

- L'élément [`<discussion>`](discussion) Il doit offrir les fonctionnalités
    d'accès aux forums de discution

- L'élément [`<debat>`](débat)

- L'élément [`<vote>`](débat) Permettrait de visualiser et/ou enregistrer son
    vote que ce soit pour post de forum ou pour la délibération d'une loi.

- L'élément `<article>` Il le seule composant devant imposer une disposition
  graphique. Il doit permette de réaliser des article, documentation, manuel,
  description, etc.
    > Voir [Les données / OpenSchema / Formatage des données
    > écrites](https://github.com/corbane/ND-Briques-Numeriques-api/blob/master/B-Les%20donn%C3%A9es/1-OpenSchema/Formatage%20des%20donn%C3%A9es%20%C3%A9crites.md)

- L'élément `<Citoyen>`

- L'élément `<Groupe>`

## Liens entre APIs

Cette API est une retranscription de objets de l'OpenSchema. Elle est donc
absolument pas interopérable.

Cette forte contrainte justifie sa présence. Elle doit permettre, aux yeux des
développeur UX de paraitre interopérable...

## A faire

- [ ] Inventorier les compétences avec les outils de dev front-end (eg.
  cordova, ionic, xamarin, etc)
- [ ] Se mettre d’accord sur l’utilisation d’un framework type cordova, ionic,
  etc (ou pas)
- [ ] Inventorier les compétences avec les outils front-end de composants (eg,
  React.js, Riotjs, OnsenUI, Angular.js, Polymer, WebComponent, Knockout.js,
  Vue.js)
- [ ] Evaluer la solution React.js [Radium](http://stack.formidable.com/radium/)
  permettant de dissocier la logique du style des composants.
