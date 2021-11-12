# 🌲 ski-trails 🌲

Parses and displays data on ski trails from various sources. These sources are written as "plugins". 

Currently we have plugins for:
- Vail Resorts
- Arapahoe Basin 


## CLI Usage
```
➜ ./trails --open

  RESORT         AREA                TRAIL                 DIFFICULTY  STATUS

  Keystone       Dercum Mountain     Endeavor              ●           OPEN
  Keystone       Dercum Mountain     Schoolmarm            ●           OPEN
  Arapaho Basin  Front Side Terrain  Lower Mountain Blues  ■           OPEN
  Arapaho Basin  Front Side Terrain  High Noon             ■           OPEN
```

## Help
```
./trails --help
usage: trails [-h] [-o]

Get Ski Trail Status

optional arguments:
  -h, --help  show this help message and exit
  -o, --open  Open trails only

By default, show all trails from config.yaml
```

## Config
The configuration file adds or removes resorts you want to get trail info for. Currently the vail plugin can support any vail resort (you could add Park City for example as they are owned by vail) and the abasin plugin adds Arapahoe Basin trails.

```
➜ cat config.yaml
resorts:
- name: Keystone
  urlBase: keystoneresort.com
  plugin: vail
- name: Vail
  urlBase: vail.com
  plugin: vail
- name: Breckenridge
  urlBase: breckenridge.com
  plugin: vail
- name: Beaver Creek
  urlBase: beavercreek.com
  plugin: vail
- name: Arapahoe Basin
  urlBase: arapahoebasin.com
  plugin: abasin
```
