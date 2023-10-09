# Frontend-Aufgaben

Das Frontend befindet sich im `/client`-Ordner.

## Vorbereitung

Bevor wir unseren Code schreiben, sollten wir unsere Abhängigkeiten installieren.

Gib im Terminal vom `root` (/) des Projekts aus folgendes ein:

    - `cd client`
    - `npm i`

Um das Frontend jederzeit auszuführen, kannst du den folgenden Befehl verwenden:

    - `npm start`

## Aufgabe 1 - Lies den Code in deiner Frontend-Anwendung

Nimm dir etwas Zeit, um dich mit dem Frontend-Code im `/client`-Ordner vertraut zu machen.

- `App.js` - ist die Wurzel unserer Anwendung
- `/components` - enthält alle Komponenten für unsere Anwendung
- `/components/List` - enthält die Dateien für die `List`-Komponente
- `/components/List/index.js` - die Wurzel der `List`-Komponente
- `/components/List/ListItem.js` - eine Unterkomponente der `List`-Komponente

> Du wirst auch CSS-Dateien mit dem Namen `module` bemerken, zum Beispiel `App.module.css`
>
> Das sind CSS-Module. Der Inhalt kann beim Importieren als Objekt behandelt werden.
>
> Du kannst mehr über CSS-Module [hier](https://create-react-app.dev/docs/adding-a-css-modules-stylesheet/) lesen.

Verwende die folgenden Fragen, um deine Analyse zu strukturieren:

1. Wird irgendwo ein State verwendet?
2. Was macht die `map()`-Funktion in der `List`-Komponente?
3. Wie werden Styles verwendet?
4. Werden `props` an irgendeine Komponente weitergegeben?

## Aufgabe 2 - Aufräumen und Personalisieren von App.js

Jetzt, wo du den Code hast, verbringe etwas Zeit damit, ihn zu personalisieren.

1. Ändere den Text in `App.js`

2. Ändere die Styles in `App.module.css` nach deinen Vorlieben

3. Entferne das nervige GIF auf der Startseite 😛

## Aufgabe 3 - Aufräumen und Personalisieren von App.js

1. Ändere den Text in der `List`-Komponente (einschließlich ihrer Unterkomponente)

2. Ändere die Darstellung der Schaltflächen nach deinen Vorlieben

## Aufgabe 4 - Verwenden von fetch in der List-Komponente

Öffne die Dateien im `/components/List`-Ordner

1. Ändere die Hauptdatei in der `List`-Komponente (`index.js`), sodass sie den Endpunkt auf deinem Server aufruft

2. Das Ergebnis des Fetch sollte verwendet werden, um deinen lokalen State zu setzen, der bereits für dich vorbereitet wurde (siehe `list` und `setList` in `index.js`)

    > Verwende `fetch` oder `axios`, um die Anfrage an das Backend zu stellen

Du wirst noch nichts auf deiner Seite sehen können, aber du kannst `console.log()` oder den Netzwerk-Tab in deinem Browser verwenden, um zu überprüfen, ob Daten vom Server zurückgegeben werden.

## Aufgabe 5 - Anzeigen von Daten in der ListItem-Unterkomponente

Die Hauptlistenkomponente gibt bereits alle `props` von der Serveranfrage an die `ListItem.js`-Unterkomponente weiter.

1. Extrahiere die Eigenschaften, die du anzeigen möchtest, aus dem `props`-Objekt und zeige sie mit dem JSX in der Komponente an

2. Du solltest jetzt einige Ergebnisse auf der Website sehen können

## Aufgabe 6 - Styling mit CSS-Modulen

Die Seite sieht etwas hässlich aus, also gib ihr ein Makeover!

Jetzt, wo du einige Daten hast, kannst du mehr Zeit mit dem Styling verbringen

1. Verwende die CSS-Module, um die `List`-Komponente zu stylen

## Aufgabe 7 - Verhalten zu unseren Schaltflächen hinzufügen

Unsere Schaltflächen tun nichts, wenn wir sie anklicken, also ändern wir das

1. Füge der `onClick`-Prop für jede Schaltfläche hinzu und schreibe für jede einen separaten Handler

2. Verwende vorerst nur `console.log()`, um sicherzustellen, dass deine Handler-Funktionen aufgerufen werden, wenn du auf jede Schaltfläche klickst

## Aufgabe 8 - Weitere States hinzufügen, um den `skip`-Wert zu verarbeiten

Bisher sind die Daten auf unserer Seite etwas statisch. Wir möchten in der Lage sein, einen dynamischen "skip"-Wert an das Backend zu senden, um einen neuen Satz von Ergebnissen zu erhalten.

1. Füge der Wurzel deiner `List`-Komponente ein neues State-Objekt mit dem `useState` React-Hook hinzu. Dies speichert den "skip"-Wert. Initialisiere diesen State mit dem Wert `0`.

2. Ändere in der Handler-Funktion für die "previous"-Schaltfläche den State für den "skip"-Wert, sodass, wenn der Benutzer auf "previous" klickt, der "skip"-Wert um eine angemessene Anzahl zurückgeht (verwende den "limit"-Wert, den du in deiner Datenbank festgelegt hast)

3. Ändere in der Handler-Funktion für die "next"-Schaltfläche den State für den "skip"-Wert, sodass, wenn der Benutzer auf "next" klickt, der "skip"-Wert um eine angemessene Anzahl vorwärts geht (verwende den "limit"-Wert, den du in deiner Datenbank festgelegt hast)

4. Teste, ob dein Code funktioniert, indem du `console.log()` verwendest, um den aktualisierten Wert anzuzeigen

## Aufgabe 9 - Eine neue Anfrage stellen

1. Jetzt, wo deine Handler-Funktionen den "skip"-State ändern, füge deinen Schaltflächen-Handlern eine neue Fetch-Anfrage hinzu, um Daten vom Backend anzufordern - genau wie bei der `useEffect`-Funktion.

2. Stelle sicher, dass der State für "list" mit den Ergebnissen der `fetch`-Anfrage aktualisiert wird

## Aufgabe 10 - "previous"-Schaltfläche automatisch ausblenden

1. Wenn der "skip"-Wert deines States `0` ist, verwende eine JSX-Bedingung, um die "previous"-Schaltfläche auszublenden.
