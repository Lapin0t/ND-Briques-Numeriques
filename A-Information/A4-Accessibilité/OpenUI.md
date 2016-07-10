
l'OpenUI
<small>*les briques d'interface utilisateur*</small>
===

Voivi la liste des briques misent à disposition des utilisateurs:
Je m'inspire de l'interface de JavaFx

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
<Forum>
<Messagerie>
<Debat>
<Vote>
```

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

> Contraintes : \
> Le formatage de ces données a pour obligation d'être légé.
> rapidement serialisable et convertissable
>
> D'un poit de vu thecnique : \
> Le format MD semble bien adapté mais il deviens limiter dans certain cas.

Voici des idées de propostions d'améliorations :

- Supprimer les balises HTML eg `<div style="...">`.

- Ajouter la possibilité de disposition par FlexBox. par exemple:

- Les alignement de texte a améliorer eg. left, center, right

- Permettre de gérer les marge

- Simplifier les tablea

- Permettre des composants plus évoluer  \
  eg. Accordéon, Tabs, Gallery, Map Graph, ...

Pour plus de détail voir : [poposition de formatage de l'élément Ecrit](OpenUI-Ecrit.md)
