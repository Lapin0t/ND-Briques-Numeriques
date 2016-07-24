
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
