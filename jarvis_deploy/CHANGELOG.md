# Changelog

## 0.1.5

- Schreibgeschütztes Konfigurationsinventar für Skripte, Automatisierungen, Assist-Freigaben und OpenAI-Conversation-Agenten.
- Redigierte Inventar-Snapshots (A) mit Download über die authentifizierte Admin-Oberfläche.
- Vorschau von Config-Bundles ohne Apply-Funktion.
- Native Add-on-Updates über ein Home-Assistant-Repository; keine manuellen ZIP-Updates mehr.
- Datenmigration legt importierte Optionen nur als Vorschlag ab; Supervisor-Optionen bleiben maßgeblich.
- Migration prüft alle Ziele vor der ersten Änderung und stellt Zustand/Schlüssel bei Fehlern aus einem Sicherungsordner wieder her.
- Testkanal blockiert produktive Deployments, Rollbacks und Recovery; Import produktiver Migrationsarchive, Schlüssel, Zustände und Backups ist vollständig deaktiviert.
- Release-Veröffentlichung nur manuell mit `confirm_publish=PUBLISH`; Tag-Pushes veröffentlichen nichts.
- Produktive Deployments bleiben standardmäßig deaktiviert und benötigen weiterhin eine ausdrückliche Freigabe.
