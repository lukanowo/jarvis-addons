# Changelog

## 0.1.7

- Migration toleriert die von Supervisor 2026.11.0 erzeugten Wurzel-Verzeichniseinträge `.` und `./` im äußeren und inneren App-Archiv.
- Die strikte Prüfung von Pfaden, absoluten Pfaden, `..`-Pfaden, Symlinks, Hardlinks, doppelten Einträgen und Größenlimits bleibt unverändert.
- Wurzel-Verzeichniseinträge werden weiterhin auf das Eintragslimit angerechnet.
- Eine vollständige synthetische Supervisor-Migration sowie ein Upload über 50 MiB werden getestet.
- `ingress_stream: true` und das mitgelieferte AppArmor-Profil bleiben unverändert.

## 0.1.6

- Migrationsupload über Home-Assistant-Ingress streamt jetzt (`ingress_stream: true`); die 16-MiB-Grenze des Ingress-Proxys wird dadurch umgangen.
- Eigenes Upload-Limit von 256 MiB für Migrationsarchive; normale API-Anfragen bleiben auf 16 MiB begrenzt.
- Das innere App-Archiv wird direkt aus dem äußeren Supervisor-Backup gestreamt und nicht vollständig in den Arbeitsspeicher geladen.
- Nicht benötigte Bestandteile wie `image.tar` und `supervisor.tar.gz` werden weder extrahiert noch in `/data` abgelegt.
- Staging- und Upload-Temporärdateien werden nach Erfolg, Fehler und abgebrochener Verbindung entfernt; beim Start werden Reste eines früheren Prozesses aufgeräumt.
- Produktive Dateien werden erst nach bestandener Vorprüfung verändert.
- Tar-Bomben-, Pfad-, Symlink- und Größenprüfungen bleiben erhalten; Testkanal-Sperren bleiben vollständig aktiv.
- Das native Add-on liefert das bestehende `apparmor.txt` wieder mit; dadurch wird das restriktive Profil `jarvis_deploy` statt `docker-default` geladen.
- Automatisierte Tests decken synthetische Backups über 50 MiB, Abbrüche, Größenüberschreitungen und beschädigte Archive ab.

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
