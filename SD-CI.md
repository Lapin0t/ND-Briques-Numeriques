Serveur === Données <-> Client === Interfaces
===

> Cette architecture est un concept global, peu applicable dans l’immédiat mais
> qui a pour but de nous contraindre à programmer en modules et nous obliger à
> dissocier les couches de présentation et d'application.

## Philosophie

Ne plus compter sur des serveurs de pages dynamiques. Ne même plus imaginer des
serveurs de pages.  La volonté globale du développement aboutira très
probablement à un réseau mesh/p2p.  Par conséquent, admettre que les "serveurs"
fournissent uniquement des données et les "clients" s’occupent de créer l'UI.

## Avantages

- Il sera plus facile pour un téléphone portable de devenir un noeud sur un
  réseaux mesh puisqu'il n’a pas à lancer du code php, java ou autre pour
  fournir des pages dynamiques mais uniquement des données (eg. Bittorrent).

- Selon son appareil et sa connexion, le client installera l’affichage qui
  lui convient. L’utilisateur d’une Raspberry avec une faible connexion ne
  souhaitera probablement pas une page chargeant de lourdes image, styles et
  scripts, alors que sur un pc branché avec fibre cela peut être l’inverse.

- Le développement UX seras plus simple pour une plateforme donnée car
  l’application pour l’affichage (meteor, nodeWebkit, electron, etc) sera
  connue et il n’y aura pas besoin de se soucier de la compatibilité avec la
  multitude de plateforme existante (ie9, opera, mobile).

- Permettre à chacun d’utiliser les données pour créer des UX adaptées aux
  besoins divers des utilisateurs.

## Désavantages

- Il n’est pas certain que ce soit une grosse contrainte mais il sera donc
  obligatoire pour l’utilisateur de télécharger et installer une application
  native.

- Impose une application native par type de débit-internet/puissance-machine
  (des solutions comme Meteor, nodeWebkit, electron, cordova/phoneGap peuvent
  alléger cette contrainte)

- Communecter est construit sur un Framework MVC pas vraiment dans cette idée
  (mais suffisamment modulable pour être adapté).

## Road map

- Définir le(s) Framework(s) coté client (React-Redux/Angular/Ember/etc) pour
  que les travaux de chacuns puissent sur être homogènes !
