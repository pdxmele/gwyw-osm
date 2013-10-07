#Converters to turn OSM data into other data types:

##Smaller stuff:

###GeoJSON:
* osm-and-geojson : http://aaronlidman.com/osm-and-geojson
* osm2geo: https://gist.github.com/tecoholic/1396990
* osmtogeojson: https://github.com/tyrasd/osmtogeojson

###Shapefile:
* http://wiki.openstreetmap.org/wiki/Shapefiles#Making_shapefiles_from_OpenStreetMap_data

###Various formats:
* QGIS (native support for 2.0+, plugin for earlier versions): After importing or downloading OSM data, select what you want and then do Save As… to select a new format/projection

##Bigger stuff (various formats):

* Osmium: http://wiki.openstreetmap.org/wiki/Osmium
* osm2pgsql: the standard for rendering full tilesets
  * http://wiki.openstreetmap.org/wiki/Osm2pgsql
  * http://manpages.ubuntu.com/manpages/lucid/man1/osm2pgsql.1.html
* osm2posgresql: http://wiki.openstreetmap.org/wiki/Osm2postgresql
* Imposm: http://wiki.openstreetmap.org/wiki/Imposm
* ogr2ogr (part of GDAL): http://www.gdal.org/ogr/drv_osm.html to GeoJSON or a variety of other formats
```
ogr2ogr -f GeoJSON points.json data.osm.pbf points
ogr2ogr -f GeoJSON lines.json data.osm.pbf lines
ogr2ogr -f GeoJSON multilinestrings.json data.osm.pbf multilinestrings
ogr2ogr -f GeoJSON multipolygons.json data.osm.pbf multipolygons
ogr2ogr -f GeoJSON other_relations.json data.osm.pbf other_relations
```

#Going the other direction:
* ogr2osm: http://wiki.openstreetmap.org/wiki/Ogr2osm
