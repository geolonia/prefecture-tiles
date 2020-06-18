# Prefecture Tiles

## Prerequisite

- tippeacanoe https://github.com/mapbox/tippecanoe
- mb-util https://github.com/mapbox/mbutil

### generate tiles

```shell
$ git clone https://github.com/geolonia/prefecture-tiles.git
$ cd prefecture-tiles
$ tippecanoe -o ./prefectures.mbtiles -Z3 -z7 --drop-densest-as-needed --no-tile-compression ./prefectures.geojson ./prefectural-capital.geojson
$ mb-util --image_format=pbf ./prefectures.mbtiles ./tiles
$ find ./tiles -name "*.pbf" -exec bash -c 'mv "$1" "${1%.pbf}".mvt' - '{}' \;
```
