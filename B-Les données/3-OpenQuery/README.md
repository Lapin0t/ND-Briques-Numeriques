Les données / OpenQuery
===

## Objectifs

1. Centraliser l'accès aux informations _(l'accès pas les données bien sur)_

## Description

L’OpenQuery est une API façade pour accéder à la base de données destiné aux développeurs.
Sa simplicité, lisibilité et documentation doit permettre :
-	Aux intégrateur d’UX de ne pas ce soucié des contraintes réelles qu’impose le choix d’un système de stockage de données.
-	Facilité des initiatives à créer des plugins WP, Drupal, etc, pour que chaque asso ayant leur site puisse mettre à jour leurs données sans passer par une nouvelle plateforme
-	Et surement pleins d'initiatives auquel on ne peut penser…

## Etudes de cas

> Note :
> - Les requetés sont écrites dans une syntaxe aussi simple a analysé qu’une calculatrice basique (+, -, / et parenthèses)
> - Ce genre de requête est tout à fait envisageable avec des bases de données graph.

### Le nouveau venu

Tentons de réaliser le chemin d’une personne n'ayant pas encore participé au mouvement NuitDebout

#### 1) Nuit debout ! c'est quoi ?

```js
articles / tag( 'NuitDebout' )
```

Ici touts les articles du groupe NuitDebout sont retournés.
Le problème est qu'il va en avoir beaucoup. Donc il est essentiel de présenter les résultats de manière lisible (et probablement global)
Donc l’UI doit assurer, voici des idées de présentations :

- Spacialiser sur une ligne de temps
- Spacialiser les résultats sur une carte
- Spacialiser les notions générale
  - voir le travail de philippe Esling :
  [Democrite](https://github.com/esling/democrite)
- bref voir [UX](../../D-L'interface utilisateurs/2-UX) ...


#### 2) Ah ! L'aide aux refugié m'intérese !

```js
theme( 'réfugiés' ) / articles + groupes + evenements
```

#### 3) Oh ! Une collecte de matériel de camping est réaliser devant la bibliothéque !

```js
lieu( 'St Thomas les bidules' ) / theme( 'réfugiés' ) / tag( 'collecte' ) / evenements
// ou directement avec l'identifiant
evenement( 'fdj15jgc83jj4269lk' )
```

---

### L'actif d'un événement

Imaginons le chemin d’une personne souhaitant se rendre actif d'un évènement. Prenons pour exemples la collecte pour les réfugiés.

#### 1) C'est quoi le programme ?

```js
evenement( 'fdj15jgc83jj4269lk' ) / CR + actions + evenements
```

### Pèle mêle

Ici nous souhaitons connaitre les débats portant sur l'architecture
```js
theme( 'architecture' ) / debats
```

Ici nous cherchons à connaitre les besoins pour les actions futur portant sur l'écologie
```js
theme( 'écologie' ) / actions / depuis( '31/03/2016' ) / besoins
```

Ici nous cherchons tous les article taguer 'cop21' durant l'année 2016.
```js
articles / date( '0/0/2016' ) / .tag( 'cop21' )
```
