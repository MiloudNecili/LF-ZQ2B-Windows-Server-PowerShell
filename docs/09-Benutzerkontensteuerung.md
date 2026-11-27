# Benutzerkontensteuerung (UAC)

## Durchführung

Auf `DC` wurde die **Default Domain Policy** im Gruppenrichtlinienverwaltungs-Editor geöffnet:

```text
Computerkonfiguration
└── Richtlinien
    └── Windows-Einstellungen
        └── Sicherheitseinstellungen
            └── Lokale Richtlinien
                └── Sicherheitsoptionen
```

Die Richtlinien unter **Benutzerkontensteuerung** wurden geöffnet und ihre Registerkarte **Erklärung** eingesehen. Es wurden keine Einstellungen geändert.

## Wichtige Richtlinien

| Richtlinie | Funktion |
|---|---|
| Administratorbestätigungsmodus | Steuert die Rechteerhöhung für Administratoren. |
| Verhalten der Eingabeaufforderung für Administratoren | Legt fest, ob und wie eine Zustimmung erforderlich ist. |
| Verhalten der Eingabeaufforderung für Standardbenutzer | Legt die Anforderung von Administrator-Anmeldedaten fest. |
| Zum sicheren Desktop wechseln | Schützt den Bestätigungsdialog vor Interaktionen anderer Anwendungen. |
| Anwendungsinstallationen erkennen | Erkennt Installationsprogramme mit erhöhtem Rechtebedarf. |
| Nur signierte und überprüfte ausführbare Dateien heraufstufen | Beschränkt die Rechteerhöhung auf vertrauenswürdig signierte Dateien, wenn aktiviert. |
| Datei- und Registrierungsschreibfehler virtualisieren | Unterstützt ältere Anwendungen durch Umleitung bestimmter Schreibzugriffe. |

## Ergebnis

Die Funktionsweise der UAC-Richtlinien wurde nachvollzogen. Die vorhandene Sicherheitskonfiguration blieb unverändert.
