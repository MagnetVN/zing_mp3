**Notice:** Next Version (WIP) will exposed as a media_player. In the meantime, use [this](https://github.com/MagnetVN/zing_mp3/blob/master/zing_mp3.yaml) as frontend
 
# Installation

### Auto Install (Recommended)
1. Make sure you've the [Component Store](https://github.com/ttvt/hassio/tree/master/componentstore) installed and working.
2. Navigate to the Store (on the menu bar), then select Store 
3. Select **zing_mp3** and install.
4. Restart Home-Assistant.

### Manual
1. Create a directory `custom_components/zing_mp3` in your Home Assistant configuration directory.
2. Copy **all** files and sub-directories into the directory `<config directory>/custom_components/zing_mp3/`.

It should look similar to this after installation:
```
.homeassistant/ (/config in Hass.io)
|-- custom_components/
|   |-- zing_mp3/
|       |-- __init__.py
|       |-- manifest.json
|       |-- services.yaml
|       |-- etc...
```

3. Add the following to your configuration.yaml file.
```yaml
zing_mp3:
```

4. To use as frontend please reference to [this file](https://github.com/MagnetVN/zing_mp3/blob/master/zing_mp3.yaml)


# Usages
### Service `zing_mp3.play_top100`: 
Play current top 100 on Zing mp3

**Service data**:

`entity_id:` media_player to play

`category`: 'pop', 'country', 'rock', 'dance', 'r&b'', 'rap', 'soundtrack',
                      'nhac tre', 'tru tinh', 'que huong', 'cach mang', 'rock viet', 'rap viet', 'dance viet'

`repeat`(Optional): true. Default: false

`shuffle`(Optional): true. Default: false

Example service Data
```
{
  "entity_id": "media_player.google_home_speaker"
  "category": "tru tinh",
  "repeat": false,
  "shuffle": true
}
```

### Service `zing_mp3.play`: 
Play specific song on zing mp3

**Service data**:

`entity_id:` media_player to play

`name`: song_name to play

Example service Data
```
{
  "entity_id": "media_player.google_home_speaker"
  "name": "happy new year"
}
```

# **Update the component**
The component will check for updates each time HA is restarted. When there is a new version, a Persistent Notification will appear.
Use the services `zing_mp3.check_updates` to manually check for updates and `zing_mp3.update_component` to start the automatic update.
