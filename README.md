# Energiekarte für Waschmaschine und Trockner

<p align="center">
  <img src="https://raw.githubusercontent.com/Ronny-1979/ha-energy-card/main/logo.svg" width="400">
</p>

Eine Lovelace Custom Card für Home Assistant zur Anzeige von Waschmaschine, Trockner, Monatsverbrauch, Jahresverbrauch und Kosten.

## Features

- 📅 Monatsweise Navigation (vor und zurück)
- ⚡ Verbrauch in kWh und Kosten in € pro Gerät
- 📆 Jahresübersicht mit Aufschlüsselung pro Gerät
- 🔄 Läufe-Zähler pro Monat
- 🎨 Farbiger Status – grün (Wäscht) / blau (Trocknet) / gedimmt (Aus)
- ⚙️ Vollständig konfigurierbar über den HA-Editor

## Installation über HACS

1. HACS öffnen
2. Drei Punkte oben rechts
3. Benutzerdefinierte Repositories
4. Repository-URL einfügen: `https://github.com/Ronny-1979/ha-energy-card`
5. Kategorie: Dashboard
6. Hinzufügen
7. Karte herunterladen

## Manuelle Installation

1. `ha-energy-card.js` herunterladen
2. In `/config/www/` ablegen
3. In HA unter Einstellungen → Dashboards → Ressourcen hinzufügen:
   `/local/ha-energy-card.js` als JavaScript-Modul

## Konfiguration

```yaml
type: custom:ha-energy-card
price_entity: input_number.energiepreis_kwh
washer_energy: sensor.waschmaschine_energy_total
washer_status: binary_sensor.waschmaschine
washer_running_value: "on"
washer_runs_statistic: sensor.waschmaschine_laeufe
washer_icon: mdi:washing-machine
dryer_energy: sensor.trockner_energy_total
dryer_status: binary_sensor.trockner
dryer_running_value: "on"
dryer_runs_statistic: sensor.trockner_laeufe
dryer_icon: mdi:tumble-dryer
```

## Voraussetzungen

- Home Assistant mit aktiviertem Recorder
- Energie-Sensoren mit steigendem Gesamtzähler (kWh total)
- Binary Sensor für den Status der Geräte
- Counter oder Statistik-Sensor für die Läufe
