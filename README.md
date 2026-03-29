
# Meeting-Zeitfinder

Ein kleines, lokales Tool zur Ermittlung der besten Meeting-Zeit auf Basis einer Wochenansicht. Jeder Teilnehmer gibt anonym seine Verfügbarkeit je Wochentag über eine mobile-optimierte, einzeilige Tageszeilen-Eingabe (Checkbox + Zeitfenster) ein.

## Start

1. Datei index.html im Browser oeffnen.
2. Neue Planung erstellen:
   - Zugriffs-Kennwort vergeben (wird zum Laden und Speichern benoetigt).
   - Loesch-Kennwort vergeben (nur fuer Neu planen / Loeschen).
   - Zugriffs-Kennwort und lokaler Zwischenstand werden nur fuer den aktuellen Browser-Tab gespeichert.
3. Bestehender Planung beitreten:
   - Plan-ID und Zugriffs-Kennwort eingeben.
   - Nach der Nutzung den Browser-Tab schliessen, damit Kennwort und lokaler Zwischenstand aus der Sitzung entfernt werden.
4. Fuer jede Person auf Naechste anonyme Person klicken.
5. In der Wochenansicht je Wochentag die Checkbox aktivieren und das gewünschte Zeitfenster (von/bis) direkt eingeben.
6. Dauer und Anzahl Vorschlaege waehlen.
7. Auf Berechnen klicken.
8. Mit Plan loeschen wird die gesamte Planung entfernt (nur mit Loesch-Kennwort).

## Wie gerechnet wird

- Das Tool nutzt 30-Minuten-Slots von 06:00 bis 22:00.
- Ein Vorschlag zählt nur dann für eine Person, wenn das gesamte Zeitfenster innerhalb des angegebenen Bereichs liegt.
- Ausgabe: Top-Zeitslots mit Verfügbarkeitsquote.

## Hinweise

- Alles ist anonym (Person 1, Person 2, ...).
- Die eigentliche Planung wird in Supabase Cloud gespeichert.
- Für die aktuelle Sitzung liegen Zugriffs-Kennwort und lokaler Zwischenstand nur im `sessionStorage` des aktuellen Browser-Tabs und verschwinden beim Schließen des Tabs.
- Plan-Links enthalten nur die Plan-ID. Das Zugriffs-Kennwort muss separat geteilt werden.
- Alle Cloud-Zugriffe laufen über Supabase-RPC-Funktionen (kein direkter Tabellenzugriff im Frontend).
- Plan löschen entfernt alle bisherigen Eingaben komplett und benötigt das Lösch-Kennwort.

### Mobile-Optimierung

Die Eingabe der Verfügbarkeit ist jetzt immer einzeilig, übersichtlich und besonders für Mobilgeräte optimiert. Jede Tageszeile enthält Checkbox und Zeitfenster nebeneinander.
