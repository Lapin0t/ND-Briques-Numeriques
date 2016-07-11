
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
```

---

## L'élément `<nd-discussion>`

L'élément Forum doit offrir les fonctionnalité
d'accés aux forum

###### Les attributs:
```ts
public get uid: UID // Identifiant du fil de discussion
```

###### Les fonctions:
```ts
public commenter(Commentaire, Ecrit) // Envoie un commentaire. 
```

###### Les Evénements :
```ts
public quandCommentaire(Commentaire) //Fonction de rappel. Surviens lors d'un nouveau message
```

---

## L'élément `<nd-vote>`

L'élément permetterais de visualiser et/ou
enregistrer son vote que ce soit pour post de forum ou
pour la délibaration d'une loi. 

###### Les propriétés:
```ts
public get statistiques // Retourne les statistique de vote
```

###### Les fonctions:
```ts
public voter(avis) // Envoie son vote. 
```

###### Les Evénements :
```ts
public quandChangementStatistique(statistique) //Fonction de rappel. Surviens lors d'un changement de statistique
```

---

## L'élément `<nd-ecrit>`

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

> Voir la poposition: [formatage de l'élément Ecrit](OpenUI-Ecrit.md)

---

## Liens entre APIs

Cette API est une retranscription de objets de l'openData.
Elle est donc absolument pas intéropérable.

De même elle est extrêment lié au protocole de communication.

Ces forte contrainte justifit ça présence. Elle permet, aux yeux
des dévellopeur UX de paraitre interopérable...

---

## Outils

- React.js
- Polymer
- WebComponent
- Knockout.js

---

## A faire

- [x] Definir les liens avec les autres API
- [ ] Créer des sénarios d'utilisation
- [ ] Implémentation React.js
- [ ] Implémentation Angular.js
- [ ] ~~Implementation .Net WPF~~

---