NuitDebout, la brique numérique
===

## Origine

Historiquement ce projet est né des réflexions de la commission « NuitDebout
Demain ». Cette commission est constituer essentiellement d’actifs de d’autre
commissions et a pour but d’anticiper et favoriser l’avenir du mouvement.

Nous nous sommes vite rendu compte que nous ne souhaitions devenir une énième
association ou collectif. Il a été aussi constater qu’il y a énormément
d’initiatives partout en France et ce depuis des années. Mais que toutes, nuit
debout compris, souffrais d’un manque de visibilité et d’interconnexions
extérieurs comme internes.

Ce projet a donc été initié pour résoudre cette problématique, puis un
hackathon a été réaliser afin d’identifié les problèmes et en extraire des
besoins essentiels.  Pour vous donner une vision large, nous pouvons imaginé
que le besoin est de faire converger et interconnecter toutes les initiatives
de cet [annuaire](http://4emesinge.com/geographie-des-alternatives).

> Consultez en priorité [synthèse des souhaits
> utilisateurs](https://github.com/corbane/ND-Briques-Numeriques/wiki) pour
> plus de détails

## Philosophie

- Cette architecture est le morcellement en briques fonctionnelles de la
  synthèse des souhaits utilisateurs. Elle a pour buts :
  - que chacun puissent contribuer au développement de l’application
  - que chacun est une  vision globale de son travail et de ceux des autres

> :exclamation: faire une charte global et pour l’édition de ce doc et balancer
> ce qui suit dedans
- Des API === Donne-moi des Lego et je fabriquerais.
- Se contraindre à une architecture (Serveur === Données <-> Client ===
  Interfaces). Pourquoi : voir [SD-CI](SD-CI.md).
- Logiciel libre & open source.

## Architecture

Passons maintenant dans le vif du sujet :yum:.

### Structure réseau

- L'[OpenNet](A-Structure%20r%C3%A9seau/1-OpenNet) as pour but de définir les
  modèles et protocoles utiliser pour la plateforme.

- L'[OpenBox](A-Structure%20r%C3%A9seau/2-OpenBox) est une couche matérielle
  ayant but d’aider et favoriser l’accès à la communication internet.

### Les données

- L'[OpenSchema](B-Les%20donn%C3%A9es/1-OpenSchema)
  définit l’ontologie des données et leurs schémas.

- L'[OpenDb](B-Les%20donn%C3%A9es/2-OpenDb)
  définit les serveurs physiques utilisable pour la plateforme.

- L'[OpenQuery](B-Les%20donn%C3%A9es/3-OpenQuery)
  définit les protocoles et fonctions d’accès aux données.

### Processus décisionnels

- L'[OpenDemocraticProcess](C-Processus%20d%C3%A9cisionnels/1-OpenDemocraticProcess)
  Définit les outils pour que chaque collectif, organisation ou groupe puissent
  mettre en actions leur système décisionnel (ou choisir parmi un panel de
  solutions module)

### L'interface utilisateurs

- L'[OpenUi](D-L'interface%20utilisateurs/1-OpenUi) Regroupe des librairies
  d'éléments, widgets et composants réutilisables pour créer les UX.

- L'[UX](D-L'interface%20utilisateurs/2-UX) Bon là je n’ai sûrement pas besoin
  d’expliquer l’utilité d’une UX bien faite... :)


---

> :question: L’OpenFunding pour les Moyens financiers, j’avoue ne pas savoir ou
> le mettre. Est-ce des données, un processus décisionnels, une structure
> réseau, ou un peu des trois. Mais il faut pouvoir que des groupes ad-hoc
> puisse travailler dessus le plus indépendamment...
