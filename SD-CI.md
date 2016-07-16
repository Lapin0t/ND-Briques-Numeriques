
Serveur === Données <-> Client === Interfaces
===

> Ceci est une proposition personnelle qui demande à être construit (ou non) collectivement

## Philosophie

Ne plus compter sur des serveurs de pages dynamiques. Ne même plus imaginer des serveurs de pages.

La volonté globale du développement aboutira très probablement sur un réseaux mesh.

Par conséquent, admettre que les "serveurs" fournissent uniquement des données, et les "clients" s’occupent de créer l'UI.
  
## Avantages

- Il est facile pour un téléphone portable de devenir un serveur puisqu'il n’a pas à lancer du code php, java ou autre pour fournir des pages dynamiques.

- Celons son appareil et sa connexion, le client installeras l’affichage qui lui convient. L’utilisateur d’une Raspberry avec une faible connexion ne souhaitera probablement pas une page chargent de lourds image, styles et script. Alors que sur un pc branché avec fibre cela peut être l’inverse.

- Permettre à chacun d’utiliser les données pour créer des UX adapté les besoins divers des utilisateurs.

## Désavantages

-	Communecter est construit sur un Framework MVC pas vraiment dans cette idée…

## Contrainte

(si aprouvé)

-	Définir le(s) Framework(s) coté client (React-Redux/Angular/Ember/etc…) pour que les travaux de chacuns puisse sur être homogène !
