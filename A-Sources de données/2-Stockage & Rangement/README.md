
A-Sources de données / Stockage & Rangement
===

## Objectifs

1.	Décentraliser le stockage des données.
2.	Replacer l'information dans son contexte
3.	Organisation & Tris personnalisable 
4.	La mémoire. Conservé et réutiliser l'information.

## Actuellement

- _(1)_ Le groupe de réflexion [Chat Réseaux Mesh & P2P](https://wiki.nuitdebout.fr/wiki/R%C3%A9seaux_Mesh_%26_P2P)
- _(4)_ Le groupe de réflexion [Mémoire Commune](https://wiki.nuitdebout.fr/wiki/Villes/Paris/Accueil_et_coordination/M%C3%A9moire_Commune#Stockage_num.C3.A9rique)

_Aides_

- _(1)_ [Article p2p](http://schuler.developpez.com/articles/p2p/)
- _(3)_ [Introduction-neo4j](http://logisima.developpez.com/tutoriel/nosql/neo4j/introduction-neo4j/#LI-E-8)

## Propositions

Ojectif 1:
- _!! AUCUNE !!_

Ojectif 2:
- _!! AUCUNE !!_

Ojectif 3:
- Utiliser une base de données graph. (eg. Neo4j). 

Ojectif 4:
- _!! AUCUNE !!_

## Solutions temporaire

Pour le moment, réaliser un réseau maillé efficace ne semble pas à notre porté.
Donc il serait possible de continuer avec les base de données centraliser Le point important est d'avoir une interface de programmation interopérable.
Les langages de requête permettent une flexibilité.

Cypher: `(c:Citoyen) --> NuitDebout, (c) --> (programmeur)`


```sql
CREATE (e1:Group {n: 'NuitDebout'})
CREATE (e2:Commission {n: 'Logistique'})
CREATE (e3:Commission {n: 'Architecture'})
CREATE
    (e2)-[:IN]->(e1),
    (e3)-[:IN]->(e1)
```

## Outils

> ! Ce serais utile de lister ici les travaux et librairies existante, stable et donc envisageables des aujourd’hui !

voir les travaux de philippe Esling [Democrite](https://github.com/esling/democrite)

---

wealth talent exclude fiscal skill junk erase tackle waste lonely gadget consider
