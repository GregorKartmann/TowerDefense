# Map Blueprint V1 - Must-Konzept fuer 100-Wellen-Maps

## Ziel
Eine wiederverwendbare Blaupause fuer jede zukuenftige Map, damit Balancing, Content-Produktion und technische Umsetzung konsistent bleiben.

## Annahme
Die Vorgabe "alle 10 Maps ein schwerer Encounter" wird fuer diese Blaupause als "alle 10 Wellen ein schwerer Encounter" innerhalb einer 100-Wellen-Map interpretiert.

## Nicht verhandelbare Regeln (Must)
- Jede Map hat exakt 100 Wellen.
- Schwere Encounter auf Welle 10, 20, 30, 40, 50, 60, 70, 80, 90.
- Welle 100 ist immer Endboss (mehrphasig).
- Jede Map enthaelt alle 6 Bereichstypen fuer Placement:
  - Wasser
  - Feld
  - Gras
  - Wald
  - Gebirge
  - Himmel
- Jede Unit hat 1-3 erlaubte Bereichstypen (`deployZones`).

## Bereichs-System (Placement)

### Taktische Rolle je Bereich
- Wasser: Control/Slow, Linienkontrolle, eher wenige Slots.
- Feld: Allround-Flache, Standard-DPS, oekonomisch effizient.
- Gras: Hinterhalt/Tempo-Boni, mittlere Reichweite.
- Wald: Utility und Debuffs, Blocksicht als Designhebel.
- Gebirge: Hohe Reichweite, starke Alpha-Treffer, schwerer Zugang.
- Himmel: Anti-Air/Support, hohe Flexibilitaet, oft teuer.

### Slot-Budget fuer eine Blaupausen-Map
Empfehlung bei 60 Build-Slots:
- Wasser: 8
- Feld: 14
- Gras: 10
- Wald: 10
- Gebirge: 10
- Himmel: 8

Regel fuer Folge-Maps:
- Jeder Bereich muss mindestens 6 Slots haben.
- Kein Bereich darf mehr als 30 Prozent aller Slots halten.
- Primar-Biome einer Map duerfen +4 Slots erhalten, Sekundaer-Biome +2.

## Unit-Bereichsmodell (1-3 deployZones)

### Klassen
- Spezialist (1 Bereich): hoechste Effizienz, harte Platzierungs-Limits.
- Hybrid (2 Bereiche): gute Effizienz, gutes Risiko/Belohnungsprofil.
- Flex (3 Bereiche): maximale Platzierbarkeit, dafuer geringere Effizienz pro Kostenpunkt.

### Balancing-Startwerte
- 1 Bereich: Power-Faktor 1.15, Kosten-Faktor 1.00
- 2 Bereiche: Power-Faktor 1.07, Kosten-Faktor 1.05
- 3 Bereiche: Power-Faktor 1.00, Kosten-Faktor 1.12

Hinweis:
Diese Faktoren sind Startwerte fuer den Vertical Slice und werden nach Playtests angepasst.

## 100-Wellen-Struktur (pro Map)

### Kapitelstruktur
Die 100 Wellen werden in 10 Kapitel zu je 10 Wellen geteilt:
- Wellen X1-X6: Standarddruck und Ressourcenaufbau.
- Wellen X7-X8: Spike-Wellen (mehr Dichte oder Resistenzmix).
- Welle X9: Vorbereitung/Pruefung fuer den Encounter.
- Welle X10: Schwerer Encounter.

Beispiel:
- Kapitel 1: Wellen 1-10 (Welle 10 Encounter)
- Kapitel 2: Wellen 11-20 (Welle 20 Encounter)
- ...
- Kapitel 9: Wellen 81-90 (Welle 90 Encounter)
- Kapitel 10: Wellen 91-100 (Welle 100 Endboss statt normaler Encounter)

### Schwierigkeitskurve (Richtwert)
- Kapitel 1-2: Onboarding und Build-Identitaet.
- Kapitel 3-4: Resistenz-Checks und Lane-Druck.
- Kapitel 5-6: Mixed-Comp-Pruefung (Air + Armor + Speed).
- Kapitel 7-8: Ressourcenstress und Platzierungsoptimierung.
- Kapitel 9: Vor-Endboss-Check.
- Kapitel 10: Endgame und Bosskampf.

## Encounter-Design (Wellen 10-90)

Jeder schwere Encounter sollte exakt diese Bausteine haben:
- 1 Kernbedrohung (Mini-Boss oder Elite-Formation)
- 1 Sekundaermechanik (z. B. Shield-Aura, Summons, Regeneration, Air-Surge)
- 1 klare Konter-Antwort (z. B. Anti-Air, Armor-Break, Burst-Fenster)
- 1 sichtbare Belohnung (Bonus-Gold, Upgrade-Punkt, temporarer Buff)

Ziel:
Alle 10 Wellen ein bewusstes "Build-Checkpoint"-Gefuehl erzeugen.

## Endboss-Design (Welle 100)

Der Endboss ist 3-phasig:
- Phase 1 (100% bis 70% HP): Basisfaehigkeiten + Adds.
- Phase 2 (70% bis 35% HP): neue Mechanik (z. B. Bereichsdebuff oder Lane-Split).
- Phase 3 (35% bis 0% HP): Enrage, erhoehte Geschwindigkeit/Schaden, kurzes Burst-Fenster.

Pflichtkriterien fuer den Boss:
- Keine "Stat-Check only"-Loesung.
- Mindestens ein Counterplay-Fenster pro Phase.
- Lesbare Telegraphs fuer Kernangriffe.

## Blueprint-Template fuer neue Maps

Jede neue Map wird mit dieser Checkliste gebaut:
- Map-Identitaet: Thema, Primar- und Sekundaer-Biome
- Pfadlayout: Anzahl Lanes, Merge/Split-Punkte, kritische Chokepoints
- Slotverteilung auf 6 Bereichstypen
- Kapitelplan 1-10 mit Encounter-Mechanik je 10er-Block
- Endboss-Mechanik und 3 Phasen
- Erwartete Rundendauer und Ziel-Schwierigkeit

## Datenmodell (technische Grundlage)

```json
{
  "mapId": "map_01",
  "wavesTotal": 100,
  "zones": ["water", "field", "grass", "forest", "mountain", "sky"],
  "buildSlots": [
    { "id": "s_001", "zone": "field", "x": 12, "y": 6 }
  ],
  "encounterWaves": [10, 20, 30, 40, 50, 60, 70, 80, 90],
  "bossWave": 100
}
```

```json
{
  "unitId": "unit_goku_base",
  "deployZones": ["field", "grass"],
  "role": "dps_hybrid",
  "cost": 180
}
```

## Must-Umsetzung in 4 Schritten
- Schritt 1: Bereichssystem + `deployZones`-Regel technisch implementieren.
- Schritt 2: Map-01 mit 60 Slots und 6 Bereichstypen aufbauen.
- Schritt 3: Wave-Director fuer 100 Wellen inkl. Encounter-Taktung (10-90) bauen.
- Schritt 4: Endboss-Welle 100 mit 3 Phasen und klaren Telegraphs integrieren.

## Definition of Done fuer die Blaupausen-Map
- Alle 100 Wellen sind ohne Skriptluecke spielbar.
- Encounter-Wellen 10-90 fuehlen sich als Build-Checks klar unterschiedlich an.
- Boss-Welle 100 ist mehrphasig und fair lesbar.
- Mindestens 8 Units mit 1-3 `deployZones` sind sinnvoll spielbar.
- Die Blaupause kann mit minimalen Parameteraenderungen auf Map-02 kopiert werden.
