# Online stellen (Render)

Die App ist für einen Python-Web-Service vorbereitet.

## Benötigte Umgebungsvariablen
- `POOL_ENV=production`
- `POOL_PASSWORD`: dein gewünschtes Pool-Passwort
- `POOL_ORIGIN`: die endgültige HTTPS-Adresse deiner App, z. B. `https://survivor-pool-xyz.onrender.com`
- `POOL_DB`: Pfad zur SQLite-Datei. Für dauerhafte echte Nutzung sollte ein persistenter Datenträger verwendet werden.

## Start
`gunicorn server:application --bind 0.0.0.0:$PORT --workers 1 --threads 8`

Wichtig: Kostenlose Instanzen können je nach Hosting-Angebot keinen persistenten Datenträger enthalten. Ohne persistenten Datenträger können Daten bei einem Neuaufbau verloren gehen. Für eine dauerhafte Pool-Nutzung persistenten Speicher konfigurieren oder die Datenbank auf einen externen persistenten Dienst umstellen.
