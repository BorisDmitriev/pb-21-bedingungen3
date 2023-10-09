# Fullstack-Paginierung

![Seite umblättern](https://media.giphy.com/media/xT77Y1T0zY1gR5qe5O/source.gif)

Diese Aufgabe kombiniert sowohl Frontend als auch Backend. Du wirst eine einfache Website erstellen, die Paginierungskonzepte implementiert.

Was du tun wirst:

> - Paginierung im Backend mit Mongoose handhaben
> - Eine Benutzeroberfläche erstellen, um die Paginierung im Frontend mit React zu handhaben

Dieses Projekt setzt voraus, dass du bereits Erfahrung hast mit:

> - Mongoose Schemas und Models
> - Daten aus einer Sammlung abfragen
> - Erstellen von Routen und Endpunkten in Express
> - Einige grundlegende React-Kenntnisse

## Ordnerstruktur und Vorbereitung

Es gibt 2 Ordner:

1. `/client` - dieser enthält das `create-react-app` erstellte React-Frontend
   - Dies wird auf Port `3000` laufen
    
2. `/server` - dieser enthält den Backend-Code
   - Dies wird auf Port `3001` laufen

## Aufgaben

1. Vervollständige die [Backend-Aufgaben](./server/BACKEND_TASKS_DE.md)
2. Vervollständige die [Frontend-Aufgaben](./client/FRONTEND_TASKS_DE.md)

## Bonus-Aufgaben

### Bonus 1 - Sortieroptionen hinzufügen

Deine Benutzer möchten möglicherweise mehr Kontrolle darüber haben, wie die Daten angezeigt werden, zum Beispiel nach Preis sortieren.

##### Frontend

1. Aktualisiere deine Benutzeroberfläche, um neue Schaltflächen zum Sortieren hinzuzufügen. Diese Schaltflächen sollten auf bestimmte Kriterien verweisen, die deine Sammlung bereitstellt.

##### Backend

1. Du musst dein Backend aktualisieren, um einen Sortierparameter zusammen mit dem Skip-Parameter zu empfangen.

2. Du solltest im Backend überprüfen, ob der empfangene Parameter gültig ist.
