Le composant Message
===

> voir [Proposition graphique](../../UX/discussion-débats-mobile)

## Objectifs

- envoyer un message
- répondre à un message
- supprimer un message de son affichage (n’impacte pas les autres)
- catégoriser les messages
- indiquer si on est d'accord avec un message
- indiquer si on est ne pas d'accord avec un message (impose un message réponse pour les débats)

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
