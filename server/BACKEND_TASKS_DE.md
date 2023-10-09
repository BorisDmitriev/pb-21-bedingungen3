# Backend-Aufgaben

Das Backend befindet sich im `/server`-Ordner.

Du findest Code-Schnipsel [hier](./SNIPPETS_DE.md).

## Vorbereitung

Bevor wir unseren Code schreiben, sollten wir unsere Abhängigkeiten installieren.

Vom `root` (/) des Projekts, gib im Terminal Folgendes ein:

   - `cd server`
   - `npm i`

Dies wird automatisch die folgenden Pakete installieren:
   - express
   - mongoose
   - dotenv

Um das Backend jederzeit auszuführen, kannst du den folgenden Befehl verwenden:

   - `node server.js`

##### Wenn du nodemon installiert hast

   - `nodemon server.js`

## Aufgabe 1 - Auswahl eines Datensatzes

Für diese Aufgabe kannst du aus den von MongoDB Atlas bereitgestellten Beispiel-Datensätzen wählen. Wähle einen aus und notiere ihn. Wir werden dies im Verlauf dieser Aufgabe als deinen **gewählten Datensatz** bezeichnen. "Sammlung" = engl. "collection"

Wir empfehlen einen der folgenden:

- Datenbankname: `sample_geospatial`, Sammlung: `shipwrecks`
- Datenbankname: `sample_restaurants`, Sammlung: `restaurants`
- Datenbankname: `sample_mflix`, Sammlung: `movies`
- Datenbankname: `sample_training`, Sammlung: `inspections`

> Wichtig! Diese Aufgabe setzt voraus, dass du bereits die Beispieldaten in deinem Konto geladen hast. Wenn du dies noch nicht getan hast, befolge die Anweisungen zum [Laden der Beispieldaten](./LOADING_SAMPLE_DATA_DE.md).

## Aufgabe 2 - Schreibe eine .env-Datei

> Hinweis: Für diese Aufgabe gehen wir bereits davon aus, dass du einen MongoDB-Server hast und weißt, wie du auf deine Anmeldeinformationen zugreifen kannst.

1. Erstelle eine Datei in deinem Stammverzeichnis mit dem Namen `.env`. Diese Datei enthält alle Verbindungsinformationen für den Zugriff auf deine Datenbank.

2. Kopiere den Text aus der Datei `.env.example` in deine `.env`-Datei.

3. Für den Schlüssel `DB_NAME` beziehe dich auf den **Datenbanknamen** deines **gewählten Datensatzes**.

4. Fülle für die anderen Schlüssel die Details aus, die dir von deinem MongoDB-Dienst zur Verfügung gestellt wurden.
    - DB_HOST=
    - DB_USER=
    - DB_PASS=

## Aufgabe 3 - Erstellung deines Schemas

Analysiere die Daten in der **Sammlung** deines **gewählten Datensatzes**.

Frage dich, welche Felder verwendet werden, welche Datentypen verwendet werden?

1. Im `/models`-Ordner erstelle eine Datei mit dem Namen der **Sammlung** deines **gewählten Datensatzes**.

   > Tipp: Da diese Datei letztendlich das Modell enthalten wird, verwende einen großgeschriebenen Namen, zum Beispiel `Shipwreck`.

2. Schreibe in dieser Datei ein Schema basierend auf deinen Erkenntnissen.

   > Tipp: Du musst nicht ALLE Feldnamen einbeziehen! Zum Beispiel kannst du die komplizierteren oder langweiligeren weglassen.

## Aufgabe 4 - Erstellung des Modells

1. Erstelle ein Modell aus deinem Schema.

   > Tipp: Die `mongoose.model()`-Methode nimmt 4 Parameter, aber uns interessieren eigentlich nur die ersten 3:
   >  1. Der Name des Modells
   >  2. Eine Referenz auf das Schema
   >  3. (optional) der Name der Sammlung

2. Da deine Sammlung bereits existiert, verwende den 3. Parameter, um direkt auf den Namen der **Sammlung** deines **gewählten Datensatzes** zu verweisen. Auf diese Weise wirst du sicher sein, dass das Modell auf die bereits in deinem Datensatz gespeicherten Daten reagiert.

   > Beispiel: Wenn deine Sammlung **'shipwrecks'** heißt, verwende **'shipwrecks'** als 3. Parameter.

3. Exportiere dein Modell mit dem Node-Modul-Standard.

## Aufgabe 5 - Erstelle deine Route

1. Im `/routes`-Ordner erstelle eine Datei, die den Namen deiner Route haben wird. Wähle den Namen, den du für angemessen hältst.

   > Tipp: Vergiss nicht, `express` zu importieren!
   
   > Tipp: Vergiss nicht, `express.Router()` zu verwenden, um dein `router`-Objekt zu erstellen!

2. Importiere und verwende die Route, die du gerade erstellt hast, in `server.js`.

   > Tipp: Du benötigst `app.use()`.

