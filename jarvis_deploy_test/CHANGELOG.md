# Changelog – Testkanal

## 0.1.6

- Testimage übernimmt den gestreamten Migrationsupload und das getrennte 256-MiB-Limit aus 0.1.6.
- Import produktiver Migrationsarchive, Schlüssel, Zustände und Backups bleibt im Testkanal vollständig deaktiviert.
- Produktive Deployments, Rollbacks und Recovery bleiben technisch gesperrt.
- Das native Test-Add-on liefert das bestehende `apparmor.txt` mit; Supervisor lädt daraus das Profil `jarvis_deploy_test`.

## 0.1.5

- Testimage mit allen Inventar-, Snapshot- und Vorschaufunktionen aus 0.1.5.
- Produktive Deployments sind im Testimage technisch gesperrt, unabhängig von den Add-on-Optionen.
- Der Testkanal hat eine eigene App-ID, ein eigenes `/data` und ein eigenes GHCR-Image.
- Datenmigration legt importierte Optionen nur als Vorschlag ab; Supervisor-Optionen bleiben maßgeblich.
- Import produktiver Migrationsarchive, Schlüssel, Zustände und Backups in den Testkanal vollständig deaktiviert; Migrationstests nur mit synthetischen Testdaten.
- Produktive Deployments, Rollbacks und Recovery sind technisch gesperrt.
