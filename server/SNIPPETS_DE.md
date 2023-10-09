# Schnipsel

Kleine Code-Stücke, die dir bei dieser Aufgabe helfen

##### Schema-Vorlage
```javascript
// Vergiss nicht, den Variablennamen zu ändern!
const mySchema = new mongoose.Schema({
});
```

##### Model-Vorlage

```javascript
const Model = mongoose.model();
```

##### Router mit einer GET-Anfrage

```javascript
import express from 'express';
const router = express.Router();

// Erfasse alle GET-Anfragen zur Route
router.get('/', (request, response) => {
});

module.exports = router;
```

##### Router GET-Anfrage mit Parametern
```javascript
// Ersetze "/path" durch deinen eigenen Pfad
// Ersetze ":param1" durch deinen eigenen Parameter
// Füge so viele Parameter hinzu, wie du benötigst
router.get('/path/:param1', (request, response) => {
    const params = request.params;
});
```

##### Router GET-Anfrage mit Query-Parametern
```javascript
// Ersetze "/path" durch deinen eigenen Pfad
router.get('/path', (request, response) => {
    const query = request.query;
});
```

##### Verwendung einer Route-Anwendung
```javascript
// Vergiss nicht, deinen Router zu importieren, wenn du ihn in einer separaten Datei gespeichert hast!
// Ersetze "/path" durch deinen eigenen Pfad
// Ersetze "router" durch die Referenz zu deinem Router

app.use('/path', router);
```
