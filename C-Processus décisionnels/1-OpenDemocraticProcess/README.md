OpenDemocraticProcess
===

:dizzy: Bon alors là c’est encore au stade « projet sur la comète ! » mais si ça peut donner des idées, why not ! :)

## Prérequis

Voir les [objectifs et synthéses](https://github.com/corbane/ND-Briques-Numeriques/tree/master/C-Processus%20d%C3%A9cisionnels) du hackathon

## Propositions _(Qui peuvent être compatibles)_

### Reéaliser un panel types de processus de vote

#### A faire

- [ ] Inventorier les processus de vote existants

---
### Definir un language de définition de processus

> Dans l’idée de permettre aux bidouilleurs non développeur de réaliser leurs processus de votes pour les besoins spécifique de leur asso, collectif, orga, etc...

#### Fonctionnalités de description:

- Definir des procedures `PROCEDURE <nom>`
- Appeler des procedures `PROCEDER <nom>`
- Definir des actions `DISCUTER PROPOSER VOTER`
  - Definir les détails des actions (durée, méthode, etc...)
- Definir des conditions `SI ... ALORS ... SI NON ... FIN DE SI`
- Definir des posibilité `CHOISIR ... OU ... FIN DE CHOISIR`

#### Exemple:

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

#### A faire

- [ ] Definir la syntaxe

---
### Créer un interface de programmation visuel

> Dans l’idée de permettre aux plus grand nombre d'utilisateurs de réaliser leurs processus de votes

Une interface utilisateur permettant visuellement du type red-node, grasshopper, noflo, etc...

<img src="visual-programing-nodes.png"/>

#### A faire

- [ ] Definir les fonctions utilent

---

## A faire dans tous les cas

- [ ] Definir les connexions avec les autres API
- [ ] Editer des scenarios

---
## Outils

> CHARTRE :
> -	:exclamation: N’indiquer que les outils, librairies que vous avez déjà utilisés, Les copier-coller de liens web sont inconstructif.
> - :exclamation: Le but n’est pas de faire un recensement mais une liste d’outil envisageable immédiatement. (On oubliera donc les outils trop jeunes même avec de belles perspectives)
> -	Prenez le temps d’expliquer les avantages et inconvénients de l’outil
> -	Si l’outil demande plus de détail (et si vous êtes d’accord), veuillez indiquer un moyen de vous joindre. ex. pseudo racket chat, email, etc…

voir [outils.csv](../outils.csv)
