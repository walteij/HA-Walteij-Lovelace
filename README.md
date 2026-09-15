# HA-Walteij-Lovelace

HACS Frontend plugin repository for the MLB Standings and ARR Media Manager Lovelace cards.

Current version: 1.0.0.2

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

ARR Media Manager cards are available from the same frontend repository:

- `/hacsfiles/ha-walteij-lovelace/arr-media-manager-card.js`
- `/hacsfiles/ha-walteij-lovelace/arr-media-search-card.js`

Register either file as a `JavaScript Module` resource. Restart Home Assistant after installing or updating the repository and hard-refresh the browser if an older cached resource remains.

## ARR Media Manager cards

### Search and download card

Use `custom:arr-media-manager-card` for a one-step search-and-add workflow:

```yaml
type: custom:arr-media-manager-card
title: ARR zoeken
config_entry_id: YOUR_ARR_CONFIG_ENTRY_ID
search_after_add: true
```

### Lookup result card

Use `custom:arr-media-search-card` when you want to inspect multiple lookup results and explicitly choose which result to add:

```yaml
type: custom:arr-media-search-card
title: Media zoeken
config_entry_id: YOUR_ARR_CONFIG_ENTRY_ID
max_results: 10
search_after_add: true
show_overview: true
show_posters: true
show_existing: true
confirm_before_add: true
```

The ARR config entry determines whether the request is sent to Sonarr, Radarr, or Lidarr. Do not add an application selector to the card. The card calls the `arr_media_manager.lookup` and `arr_media_manager.add_media` actions directly.

Optional root-folder and quality-profile selectors can be configured when instance-specific values are known:

```yaml
root_folder_options:
	- /media/movies
	- /media/tv
quality_profile_options:
	- value: 1
		label: HD-1080p
```

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
