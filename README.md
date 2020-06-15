# Prefecture Tiles

## Prerequisite

- tippeacanoe https://github.com/mapbox/tippecanoe
- mb-util https://github.com/mapbox/mbutil

### generate tiles

```shell
$ git clone https://github.com/geolonia/prefecture-tiles.git
$ cd prefecture-tiles
$ tippecanoe -o ./data/prefectures.mbtiles -zg --drop-densest-as-needed --no-tile-compression ./data/prefectures.geojson -Z5 -z7
$ mb-util --image_format=pbf ./data/prefectures.mbtiles ./docs
$ find ./docs -name "*.pbf" -exec bash -c 'mv "$1" "${1%.pbf}".mvt' - '{}' \;
```
