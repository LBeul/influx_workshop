# Influx Workshop @ HTW Berlin

## 01 | Mit Influx loslegen 🚀

### Influx installieren und konfigurieren ⚙️

- InfluxDB lokal oder via Docker [installieren](https://docs.influxdata.com/influxdb/v2/install/)
  - Vorteil bei Docker: Initiales Setup direkt mit dabei &die nächsten Schritte bis zum API Token können übersprungen werden
- Falls lokal installiert -> [Influx starten](https://docs.influxdata.com/influxdb/v2/install/#start-influxdb)
- Falls lokal installiert -> InfluxD via UI [initial einrichten](https://docs.influxdata.com/influxdb/v2/get-started/setup/)
  - Username und Passwort vergeben
  - Organisation erstellen (z.B. "HTW")
  - Initialen Bucket erstellen (z.B. mit dem Namen `sensor_data`)
- [API Token erstellen](https://docs.influxdata.com/influxdb/v2/admin/tokens/create-token/) und für die Nutzung in Node RED speichern

### Bucket manuell mit Daten füllen 🪣

- Nutzt das .csv-File um euren Influx Bucket mit initialen Daten zu befüllen
  - Dazu einfach auf das Upload-Symbol in der Sidebar klicken und den Reiter `Buckets` auswählen
  - Den gewünschten Bucket für die Sensordaten auswählen (oder neuen anlegen)
  - auf `+ ADD DATA` klicken und `CSV Upload` auswählen
  - Das `sensor_dump_240515.csv` File einfügen

## 02 | Influx ins IoT-Projekt einbinden 🌡️

- Node RED starten und öffnen
- Benötigten Influx Node via `Menu > Manage Pallete` (oder <kbd>⌥⇧p</kbd>) installieren
  - [node-red-contrib-influxdb](https://flows.nodered.org/node/node-red-contrib-influxdb)
- Custom Flows aus diesem Repository exportieren
  - Vorher die eigenen Flows als JSON exportieren, damit nichts verloren geht! 🚨
  - In Node RED auf `Menu > Import`gehen (alt. <kbd>⌥i</kbd>)
  - Dort den JSON Content aus `writeToInflux.json` hineinkopieren
  - Dort den JSON Content aus `readFromInflux.json` hineinkopieren
- InfluxDB Nodes konfiguriern
  - Influx **Version 2.0** auswählen
  - URL der laufenden Influx Instanz (i.d.R. `http://localhost:8086/`) eingeben
  - API Token aus dem InfluxDB Setup-Schritt eingeben
  - In den `influxdb out` Nodes den zuvor angelegten Bucket spezifizieren (z.B. `sensor_data`)
  - Ggf. den Code der [Flux Queries](https://docs.influxdata.com/flux/v0/get-started/query-basics/) in den `influxdb in` Nodes anpassen (bzgl. Bucketnamen, etc.)
- Deployen und dann geht's auch schon los 🤓
