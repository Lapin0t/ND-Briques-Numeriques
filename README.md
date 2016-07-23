# ND-Briques-Numeriques

## Pré-requis

Voici les liens des travaux effectués servant de base de réflexions à ce cahier des charges :

- Articles explicatif
  [la Gazette Debout](http://gazettedebout.fr/2016/07/08/hackathondebout-geeks-de-nuit-debout-preparent-lavenir-mouvement/)

- Le hackathon E-Democratie \
  [Carte mentale générale](https://www.mindmeister.com/724254875/hackathondebout-e-democratie) \
  [Synthése de la carte mentale générale](https://www.mindmeister.com/721715693/hackathondebout-vue-d-ensemble) \
  [Les projets complémentaire](https://www.mindmeister.com/724295990/hackathondebout-projets-compl-mentaires)

- NuitDebout par [communecter.org](https://docs.google.com/document/d/1wZnQ6_0ak9YkXiglp1r5GNjxtrf6W6NP43wq2gvrkKg/mobilebasic)

## Philosophie

Donne-moi des briques et je construirais

Logiciel libre & open sources

[S’il vous plait adhérer à cette rigueur.](CRITIQUE.md)

---
## Objectifs

3 grand thèmes fonctionnel sont ressortis du hackathon :

-	[Les sources de données](A-Sources de données)
-	[Le capital social](B-Capital sociétale)
-	[Le processus décisionnel](C-Processus décisionnels)

## Contraintes

- Il n'héxiste pas Une solution !  <br/>
  Mme Michou, le petit gaetan ou Marc l'ingé-son ne souhaite la même interface
  (**simple**, **personisable**)

- Pour le 31 aout il nous faut lier les actifs entre eux et motiver l'envie de devenir actif.

Propositions
===

### B. Proposition sectorisé en briques

### Philosophie globale :

- Ne plus compter sur des serveurs de pages dynamiques. Ne même plus imaginer des serveurs de pages. Mais admettre que les "serveurs" fournissent uniquement des données, et les "clients" s’occupent de créer UI. Pourquoi ? voir [SD-CI](SD-CI.md)

### Structure réseau

- L'[OpenNet](https://github.com/corbane/ND-Briques-Numeriques-api/tree/master/A-Structure%20r%C3%A9seau/1-OpenNet)
  as pour but de définir les modéles et protocoles utiliser pour la plateforme.

- L'[OpenBox](https://github.com/corbane/ND-Briques-Numeriques-api/tree/master/A-Structure%20r%C3%A9seau/2-OpenBox)
  est une couche matérielle de l’OSI ayant but d’aider et favoriser l’accès à la communication internet

### Les données

- L'[OpenSchema](https://github.com/corbane/ND-Briques-Numeriques-api/tree/master/B-Les%20donn%C3%A9es/1-OpenSchema)
  définit l’ontologie des données et leurs schémas

- L'[OpenDb](https://github.com/corbane/ND-Briques-Numeriques-api/tree/master/B-Les%20donn%C3%A9es/2-OpenDb)
  définis les serveurs physiques utilisable pour la plateforme
  
- L'[OpenQuery](https://github.com/corbane/ND-Briques-Numeriques-api/tree/master/B-Les%20donn%C3%A9es/3-OpenQuery)
  définit les protocoles et fonctions d’accès aux données

### Processus décisionnels

- L'[OpenDemocraticProcess](https://github.com/corbane/ND-Briques-Numeriques-api/tree/master/C-Processus%20d%C3%A9cisionnels/1-OpenDemocraticProcess)
  Définit les outils pour que chaque collectifs, organisation, groupes, …, puissent mettre en actions leur système décisionnel. (ou choisir parmi un panel de solutions module)

### L'interface utilisateurs

- L'[OpenUi](https://github.com/corbane/ND-Briques-Numeriques-api/tree/master/D-L'interface%20utilisateurs/1-OpenUi)
  Regroupe des librairies d'éléments, widgets, composant, etc, réutilisables pour créer les UX.

- L'[UX](https://github.com/corbane/ND-Briques-Numeriques-api/tree/master/D-L'interface%20utilisateurs/2-UX)
  Bon là je n’ai surement pas besoin d’expliquer l’utilité d’une UX bien faite… :)


