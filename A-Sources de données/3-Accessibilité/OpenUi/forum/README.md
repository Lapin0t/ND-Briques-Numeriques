
L'élément \<forum\>
===

La class abstraite `<forum>` doit permettre aux développeur d'UX d'accéder aux actions suivantes !

- Envoyer un message
- Répondre à un message
- Supprimer un message de son affichage. (N’impacte pas les autres)
- Catégorise les messages
- Indiquer être d'accord avec un message
- Indique ne pas être d'accord avec un message (impose un message réponse)

```c++
interface Forum extends HTMLDivElement
{
    public sendMessage(fil, message, parent) {}
    public IamOk(fil, message, reponse = null) {}
    public IamNotOk(fil, message, reponse) {}
}
```

![Affichage d'un message par défaut](UX-Message-Actions-Menu.png)

![Supprimer un message](UX-Message-Actions-Menu-Details.png)

![Supprimer un message](UX-Message-Actions-Swipe-Kill.png)

![Supprimer un message](UX-Message-Actions-Swipe-Send.png)
