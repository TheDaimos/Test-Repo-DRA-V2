# DRA V2 – Sicheres Installations-Testprojekt

Dieses öffentliche Repository enthält **ausschließlich künstliche Testdateien** zur ersten gebündelten Realabnahme von **Deploy Relay Agent V2**. Keine Tokens, personenbezogenen Daten, echten Home-Assistant-Einstellungen oder Produktivdateien.

## Installationsbereich

Das Deployment-Manifest `deploy-relay.json` schreibt ausschließlich nach:

```text
/config/dra_v2_testprojekt/
```

Das Verzeichnis ist unabhängig von `/config/custom_components/`, `.storage` und deinen bestehenden Home-Assistant-Integrationen. Die Installation benötigt laut Manifest **keinen Home-Assistant-Neustart** (`after_install: none`).

## In DRA V2 einbinden

In **Projektverwaltung → Projekt hinzufügen**:

- GitHub-Repository: `TheDaimos/Test-Repo-DRA-V2`
- Name: `DRA V2 Testprojekt`
- Aktiviert: **Ja**
- Zugriffsart: **Read-Write** (erlaubt nur nach ausdrücklicher Bestätigung eine **lokale** Installation durch DRA; **kein GitHub-Schreibzugriff**)
- Manifestdatei: `deploy-relay.json` (Standard)
- Entwicklungszweig: `main`

**Wichtig:** DRA V2 leitet die interne Projektkennung automatisch aus dem Repositorynamen ab: `test_repo_dra_v2`. Genau diese Kennung ist deshalb im Manifest hinterlegt.

## Bewusste Schutzgrenzen

Das Repository enthält nur `payload/` als Installationsquelle. Die V1-bewährte Engine in V2 soll daraus den eigenen Ordner `/config/dra_v2_testprojekt/` anlegen. **DRA V1/V2 selbst, Gewitterradar, WeatherRouter und weitere produktive Bereiche dürfen nicht verändert werden.**

### Geplanter gebündelter Realtest

Erste Installation: Quellprüfung, Vorschau, einmalige Bestätigung, serverseitiger Auftrag, Sicherung, Prüfung. Nach der ersten erfolgreichen Installation kann eine geänderte Testdatei im selben Repository einen zweiten ungefährlichen Änderungs-/Backup-Test ermöglichen. Während des ersten Auftrags kann der Browser geschlossen und der Auftrag anschließend wieder abgerufen werden.

**C.K. – Eine Idee weiter gedacht.**
