# Meeting-Zeitfinder

Ein kleines, lokales Tool zur Ermittlung der besten Meeting-Zeit auf Basis einer Wochenansicht. Jeder Teilnehmer markiert anonym direkt im Raster, wann er verfuegbar ist.

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
5. In der Wochenansicht per Maus oder Finger markieren:
   - Klicken/ziehen markiert Slots als verfuegbar.
   - Erneut auf markierte Slots ziehen entfernt sie wieder.
6. Dauer und Anzahl Vorschlaege waehlen.
7. Auf Berechnen klicken.
8. Mit Plan loeschen wird die gesamte Planung entfernt (nur mit Loesch-Kennwort).

## Wie gerechnet wird

- Das Tool nutzt 30-Minuten-Slots von 06:00 bis 22:00.
- Ein Vorschlag zaehlt nur dann fuer eine Person, wenn das gesamte Zeitfenster markiert ist.
- Ausgabe: Top-Zeitslots mit Verfuegbarkeitsquote.

## Hinweise

- Alles ist anonym (Person 1, Person 2, ...).
- Die eigentliche Planung wird in Supabase Cloud gespeichert.
- Fuer die aktuelle Sitzung liegen Zugriffs-Kennwort und lokaler Zwischenstand nur im `sessionStorage` des aktuellen Browser-Tabs und verschwinden beim Schliessen des Tabs.
- Plan-Links enthalten nur die Plan-ID. Das Zugriffs-Kennwort muss separat geteilt werden.
- Alle Cloud-Zugriffe laufen ueber Supabase-RPC-Funktionen (kein direkter Tabellenzugriff im Frontend).
- Plan loeschen entfernt alle bisherigen Eingaben komplett und benoetigt das Loesch-Kennwort.
