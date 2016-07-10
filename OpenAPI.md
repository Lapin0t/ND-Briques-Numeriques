L'OpenAPI
===

## Le context

Sur la question « Qu’elle application pour l’e-démocratie », il a été très rapidement constater un nombre important d’idées et d’envies.
Nous avons donc conclu par la proposition d’étudier une Open API et des Open Data. Cela permettra de ne pas avoir à programmer la structure, le stockage et l’accès aux données pour chacune des applications développer. 

## Les contraintes

Nous nous sommes créées un graph des composents afin d'anticiper le travail à faire.

![](https://i.imgur.com/dLwSkxX.png)

## Ma vision perso <small>(jmv_archi)</small>

- Les utilisateurs sont au plus proche des fonctionnalités proposées.
- Les utilisateurs ne sont pas développeur et pourtant ils aiment adapter leurs outils à leurs besoins.
- Les utilisateurs ne parlent pas tous anglais.

Donc
- Une API & DATA générique.
- Un language de programmation simple.
	- Proposition: JavaScript posséde un large doc française et une souplesse d'utilisation
- Une interface de programmation simple.
	- Proposition: Editeur de programmation visuel. (cf: [grasshopper](http://www.grasshopper3d.com/))

L'API
===


### System

type de servers:

- Des niveaux de serveur (un peu comme les niveau de zoom d'un serveur de tuile)

```ts
server.getSurrounding(level)
```

- Le projet IPFS - BitTorrent

```ts
torrent.numPeers()
```

Exemple:
Pour un agendas, les calques peuvent être ordonée par
-   le lieu des événemeent
-   L'année puis le mois et le jour


Il peut donc avoir des noeud-server avec la définition d'un continent,
d'autre avec le définition des pays et enfin des villes.

Ou alors une db pour les années, une pour les mois et une pour les jours

    ! Donc comment décider de quel noeud arra tel ou tel db ? dynamic ?

Pour des fichiers, ils peuvent être ranger celon
-   leur type ?
-   leur expéditeur(donc géographique) ?


    ! Peut être étudier du hadware pour les noeuds serveur ? qui fais les réparations ?
    ! On pourais (si fichier dll/so pas trop lourde les tester entre elle pour identification)

type de connextion:

```ts
node1.multipleConnection = (true | false);
node1.connect(node2);
node1.onNewConnection    = (nodeClient) => {}
node1.onDeleteConnection = (nodeClient) => {}
node1.onReception        = (nodeClient, pack) => {}
node1.send(nodeDestination, pack, ar);
node1.getSurrounding()
```

### Les classes générique:
```ts
class Atom {
	nom: String;
	lier(atom: Atom);
}
class Liaison {
	public source: Atom;
	public target: Atom;
}
```




### Les classes majeurs

#### Les classes sources

Les classes source représentent les elements constituant les autres éléments.
Il y a les personnes physique ou morale.

efinitions:
```ts
class Citoyen extends Atom {
	public atomAccepter = [
		Description,
		Besoin
	]
}

class Groupe extends Atom {
	public atomAccepter = [
		Groupe,
		Citoyen,
		Description,
		Agenda,
		Geolocalisation,
		Weblocalisation,
		Besoin
	];
}
```

#### La Taxinomie 

Elles peuvent être peuvent etre par exemple:
- Ecologie
- Argriculture
- Architecture
- Economie
- Emploi
- Commerce
- Politique
- Voyage
- ...


:::warning
Wikipédia indique:
> La taxinomie est une science qui cherche à établir un rang systématique et hiérarchisé d'un ensemble d'entités (les taxons) selon les caractères qu'ils ont en commun, des plus généraux aux plus particuliers.

Il est sera donc néssésaire de faire une étude pour ordoner ces éléments (ex: Architecture, logement, urbanisme) 

quel sont les méthodes pour ordonné les noms propre ?
-> voir thesaurus
:::

définition:
```typescript=
class Axom extends Atom {
	public atomAccepter = [
		Description,
		Besoin,
		Groupe
	]
}
```

- Affaires international
- Environnement & Énergie
	- Ecologie
- Enseignement & Recherche
- Finances
- Sociales
	- Famille
	- Jeunesse
	- Retraités
	- Chômeurs
- Santé
- Défense
- Justice
- Travail
	- Chomage
	- Formation
	- 
- Aménagement du territoire 
	- Urbanisme
		- Zone économique
		- Zone industriel
		- Zone commercial
		- Zone résidentiel
	- Transport
- Agriculture
- Culture & Communication


- Culture
- Économie &amp; Industrie
- Écologie &amp; Énergie
- Éducation &amp; Recherche
- Emploi
- Famille &amp; Jeunesse
- Finances
- Institutions politiques
- Logement
- Numérique
- Outre-mer
- Politique étrangère
- Sécurité &amp; Défense
- Social &amp; Santé
- Sports &amp; Loisirs
- Transport


### Les classes democratique:


> Cette section de l'API est pour le moment trés flou. Aucune méthode de vote n'est apparu comme unanime.
Prevoir donc une grande flexibilité.

> Peut être prévoir une API de description d'étape (type flow graph) ?


```javascript=
class Etapes extends Atom {
	atomAccepter = [ Debat, Proposition, Opposition ]
}
class Operation extends Etape {
	etapeSuivante: Etape
}
class Condition extends Etape {
	etapeValide: Etape;
	etapeInvalide: Etpe;
}
```

#### Pour des votes par accord majoritaire


```javascript=
vaj vote_majoritaire = etapes (
	Operation(
		"propositions",
		proposition("1"),
		proposition("2"),
		proposition("3")
	),
	Operation(
		"vote"
	)
)
```

#### Pour des vote par consensus:

Un consensus aboutis l'orsque plus une seule opposition est levé.
Lorsqu'une personnes s'oppose à une ou des propositions elle à l'obligation d'y apporter et/ou de travailler collectivement a des soulutions.
voici les étapes:
![](https://i.imgur.com/4ksktES.png)


```typescript=
class Debat extends Atom {
	public atomAccepter = [
		Agenda,
		Date,
		Opposition,
		Proposition,
		Vote
	];
}
class Opposition extends Atom {}
class Proposition extends Atom {}
class Vote extends Atom {}
enum DebatProgression { A_DEBATRE, EN_DEBAT, DICIDER }
```

### Les classes finis:
```typescript=
class Date extends Atom {
	public atomAccepter = null;
}
class Localisation extends Atom {
	public atomAccepter = null;
}
class Weblocalisation extends Atom  {
	public atomAccepter = null;
}
class Description extends Atom {
	public atomAccepter = null;
}
```


### Les classes de dialogue:
```typescript=
class Commentaire extends Atom {
	public atomAccepter = [Commentaire];
}
```

### Les classes evenementiels

```typescript=
/* Les class scalaire */
class Agenda extends Atom {
	public atomAccepter = [
		Evenement
	];
}
class Evenement extends Atom {
	public atomAccepter = [
		Date,
		Description,
		Geolocalisation,
		Weblocalisation
	];
	public typeDeriver = [
		Reunion, Action, Concert
	]
}
```

Proposition d'objectif
===

## L'API

### Usage

#### Ce connecter:

```javascript=
var db = require('DB.js').connect('www.nuitdebout.fr/db.php');
```

Ici nous souhaitons connaitre les débats portant sur l'architecture
```javascript=
db.theme('architecture').debats();
```

Ici nous cherchons à connaitre les besoins pour les actions futur portant sur l'écologie
```javascript=
db.theme('écologie').actions.date(Date.Now).besoins();
```
Ici nous cherchons tout les article tager 'cop21' durant l'année 2016.
```javascript=
db.articles.date('0/0/2016').hashtag('cop21')();
```

#### Créer un groupe:

```javascript=
var grp = groupe (
	"ArchiDebout",
	description("..."),
	citoyen(UID, ...),
	projet (
		"Manifeste",
		description("..."),
		etude(
			"Manifest Micjelin",
			date("0/0/2015"),
			article( weblocalisation("http://...") ),
			article( weblocalisation("http://...") )
		)
	),
	groupe (
		"Pôle construction",
		description("..."),
		projet(
			"Dôme étoile",
			description("..."),
			ND.groupe("gazetteDebout").article("Les iglous de ND")
		)
	)
);
grp.creer();
```

#### Ajouter des liaisons:

```javascript=
var serveur = require("ND.js");
serveur.lieu("paris").groupe('ND')();

ND.groupe("ecologie").lier (
	action (
		"Manifestation anti-OGM",
		date("10/05/2016"),
		besoin(
			article()
		)
	)
)
```

les interfaces
===

#### L'objectif:

- Etre le plus léger possible
- Avoir un maximum de mécnisme côté client

#### Définition d'une interface:

NON !!!!!

voir [http://www.unheap.com/section/user-interface/page-layout/](http://www.unheap.com/section/user-interface/page-layout/)

Il existe les format
- YAML
- L'encien JavaFX

```typescript=
module UI {
	public function charger(path: string);
	
} 
```

- Je souhaite voir les evenements pret de chez moi ?
- Je souhaite voir / les evenements sur l'écologi pret de chez moi / qui sont pret de chez moi
- Je souhaite proposer une actions
- Je souhaite voir les actions / qui ont été faitent entre le 8 et 10 avril

```typescript=
srv.agenda.lieu(HERE);
srv.agenda.lieu(HERE).sujet('ecologie'); 
srv.moi.actions.ajouter(...);
srv.actions(TOUS).date('01/05/2016', '10/05/2016');
```


