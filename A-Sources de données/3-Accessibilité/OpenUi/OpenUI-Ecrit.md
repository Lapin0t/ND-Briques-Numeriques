
Proposition pour le formatage des données de l'élément `<Ecrit>`
===

> :grey_exclamation: Ce document est une base de réflexions, il n’a pas pour but d’imposé quoique ce ça mais d’illustrer la proposition.

## Contraintes :

Le formatage de ces données a pour obligation d'être légé. rapidement serialisable et convertissable

## Propostions:

Le format MD semble bien adapté pour la description
d'articles mais il deviens limiter dans certain cas.

###### améliorations :

- Supprimer les balises HTML eg `<div style="...">`.

- Ajouter la possibilité de disposition par FlexBox. par exemple:

- Les alignement de texte a améliorer eg. left, center, right

- Permettre de gérer les marge

- Simplifier les tablea

- Permettre des composants plus évoluer  \
  eg. Accordéon, Tabs, Gallery, Map Graph, ...

## Le formatage des données

> Le formatage propsé ci dessous n'as pas pour ocation à être utiliser par
> les utilisateurs mais pour but de réduire au minimum la taille des données; \
> Les fichier MD sont cool mais devienne limiter dans certain cas

### Supprimer les possibilités d'intégration HTML eg `<div style="...">`.

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