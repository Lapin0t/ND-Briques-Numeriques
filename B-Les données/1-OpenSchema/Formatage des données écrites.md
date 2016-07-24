
Formatage des données écrites _(Proposition)_
===

> ### :grey_exclamation: Ce document est encore un brouillons c’est donc une base de réflexion.

## Description

Le format MD semble bien adapté pour l’écriture de documents, légè et facilement serialisable/convertissable mais il devient limité dans certain cas. Les données de type articles, documents, manuels aurons besoin d’un minimum de représentations.

## améliorations

> Le format proposé ci-dessous n'as pas pour vocation à être utilisés par les utilisateurs mais pour but de réduire au minimum la taille des données, le standardiser et interopérable entre les applications.

### Ajouter la possibilité de disposition par FlexBox.

Syntaxe :
```
<>
Ceci est un block
<->
et celui ci est sur une autre colone
<>
```

### Les alignement de texte a améliorer eg. left, center, right

Syntaxe :
```
~g Contenu positioné à gauche
~d Contenu positioné a droite
~c Contenu positioné au centré
```

### Permettre de gérer les marge

Syntaxe :
```
~ Une tabulation
~~ Deux tabulations
~~~ etc ...
```

### Simplifier les tableau

Syntaxe :
```
[[
    : En tête de colone
    : En tête de colone
][
    : valeur
    : valeur
    --
    : valeur
    : valeur
]]
```

### Permettre des composants plus évoluer

> eg. Accordéon, Tabs, Gallery, Map Graph, ...
  
#### Accordéon:

Syntaxe :
```
([
: En tête
][
: Contenu 1
])
```

#### Tabs:

Syntaxe :
```
<[
: En tête
][
: Contenu 1
]>
```

#### Gallery:

Syntaxe :
```
{
: Contenu 1
: Contenu 2 
}
```

### Supprimer les possibilités d'intégration HTML eg `<div style="...">`.

Car utiliser pour des composants spécifiques.

#### Graph:

Syntaxe :
```
<G-Bare json>
<G-Cercle json-data>
```

#### Map:

Syntaxe :
```
<Map json-data>
```

---