## Aufgabe 6 - Schreibe einen Endpunkt, um alle Daten in unserer Sammlung aufzulisten

Wir erstellen einen Endpunkt, um alle Daten aus der **Sammlung** unseres **gewählten Datensatzes** aufzulisten.

1. Importiere in der Route, die du in der vorherigen Aufgabe erstellt hast, das Modell, das du in Aufgabe 4 erstellt hast.

2. Erstelle einen Endpunkt mit der Methode `GET`. Gib dem Endpunkt einen passenden Pfad (oder keinen, wenn du möchtest).

3. Verwende im Handler für diesen Endpunkt das erstellte Modell, um die Sammlung abzufragen, mit der das Modell verknüpft ist. Du möchtest alle Ergebnisse zurückgeben.

   > Tipp: Denke daran, `find()` ohne Parameter zu verwenden, um ALLES zurückzugeben.
   
   > Tipp: Denke daran, dass diese Modellmethoden Promises zurückgeben. Behandle das Promise also mit den `then()`-Methoden oder verwende das bevorzugte `async / await`.

4. Sende deine Ergebnisse mit `response.send()` zurück an den Client.

5. Füge Fehlerbehandler mit `try / catch` oder `catch()` hinzu, um mögliche Fehler zu behandeln. Sende einen anderen Antwortcode und eine Nachricht an den Client, wenn ein Fehler auftritt.

## Aufgabe 7 - Sortieren unserer Ergebnisse

Möglicherweise möchtest du die Ergebnisse nach einem bestimmten Feld sortieren.

1. Verwende die `sort({ field : criteria})`-Methode, um die von deiner Abfrage zurückgegebenen Ergebnisse zu sortieren, wobei `field` das Feld ist, nach dem du sortieren möchtest, und `criteria` `"asc"`, `"desc"`, `"ascending"`, `"descending"`, `1` oder `-1` ist.

## Aufgabe 8 - Begrenzung unserer Ergebnisse

Achtung! Deine Sammlung hat Tausende von Ergebnissen! Du solltest nicht alles zurückgeben, was der Server findet.

1. Verwende die `limit(n)`-Methode, um die von deiner Abfrage zurückgegebenen Ergebnisse zu begrenzen, wobei `n` die Anzahl der zurückzugebenden Ergebnisse ist.

2. Welche Zahl wirst du verwenden?

## Aufgabe 9 - Überspringen von Indizes aus unseren Ergebnissen

Die Möglichkeit, Indizes zu überspringen, ist für jede Anwendung, die Paginierung verwendet, von entscheidender Bedeutung.

1. Füge deinem Endpunkt einen Parameter oder Abfrageparameter hinzu. Dieser Parameter ist der Wert, der angibt, wie viele Indizes unsere Abfrage überspringen soll, bevor die zurückgegebenen Ergebnisse gezählt werden.

   > Tipp: Denke daran, dass du `request.params` oder `request.query` verwenden kannst, um auf diesen Wert zuzugreifen.

2. Verwende die `skip(n)`-Methode, um unserer Abfrage mitzuteilen, dass eine bestimmte Anzahl von Datensätzen übersprungen werden soll, wobei `n` die Anzahl der zu überspringenden Ergebnisse ist.

> Wichtig! `skip()` erwartet eine Zahl, aber jede Eigenschaft in `request.params` ist ein String. Du solltest diese Zahl in einen String konvertieren, bevor du sie in `skip()` verwenden kannst.

## Aufgabe 10 - Auswahl bestimmter Felder

Immer noch zu viele Daten!

1. Wähle einige Felder aus, die du zurückgeben möchtest, und verwende die `select()`-Methode, um deine Ergebnisse auf diese Felder zu beschränken. Zum Beispiel:
   `select('date')` wird deine Ergebnisse auf das `date`-Feld aus deiner Sammlung beschränken.

> Tipp: Du kannst einen einzelnen String oder ein Array von Strings übergeben.

## Aufgabe 11 - Einrichten von CORS

Um Probleme mit der Same-Origin-Sicherheitsrichtlinie zu vermeiden, verwenden wir die CORS-Middleware.

1. Installiere das npm-Paket cors.

2. Importiere und füge cors zu deinem Middleware-Stack hinzu.

Dies wird den gefürchteten Same-Origin-Policy-Fehler in deinem Browser verhindern.

> Hinweis: Denke daran, deine Middleware vor allen deinen Routen auszuführen!

## Aufgabe 12 - Ausführen und Testen unserer API

Jetzt, wo alles eingerichtet ist, teste deine API mit einem Testtool wie Postman oder Insomnia (oder einem anderen Tool).

Überprüfe, ob die Ergebnisse, die du erhältst, den Erwartungen entsprechen.

Jetzt geht es weiter mit den [Frontend-Aufgaben](../client/FRONTEND_TASKS_DE.md) 🥳
