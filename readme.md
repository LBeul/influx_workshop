# Influx Workshop @ HTW Berlin

## Influx installieren und konfigurieren

- InfluxDB lokal oder via Docker [installieren](https://docs.influxdata.com/influxdb/v2/install/)
  - Vorteil bei Docker: Initiales Setup direkt mit dabei &die nächsten Schritte bis zum API Token können übersprungen werden
- Falls lokal installiert -> [Influx starten](https://docs.influxdata.com/influxdb/v2/install/#start-influxdb)
- Falls lokal installiert -> InfluxD via UI [initial einrichten](https://docs.influxdata.com/influxdb/v2/get-started/setup/)
  - Username und Passwort vergeben
  - Organisation erstellen (z.B. "HTW")
  - Initialen Bucket erstellen (z.B. "sensor_data")
- [API Token erstellen](https://docs.influxdata.com/influxdb/v2/admin/tokens/create-token/) und für die Nutzung in Node RED speichern

## Bucket manuell mit Daten füllen

- Nutzt das .csv-File um euren Influx Bucket mit initialen Daten zu befüllen
  - Dazu einfach auf das Upload-Symbol in der Sidebar klicken und den Reiter `Buckets` auswählen
  - Den gewünschten Bucket für die Sensordaten auswählen (oder neuen anlegen)
  - auf `+ ADD DATA` klicken und `CSV Upload` auswählen
  - Das `sensor_dump_240515.csv` File einfügen
