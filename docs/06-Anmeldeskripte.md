# Anmeldeskripte

## Konfiguration

- `HalloUser.vbs` und `Hallo.ps1` auf `DC` erstellt.
- GPO `Anmeldeskript` erstellt und mit OU `Arbeit` verknüpft.
- VBScript unter `Benutzerkonfiguration > Richtlinien > Windows-Einstellungen > Skripts > Anmelden` hinzugefügt.
- PowerShell-Skript unter `PowerShell-Skripts` hinzugefügt.
- Beide Dateien im GPO-Verzeichnis `User\Scripts\Logon` innerhalb von `SYSVOL` abgelegt.

## Fehlerbehebung

- GPO auf `W11` für `GFNLAB\kk` angewendet, aber zunächst keine Meldungen angezeigt.
- Ursache: `scripts.ini` und `psscripts.ini` verwiesen auf lokale Dateien unter `C:\Users\Administrator\Documents`.
- Sicherungskopien der INI-Dateien erstellt und die Einträge auf `HalloUser.vbs` bzw. `Hallo.ps1` korrigiert.
- Zeichencodierung von `HalloUser.vbs` für Windows Script Host angepasst.

## Ergebnis

Nach `gpupdate /force` und erneuter Anmeldung auf `W11` wurden beide Anmeldeskripte ausgeführt:

- `Hallo.ps1`: Meldungsfenster `Logon Info` mit Benutzername und Uhrzeit.
- `HalloUser.vbs`: Begrüßungsfenster mit Benutzername und Uhrzeit; Sonderzeichen korrekt dargestellt.

![Anmeldeskripte erfolgreich ausgeführt](../images/05-anmeldeskripte-erfolgreich.png)
