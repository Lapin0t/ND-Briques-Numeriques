OpenFlowProcess
===

Ce qui existe :

- Un langage de FlowGraph (pas trés lisible et instinctif)

Proposition :

```js
PROCEDURE DE DEPART 'Concenssus-test-1'
1:  DISCUTER + PROPOSER + VOTER (
        pendant: maximum: "3 mois" minimum: "1 mois"
    )
2:  SI PROPOSITIONS == 1 ALORS
        VALIDER ( PROPOSITION(1) )
    SI NON
        CHOISIR
            PROCEDER A 'grooupes de travail'
            CONTINUER ETAPE 2
        OU
            CONTINUER ETAPE 1
        FIN DE CHOISIR
    FIN DE SI
3:  PROCEDER A 'Definition des besoins' +
    PROCEDER A 'Definition du planning théorique'
FIN DE PROCEDURE DE DEPART
```

Et / Ou

! Bon plutôt que de refaire un langage de prog il devrait être
plus rapide de créer une interface visuel de programmation ... ? \
eg: node-red ou grasshopper en beaucoup simple bien sur

## Les fonctionnalités de description

- Definir des procedures `PROCEDURE <nom>`
- Appeler des procedures `PROCEDER <nom>`
- Definir des actions `DISCUTER PROPOSER VOTER`
  - Definir les détails des actions (durée, méthode, etc...)
- Definir des conditions `SI ... ALORS ... SI NON ... FIN DE SI`
- Definir des posibilité `CHOISIR ... OU ... FIN DE CHOISIR`

## Outils

- Analyseur syntaxique JavaScript [peg.js]()

## A faire

- [ ] Definir la syntaxe
- [ ] Definir les connexions avec les autres API
- [ ] Editer des scenarios