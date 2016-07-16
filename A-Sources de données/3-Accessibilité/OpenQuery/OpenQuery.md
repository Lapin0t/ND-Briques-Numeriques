L'OpenQuery
<small>Recherche sue la base de données</small>
===

:grey_exclamation:
La philosophie "Donne moi des légos et je construirais" est partie prenante
de ce cahier des charges. Les éléments de codage sont donc en français.
et les requête serveur sont écrite au plus compréhensible.

## Scènarios

---

### Le nouveau venu

> Tentons de réaliser le chemin d'un personnes n'ayans pas encore participé
> au mouvement NuitDebout

#### 1) Nuit debout ! c'est quoi ?

```js
tag("NuitDebout") / articles
```
> Ici touts les articles du groupe NuitDebout sont retournés. \
Le probléme est qu'il va en avoir beaucoup. Donc il est écentiel
de présenter les résultats de maniére lisible (et probablement global) \
La présentation peut être faitent :

- Par théme. \
  WebComponent `<VueTheme recherche="...">`
- Par géographie. \
  WebComponent `<VueCarte recherche="...">`
- Par co-occurence d'idées \
  voir le travail de philippe Esling :
  [Democrite](https://github.com/esling/democrite) \
  WebComponent `<VueCoOccurences recherche="...">`


#### 2) Ah ! L'aide aux refugié m'intérese !

```js
therme("réfugiés") / articles + actions + groupes + evenements
```

> Ici et affiché plus d'éléments sur le sujet en question
La présentation peut être faitent :

- Par types *(articles, actions, groupes, evenements)* \
  WebComponent: `<VueTypes>`
- Par théme.
- Par géographie.

#### 3) Oh ! Une collecte de matériel de camping est réaliser devant la bibliothéque !

```js
lieu("St Thomas sur Seine") / tag("collecte,réfugiés") / evenements
// ou directement avec l'identifiant
evenement(fdj15jgc83jj4269lk)
```

> La présentation peut être faitent :

- Par une vue description \
  WebComponent: [`<Ecrit>`]()

---

### L'actif d'un événement

> Imaginons le chemin d'une personnes souhaitant se rendre actif
> d'un évéenement. Prenons pour exemples la collecte pour les refugiés. 

#### 1) C'est quoi le programme ?

```js
evenement(fdj15jgc83jj4269lk) / CR + actions + evenements
```

> Que ce soit pour un evenement, une action, ou un compte rendu
> la présentation peut être faitent : via une [`<Ecrit>`]()

#### 2)  

Ici nous souhaitons connaitre les débats portant sur l'architecture
```js
db.theme('architecture').debats();
```

Ici nous cherchons à connaitre les besoins pour les actions futur portant sur l'écologie
```js
db.theme('écologie').actions.date(Date.Now).besoins();
```
Ici nous cherchons tout les article tager 'cop21' durant l'année 2016.
```js
db.articles.date('0/0/2016').hashtag('cop21')();
```