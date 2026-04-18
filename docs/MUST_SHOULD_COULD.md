# Must / Should / Could (MoSCoW) - Dragon Ball 2D Tower Defense

## Zielbild
Eigenstaendiges 2D-Tower-Defense-Spiel im Dragon-Ball-Kosmos (DB/DBZ/GT/Super), inspiriert von PokePath in Struktur und Lesbarkeit, aber ohne Klon-Umsetzung.

## Must (Release-kritisch)
- Spielbares Core-Loop: Unit platzieren -> Wellen abwehren -> Sieg/Niederlage.
- Stabiler 2D-Tech-Stack (`Phaser 3 + TypeScript + Vite`) mit sauberer Projektstruktur.
- Mindestens 1 voll spielbare Blaupausen-Map mit Pfad, Spawnpunkten, Zielpunkt und 100 Wellen.
- Encounter-Taktung in der Blaupausen-Map: schwerer Encounter alle 10 Wellen (10-90), Endboss auf Welle 100.
- Bereichs-Placement pro Map: Wasser, Feld, Gras, Wald, Gebirge, Himmel.
- Unit-Deployment-Regel: Jede Unit darf exakt 1-3 spezifische Bereiche abdecken (Spezialist bis flexibel).
- Grundsysteme: Placement-Regeln, Targeting, Angriffstimer, Schaden, HP, Kills.
- Mindestens 8-10 spielbare Units mit klaren Rollen (Single-Target, AoE, Slow, Support).
- Mindestens 10 Gegnertypen inkl. 1 Boss-Welle.
- Upgrade-System pro Unit (mindestens 2 Upgrades pro Unit).
- Basis-HUD: Gold/Kosten, Leben, Wave-Info, Start/Pause, Geschwindigkeit (1x/2x).
- Speichern der Basis-Progression (mindestens lokale Einstellungen und freigeschaltete Inhalte).
- Performance-Ziel: fluesige Darstellung auf Desktop-Browsern (stabil spielbar ohne starke Ruckler).
- Rechtliche Leitplanken dokumentiert (IP-Risiko fuer oeffentliche/kommerzielle Verwertung sichtbar gemacht).

## Should (stark empfohlen)
- Saga-Mutatoren: DB, DBZ, GT, Super mit je eigener Regelbesonderheit.
- Ki-System mit aktivierbaren Ultimate-Skills.
- Team-Synergien (z. B. Saiyajin, Namekianer, Androiden, Goetter).
- 4-6 weitere Maps mit steigender Komplexitaet.
- Schwierigkeitsgrade oder Challenge-Modi.
- Gegner-Statussysteme (Stun, Burn, Slow, Armor Break).
- Bessere UX: Unit-Tooltip, Reichweiten-Vorschau, Upgrade-Vergleich, Wellenvorschau.
- Audio-Basics: Treffer-SFX, Wave/Boss-Cues, UI-Feedback.
- Telemetrie fuer Balancing (Winrate, meistgenutzte Units, Abbruchwellen).
- Interne QA-Checkliste und regelmaessige Playtests pro Milestone.

## Could (nice to have)
- Co-op oder asynchroner Vergleichsmodus (Highscore/Leaderboard).
- Taegliche/woechentliche Challenges.
- Kosmetische Skins, VFX-Varianten, alternative UI-Themes.
- Story-Event-Missionen mit kurzen Dialog-Intros.
- Map-Editor fuer interne Content-Produktion.
- Replays und Share-Codes.
- Achievement-System.
- Mobile-optimierte Touch-Steuerung als zweiter Schritt.

## Nicht Teil des Scopes (vorerst)
- 3D-Umsetzung.
- Vollstaendige Plattform-Portierung (Konsole/Native Mobile).
- Umfangreiche Multiplayer-Features zum Start.
- 1:1-Nachbau von PokePath-Mechaniken, UI oder Zahlenwerten.

## Definition of Done fuer den ersten Vertical Slice
- Eine Runde ist von Start bis Ende ohne Debug-Eingriffe spielbar.
- Keine blocker Bugs in Placement, Wellenstart, Sieg/Niederlage.
- Klar erkennbarer Fortschritt durch Unit-Upgrades.
- Erste Balancing-Basis vorhanden (keine offensichtliche "eine Unit gewinnt alles"-Meta).
