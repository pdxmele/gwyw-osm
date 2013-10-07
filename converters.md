##Converters to turn .osm data into other data types:

###Smaller datasets:

####To GeoJSON:
* osm-and-geojson : an easy web-based tool where you just paste in your .osm file and click a button
  * http://aaronlidman.com/osm-and-geojson
* osm2geo: JavaScript that you can add to a webpage to make the browser do the work
  * https://gist.github.com/tecoholic/1396990
* osmtogeojson: another tool written with JavaScript, can be used as a NodeJS library or a script on a page
  * https://github.com/tyrasd/osmtogeojson

####To Shapefile:
* http://wiki.openstreetmap.org/wiki/Shapefiles#Making_shapefiles_from_OpenStreetMap_data
* OSMLib (Ruby): http://osmlib.rubyforge.org/

####To various formats, including GeoJSON and Shapefile:
* QGIS: native support for 2.0+, plugin for earlier versions
  * After importing or downloading OSM data, select the features you want and then do Save As… to select a new format and/or projection

###Larger datasets (to various formats):

_Note: most of these require using the command line. If you're not used to that, don't be afraid! It can save you a lot of time!_

####To various formats:
* Osmium: built with C++ and JavaScript, powers a number of other tools
  * http://wiki.openstreetmap.org/wiki/Osmium
* ogr2ogr (part of GDAL): convert large files to GeoJSON or a variety of other formats
  * http://www.gdal.org/ogr/drv_osm.html
  * Do each geometry type separately for best results:

```
ogr2ogr -f GeoJSON points.json data.osm.pbf points
ogr2ogr -f GeoJSON lines.json data.osm.pbf lines
ogr2ogr -f GeoJSON multilinestrings.json data.osm.pbf multilinestrings
ogr2ogr -f GeoJSON multipolygons.json data.osm.pbf multipolygons
ogr2ogr -f GeoJSON other_relations.json data.osm.pbf other_relations
```

####To PostGIS:

* osm2pgsql: the standard for rendering full tilesets with Mapnik
  * http://wiki.openstreetmap.org/wiki/Osm2pgsql
  * http://manpages.ubuntu.com/manpages/lucid/man1/osm2pgsql.1.html
* Imposm: Python-powered and optimized for visualization
  * http://wiki.openstreetmap.org/wiki/Imposm
* osm2posgresql: http://wiki.openstreetmap.org/wiki/Osm2postgresql

#### After it's in PostGIS:
* TileMill and QGIS can use PostGIS tables directly
* Built-in pgsql2shp: http://manpages.ubuntu.com/manpages/lucid/man1/pgsql2shp.1.html
* Built-in ST_AsGeoJSON function: http://postgis.net/docs/ST_AsGeoJSON.html
* ogr2ogr: http://www.gdal.org/ogr2ogr.html

###Going the other direction:
* ogr2osm: http://wiki.openstreetmap.org/wiki/Ogr2osm
