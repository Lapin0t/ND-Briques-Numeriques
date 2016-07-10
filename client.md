

# Nœud client

Api JavaScript pour les clients.

## L'objectif

- Offrir une interface simple au designer d'UX
- Avoir une couche indépendante et interopérable
- Permettre aux non développeurs de lire et écrire des données

## L'idée <small>(actuel)</small>

Un module permet de réaliser les requêtes de cette maniére:
Détail de la recherche ici : [OpenQuery](OpenQuery.md)

```javascript
srv
    .groupe('NuitDebout')
    .lieu('Paris')
    .groupe('ecologie')
    .actions
    .LIRE_RESULTATS();
```

Dans cette requete il est chercher les actions des ecologie
dans la communauté NuitDebout de Paris.

Les type de données
===


### La classe de base :
> Toutes les autres élément dérive de cette classe.

```typescript
interface Atome {
    private _type: type;
    private _noeudsAccepter: Array<type>;
    private _noeudsExplicites: Array<type>
}
```

### Les éléments globaux :
> Ces éléments peuvent ce contenirent eux même. Par exemples
> l'événement d'un festival peut comporter plusieurs événements 

```typescript
interface Groupe    extends Atome {}
interface Evenement extends Atome {}
interface Projet    extends Atome {}
```

### Les éléments individuel :
> Ces éléments ne peuvent n'y se contenir, n'y contenir des élément
> de départ mais peuvent contenir d'autre éléments. Par exemple un
> article ne contiendra pas un projet, ce sera le projet qui as un article

```typescript
interface Citoyen extends Atome {}
interface Message extends Atome {}
interface Article extends Atome {}
```

### Les éléments de definition :
> Ces éléments ne peuvent contenir aucun autre éléments.

```typescript
interface Description     extends Atome {}
interface Date            extends Atome {}
interface Localisation    extends Atome {}
interface AdresseInternet extends Atome {}
interface Adresse         extends Atome {}
interface Vidéo           extends Atome {}
interface Audio           extends Atome {}
interface fichier         extends Atome {}
interface prix            extends Atome {}
```

### Pour les systémes de votes :

> il y a beaucoup de possibilité de processus de votes.
(voir [contrainte prise de décisions]()) \
donc la contrainte est de pouvoir facilement créer des processus de votes
de tout type.

quelques exemple de processus de vote:
vote par majorité, par concensus, ...

Je propose de mettre à disposition une API de type Flow graph avec des fonction de calcule.
(type excel)
```
facteur = 0.75;
moyenne = SOMME(votes) / NOMBRE(votes) * 0.75
SI note >= moyenne ALORS VALIDE
SI NON INVALIDE
```
(oui bon ce n'est pas encore trés claie :/ )

## Pour les messages

voir ClientUI.md #messages

Le type message  :

```typescript
interface Message {}
```

Les types de message dérivés :

```typescript
interface Tweet extends Message {}
interface postFacebook extends Message {}
interface telegramMessage extends Message {}
```

## Pour les connaissances

Alors les infos c'est fachement important et c'est aussi notre point faible,
la transmition des savoir. \
[A noter que cette api n'as pas pour but de créer du contenu]

Les types de connaissances  :

- Des photos.
- Des articles.

Les étapes de travail

1) Dans un premier temp que les groupes ce plis à des contraintes que
nous imposerons: par exemple les obligé à remplire un formulaire type openSearch
pour être référencer chez nous.
2) Dans un deuxiéme temp il faudrais faire des fonction d'import spécifique aux
plus grose sources de données: eg.: Facebook, Tweeter, Google plus, ...
3) Dans (trés longtemps) nous devrons serement réaliser des robot
de recherche de contenu....

Donc quel sont les briques ?



```typescript
t.auteurs = t.Types.ListeDeCitoyens;
t.connaissance = new schema(
    date(),
    descrition(),
    tag(),
    theme(),
    auteurs()
)
```

Les type de liens entre éléments
===

! En faut il ?

un article DECRIT [d'un citoyen, d'un groupe, d'un projet ...] \
un Groupe ORGANISE un evenment, projet

Je pense que la direction d'un lien entre élémenetsdéfinit les types de lien: \
Citoyen -> Projet = REALISE \
Evenement -> Date = QUAND \
Debat -> Vote = RESULTAT  