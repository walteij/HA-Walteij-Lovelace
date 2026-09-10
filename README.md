# HA-Walteij-Lovelace

HACS Frontend plugin repository for the MLB Standings Lovelace card.

## Install via HACS

1. Open HACS.
2. Go to Frontend.
3. Open the menu and choose Custom repositories.
4. Add this repository URL and choose category Frontend.
5. Install MLB Standings Card.
6. Restart Home Assistant.

After install, HACS should register the resource automatically.
If needed, add the resource manually:

- URL: /hacsfiles/ha-walteij-lovelace/mlb-standings-card.js
- Type: JavaScript Module

## Card type

Use this card type in Lovelace:

```yaml
type: custom:mlb-standings-card
```

## Examples

```yaml
type: custom:mlb-standings-card
mode: division
league: AL
division: East
title: AL East Standings
```

```yaml
type: custom:mlb-standings-card
mode: postseason
league: AL
title: AL Postseason
```

```yaml
type: custom:mlb-standings-card
mode: postseason
league: NL
title: NL Postseason
```

```yaml
type: custom:mlb-standings-card
mode: postseason
postseason_scope: combined
title: MLB Postseason
```
