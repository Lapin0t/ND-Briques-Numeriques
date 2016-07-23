
Le composant Message
===

> voir [Proposition graphique](../../UX/discussion-débats-mobile)

## Objectifs

- Envoyer un message
- Répondre à un message
- Supprimer un message de son affichage. (N’impacte pas les autres)
- Catégorise les messages
- Indiquer être d'accord avec un message
- Indique ne pas être d'accord avec un message (impose un message réponse pour les débats)

## Proposition

```typescript
interface Discussion extends HTMLDivElement
{
    public sendMessage(message, parent)
    public deleteMessage(msg)
    public tagMessage(msg, tag)
    public ImOk(message, reponse)
    public ImNotOk(message, reponse)
}
```

### Aides

- Une lib ayant le composant swipe tout fait [framework7 Swipeout](http://framework7.io/docs/swipeout.html)
- Une lib plus légère [snabbt.js](http://daniel-lundin.github.io/snabbt.js/#transform-origin-example)
