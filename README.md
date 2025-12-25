# Familien-Dashboard

Ein modernes, responsives Dashboard für Familien mit Echtzeit-Informationen.

## Features

- **Datum & Uhrzeit**: Aktuelle Zeit, Datum und Wochentag (oben links)
- **Wetter**: Live-Wetterdaten für Berlin (oben rechts)
  - Temperatur
  - Wetterbedingungen mit Icons
  - Luftfeuchtigkeit
  - Windgeschwindigkeit
- **Kalender**: Wochenansicht (unteres Drittel)
  - Zeigt die aktuelle Woche (Montag bis Sonntag)
  - Hebt den aktuellen Tag hervor
  - Unterstützt ICS-Kalender-Import

## Verwendung

### Dashboard öffnen

Öffnen Sie einfach die `index.html` Datei in einem modernen Browser (Chrome, Firefox, Edge, Safari).

Für die beste Darstellung:
- Nutzen Sie den Vollbildmodus (F11 in den meisten Browsern)
- Empfohlene Auflösung: 1920 x 1080 Pixel (16:9 Format)

### ICS-Kalender laden

1. Klicken Sie auf den Button "📎 ICS-Datei laden" im Kalenderbereich
2. Wählen Sie eine ICS-Kalenderdatei von Ihrem Computer
3. Die Termine der aktuellen Woche werden automatisch angezeigt

**ICS-Dateien erhalten Sie von:**
- Google Calendar (Exportfunktion)
- Outlook (Kalender exportieren)
- Apple Calendar
- Anderen Kalenderprogrammen

### Wetter-API

Das Dashboard verwendet die kostenlose [Open-Meteo API](https://open-meteo.com/) für Wetterdaten.
- Keine API-Key erforderlich
- Updates alle 10 Minuten
- Aktuelles Wetter für Berlin

## Technische Details

- **Single-Page-Application**: Alles in einer HTML-Datei
- **Keine externen Abhängigkeiten**: Funktioniert offline (außer Wetter-Updates)
- **Automatische Updates**:
  - Uhrzeit: Jede Sekunde
  - Kalender: Jede Minute
  - Wetter: Alle 10 Minuten

## Anpassungen

### Stadt ändern

Um die Wetteranzeige für eine andere Stadt anzupassen, ändern Sie in der `index.html` die Koordinaten in der `updateWeather()` Funktion:

```javascript
// Berlin Koordinaten: 52.52, 13.405
const response = await fetch('https://api.open-meteo.com/v1/forecast?latitude=52.52&longitude=13.405&...');
```

Ersetzen Sie die Koordinaten und aktualisieren Sie den Stadtnamen im HTML.

### Farben anpassen

Die Hintergrund-Farben können im CSS-Bereich angepasst werden:

```css
body {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
```

## Browser-Kompatibilität

- ✅ Chrome/Edge (empfohlen)
- ✅ Firefox
- ✅ Safari
- ⚠️ Internet Explorer (nicht unterstützt)

## Lizenz

Frei verwendbar für private und kommerzielle Zwecke.
