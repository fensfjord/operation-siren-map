# operation-siren-map
Geospatial data for Operation Siren maps.


## About ##
This repository contains the files I used to create my [Operation Siren map](https://i.redd.it/in6lfrlpu1l61.jpg "Operation Siren map"). The main dataset is digitised versions of the Operation Siren zones in shapefile and geopackage formats, based on the work of [Scipio90001](https://www.reddit.com/user/Scipio90001 "Scipio90001") on reddit.

I have also included the Digital Elevation Model (DEM) data which I used to produce the background image. This is derived from Tom Patterson's [Blue Earth Bathymetry](http://www.shadedrelief.com/blue-earth/ "Blue Earth Bathymetry").

## Methodology ##

### Projection ###

All data in this repository uses EPSG 3395 (WGS 84 World Mercator) coordinates, as this projection was visually closest to the original Operation Siren map in Azur Lane, and provided the best fit when georeferencing Scipio90001's map.

### Zones ###

All zones were digitised in QGIS. I followed the original zone boundaries as closely as possible, but around coastlines, I have used the Natural Earth Data 1:50m [coastline vector data](https://www.naturalearthdata.com/downloads/50m-physical-vectors/ "coastline vector data") for reference due to some misfit between the in-game and real-world coastline locations. 

I have included two shapefiles for zones:
* Operation Siren Zones - contains shapefiles for each zone. Zone names and corrosion levels are included as attributes, based on the in-game data.
* Operation Siren Superzones - outlines for each sector without sub-divisions, e.g. West Continental Shelf, Caribbean Sea

As of creating these files, the central zones for the NA Ocean were not in-game, and are only detailed on the [Azur Lane wiki](https://azurlane.koumakan.jp/List_of_Operation_Siren_Zones "Azur Lane wiki"). For digitisation purposes, in both Zones and Superzones shapefiles I have treated the NA Ocean Depths as a single zone with a corrosion value of 6, but note that the sub-zones of this sector have corrosion values of both 5 and 6. I may update this in a future release if further data becomes available.

The validity of both shapefiles has been checked with the QGIS GEOS method, so they should be suitable for further geoprocessing operations if desired.

### Ports ###

I have included a very simple shapefile of approximate point locations for the current named ports in Operation Siren, including their alignment (Azur Lane/Crimson Axis). Their locations are not intended to be authoritative, but as a useful resource for creating maps of Operation Siren.

### Digital Elevation Model ###

The topography and bathymetry data was clipped from the Blue Earth Bathymetry grid, and reprojected into EPSG 3395 coordinates using GDAL and bicubic spline interpolation. Due to the effects of reprojection and interpolation, the absolute elevation values in the model may not be accurate (and should therefore not be considered authoritative) (Not that any information about Azur Lane should really be considered authoritative).

## Licence ## 

This repository is provided under a Creative Commons Zero v1.0 Universal licence, and therefore is available for you to do whatever you like with, without requiring any attribution. If you do use it, it would be great to hear about what you've made, and if you have any questions about the data, please ask!
