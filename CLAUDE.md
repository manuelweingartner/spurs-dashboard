# San Antonio Spurs Dashboard - JARDINDUVIN

## Projekt-Info
- **Typ**: Einzelne HTML-Datei (kein Build-System)
- **Sprache**: Deutsch (Schweizer Kontext)
- **Pfad**: `P:\4 Private Projekte\Claude Coding\spurs-website\index.html`
- **Nutzer**: JARDINDUVIN (Spurs-Fan aus der Schweiz)

## Tech-Stack
- Vanilla HTML/CSS/JavaScript (kein Framework)
- Google Fonts: Inter (300-900)
- Alle Daten via ESPN API (keine API-Keys nötig)

## Design
- Spurs-Farben: Schwarz (#0a0a0a), Silber (#C4CED4), Weiss
- Dunkles Theme mit Karten-Layout
- Responsive (Desktop + Mobile)
- Team-Logos von ESPN CDN: `https://a.espncdn.com/i/teamlogos/nba/500/{teamId}.png`
- Spieler-Fotos von ESPN CDN: `https://a.espncdn.com/combiner/i?img=/i/headshots/nba/players/full/{playerId}.png`

## ESPN API Endpoints
- **Team Schedule**: `https://site.api.espn.com/apis/site/v2/sports/basketball/nba/teams/24/schedule`
- **Game Summary/Boxscore**: `https://site.web.api.espn.com/apis/site/v2/sports/basketball/nba/summary?event={gameId}`
- **Standings**: `https://site.api.espn.com/apis/v2/sports/basketball/nba/standings`
- **CORS Proxy Fallback**: `https://api.allorigins.win/raw?url=` (nötig bei file:// Protokoll)
- **Spurs Team ID**: `24`

## Navigation (Tab-System)
Sticky Tab-Leiste unterhalb des Hero-Bereichs mit 4 Tabs:
1. **Übersicht**: Countdown + Kommende Spiele
2. **Ergebnisse**: Letzte 10 Ergebnisse
3. **Spieler**: Starting Five Stats + Spieler des Monats
4. **Team Info**: Injury Report + Standings + Championship Contender

## Features
1. **Hero-Bereich**: De'Aaron Fox (#4) + Wembanyama (#1), echtes Spurs-Logo, JARDINDUVIN-Branding
2. **Countdown**: Live-Countdown zum nächsten Spiel (Schweizer Zeit)
3. **Spielplan**: Alle kommenden Spiele, zeigt 10 an mit "Alle anzeigen" Button (ohne TV-Spalte)
4. **Ergebnisse**: Letzte 10 Spiele mit Sieg/Niederlage-Karten, klickbar für ESPN-Boxscore
5. **Starting Five Stats**: Durchschnitte der 5 häufigsten Starter + aufklappbarer Gamelog (PTS, REB, AST, BLK, STL)
6. **Injury Report**: Aktuelle Verletzungen mit Farbcodierung (Out=Rot, Doubtful=Orange, Questionable=Gelb, Day-to-Day=Grün)
7. **Spieler des Monats**: Automatisch berechnet aus PTS+REB+AST+STL+BLK, zeigt Top 3
8. **Western Conference Standings**: Tabelle mit Spurs hervorgehoben, Playoff-Trennlinien
9. **Championship Contender**: Kreisförmiger Score basierend auf Win%, L10, Diff, Platzierung

## JARDINDUVIN Branding
- Logo: `https://pbs.twimg.com/profile_images/1342389942698323970/4FBBDglu_400x400.jpg`
- Erscheint in: Top-Bar, Hero-Badge, Footer

## Wichtige Hinweise
- Alle Zeiten werden in Schweizer Ortszeit angezeigt (Europe/Zurich)
- Fox trägt die Nummer #4 bei den Spurs (nicht #5 wie bei Sacramento)
- API-Aufrufe nutzen erst Direct Fetch, dann CORS-Proxy als Fallback
- Boxscores werden in 3er-Batches geladen um Rate Limits zu vermeiden
