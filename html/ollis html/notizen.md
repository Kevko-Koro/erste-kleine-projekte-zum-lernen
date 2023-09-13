# JavaScript-Code-Zusammenfassung

In diesem Dokument wird ein JavaScript-Code erklärt, der einen Twitch-Player in eine Webseite einbettet und bestimmte Aktionen ausführt, wenn das Video abgespielt wird.

## JavaScript-Code

```javascript
// Variable zur Darstellung des Twitch-Players
var twitch_embed = new Twitch.Embed("twitch-embed", {
    width: "100%",
    height: "100%",
    channel: "v31kko",
    autoplay: true,
    parent: ["www.twitch.tv"]
});

// Event-Listener für das VIDEO_PLAY-Event
twitch_embed.addEventListener(Twitch.Embed.VIDEO_PLAY, () => {
    console.log("Video is Play!!");
    
    // Ausblenden des Platzhalters
    var twitch_placeholder = document.getElementById('twitch_placeholder');
    twitch_placeholder.style.display = 'none';

    // Anzeigen des Twitch-Players
    var twitch_embed = document.getElementById('twitch-embed');
    twitch_embed.style.display = 'block';
});

## Variablen-Deklarationen

- `var twitch_embed`: Hier wird eine Variable namens `twitch_embed` deklariert, die den Twitch-Player repräsentiert. Diese Variable wird verwendet, um auf den Player zuzugreifen und seine Eigenschaften zu steuern.

## Twitch-Player-Einbettung

- `var twitch_embed = new Twitch.Embed("twitch-embed", { ... })`: In diesem Abschnitt wird der Twitch-Player erstellt und in der zuvor deklarierten `twitch_embed`-Variable gespeichert. Dieser Player wird im HTML-Div-Element mit der ID "twitch-embed" eingebettet. Die Einstellungen für den Player, wie Breite, Höhe, Kanal und Autoplay, werden ebenfalls hier festgelegt.

## Event-Listener

- `twitch_embed.addEventListener(Twitch.Embed.VIDEO_PLAY, () => { ... })`: Hier wird ein Event-Listener hinzugefügt, der auf das `VIDEO_PLAY`-Event des Twitch-Players reagiert. Wenn das Video abgespielt wird, wird die in der Pfeilfunktion definierte Aktion ausgeführt.

## Konsolenausgabe

- `console.log("Video is Play!!");`: Innerhalb des Event-Listeners wird diese Zeile verwendet, um eine Nachricht "Video is Play!!" in der JavaScript-Konsole auszugeben. Dies ist hilfreich für die Fehlerbehebung und das Debugging, um zu überprüfen, ob das Video abgespielt wurde.

## Anzeigeelemente steuern

- `var twitch_placeholder = document.getElementById('twitch_placeholder');`: Hier wird ein Element mit der ID "twitch_placeholder" aus dem HTML-Dokument ausgewählt und in der `twitch_placeholder`-Variable gespeichert.
- `twitch_placeholder.style.display = 'none';`: Mit dieser Zeile wird das ausgewählte Element (der Platzhalter) ausgeblendet, indem sein `display`-CSS-Eigenschaftswert auf 'none' gesetzt wird. Dies geschieht, wenn das Video abgespielt wird.
- `var twitch_embed = document.getElementById('twitch-embed');`: Hier wird das Twitch-Player-Element aus dem HTML-Dokument ausgewählt und in einer neuen `twitch_embed`-Variable gespeichert.
- `twitch_embed.style.display = 'block';`: Mit dieser Zeile wird das Twitch-Player-Element angezeigt, indem sein `display`-CSS-Eigenschaftswert auf 'block' gesetzt wird. Dies geschieht ebenfalls, wenn das Video abgespielt wird.

Zusammenfassend ermöglicht dieser JavaScript-Code das Einbetten eines Twitch-Players auf deiner Website und steuert, wie das Player-Element angezeigt oder ausgeblendet wird, wenn das Video abgespielt wird. Die Konsole wird auch verwendet, um eine Nachricht auszugeben, wenn das Video gestartet wird, was hilfreich sein kann, um den Ablauf des Codes zu überwachen und zu überprüfen.