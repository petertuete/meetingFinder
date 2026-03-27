# Meeting-Zeitfinder

Ein kleines, lokales Tool zur Ermittlung der besten Meeting-Zeit auf Basis einer Wochenansicht. Jeder Teilnehmer markiert anonym direkt im Raster, wann er verfuegbar ist.

## Start

1. Datei index.html im Browser oeffnen.
2. Fuer jede Person auf Nächste anonyme Person klicken.
3. In der Wochenansicht per Maus oder Finger markieren:
   - Klicken/ziehen markiert Slots als verfuegbar.
   - Erneut auf markierte Slots ziehen entfernt sie wieder.
4. Dauer und Anzahl Vorschlaege waehlen.
5. Auf Berechnen klicken.

## Wie gerechnet wird

- Das Tool nutzt 30-Minuten-Slots von 06:00 bis 22:00.
- Ein Vorschlag zaehlt nur dann fuer eine Person, wenn das gesamte Zeitfenster markiert ist.
- Ausgabe: Top-Zeitslots mit Verfuegbarkeitsquote.

## Hinweise

- Alles ist anonym (Person 1, Person 2, ...).
- Die Daten bleiben nur im Browser-Tab (kein Server, keine Cloud).
