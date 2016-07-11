
l'OpenUI
<small>*les briques d'interface utilisateur*</small>
===

## L'objectif

> **Note:** voir [objectif 4.1](../../CDF.md)

Proposer aux développeur des composants génériques web
préconfigurer pour communiquer avec les données et favoriser
ainsi la l'accés centralisé des données

## Prposition

- L'élément ```<forum>``` doit offrir les fonctionnalité
 d'accés aux forum

- L'élément ```<vote>``` permetterais de visualiser et/ou
  enregistrer son vote que ce soit pour post de forum ou
  pour la délibaration d'une loi.

- L'élément ```<graph>```

```typescript
interface Element
{
    /*... la ce serais le code React / Polymer / ou autre ...*/
    createdCallback()
}
interface ElementAtome extends Element
{
    private atome: OpenApi.Atome;
    public serialize();
}
```

L'application :

```typescript
interface Application extends Element {}
interface Page        extends Element {}
```

```typescript
interface Article  extends ElementAtome {}
interface Ecrit    extends ElementAtome {}
interface Page     extends Element {}
interface Calque   extends Element {}
interface Acordeon extends Element {}
interface Colone   extends Element {}
interface Ligne    extends Element {}
interface Grille   extends Element {}
```

```typescript
interface Text        extends Element {}
interface Description extends ElementAtome {}  
interface Email       extends ElementAtome {}
interface Date        extends ElementAtome {}
interface Chiffre     extends ElementAtome {}
```

Les schemats UI prédefinit :

```
<Citoyen>
<Groupe>
<Messagerie>
<Debat>
<Vote>
```

## L'élément `<Forum>`

L'élément Forum doit offrir les fonctionnalité
d'accés aux forum

###### Les propriétés:

Nom       | Type | Description 
--------- | ---- | -----------------------------
fil       | UID  | Identifiant du fil de discution

###### Les fonctions:

Portée | Nom       | Description 
------ | --------- | ----------------------------
public | comment(eComment, eEcrit) | Envoie un commentaire. 

###### Les Evénements :

Portée | Nom       | Description 
------ | --------- | ----------------------------
public | onNewMessage | Fonction de rappel. Surviens lors d'un nouveau message


## L'élément `<Ecrit>`

L'élément écrit est le seul a avoir une représentation dans la base de données. \
Mais pourquoi !?

1. Car c'est a l'utilisateur ou organisation de décider de la présentation
souhaitez. Chacun doit être libre de mettre en avant ou non un artice sur
ca page personnel.
2. Les page de présentation doivent pouvoir évolué celons le contexte
et contrainte du moment.
3. En revanche les serveur ne fournissant que des données et
pour des raison de sécurité aucune intégration de script ne doit être fait
4. De même l'attention est porté uniquement sur la disposition et non sur le
style.


```ts
interface Ecrit extends ElementAtome {
    protected md: string;
}
interface EcritConvertisseur <FormatSortie> {
    public convertir(data): FormatSortie;
}
```

### Le formatage

#### Contraintes :
Le formatage de ces données a pour obligation d'être légé. rapidement serialisable et convertissable

#### Proposition :

Le format MD semble bien adapté pour la description d'articles mais il deviens limiter dans certain cas.
Pour plus de détail voir la poposition: [formatage de l'élément Ecrit](OpenUI-Ecrit.md)
