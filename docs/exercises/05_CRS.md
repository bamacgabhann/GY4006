![UL Geography logo](../assets/images/GY4006_logo.png)

# 05: Coordinate Reference Systems in QGIS

The main topic of the first GIS lecture was different map projections and coordinate reference systems (and particularly introducing the example of the Irish Grid and ITM). The main point is that the Earth is not flat, it’s round, and it is not easy to show a round surface as a flat map. There’s several different ways of doing it, and they produce results which can be very different from each other. 

There’s also many different coordinate systems: the global GNSS (GPS) system uses latitude and longitude, but those are measured in degrees, and how long is a degree? They’re tricky to use locally if you’re interested in calculating distances, areas etc. Instead, many countries have defined their own national grids, usually with coordinates measured in metres – which is much more intuitive.

Now is the point we have to consider this in QGIS. Ideally, you want your map to be using one system, and all your layers to have coordinates using the same system. 

Hover the cursor over the water level monitors layer, in the Layers panel. You’ll see a popup appear, which contains the text ```OPW (Point – EPSG:4326)``` and the location of the file.

*Point* tells you that the file contains vector point data. EPSG codes are codes for coordinate reference systems (CRS) – so the data for this layer is saved in coordinate reference system EPSG:4326. This is the WGS84 global latitude-longitude coordinate reference system, which is used by the GNSS (GPS) system.

Now hover the cursor over ```WATER_RivNetRoutes``` in the Layers panel. You’ll see the popup with ```WATER_RivNetRoutes (MultiLineString – EPSG:29902)```. *MultiLineString* tells you this is vector line data, with multiple lines. This CRS is the old 1965 Irish Grid – why the EPA is still using this, I have no idea; someone needs to tell them the 90s called and want their coordinate system back.

Finally, if you hover over ```GY4006 Areas``` in the Layers panel, the popup will be ```GY4006 Areas (MultiPolygon – EPSG:2157)```. *MultiPolygon* should be obvious now – vector polygons, with multiple polygons. This CRS is the current Irish Transverse Mercator (ITM) coordinate system which is the current standard system for mapping in Ireland. This is the CRS we want to use throughout the project.

Now look at the bottom right corner of the screen – you should see ```EPSG:29902``` listed there. This is the Project CRS – the coordinate reference system used in the Map Canvas. It’s currently set to the 1965 Irish grid, because that’s the CRS used by the first data we added. 

The Layer CRS is what projection the file is saved in. The Project CRS is how the map is drawn in the map canvas. 

Since we’re working on data just from Ireland, the CRS we want to use is ITM, Irish Transverse Mercator, ```EPSG:2157```. This is easy to do, since we have a layer using ITM. Set the project CRS from GY4006 Areas in the Layers panel. Ireland will be a bit zoomed out now, so right click on the rivers layer, and choose Zoom to Layer to zoom back in.

You may noticed that when changing the project CRS, although the data looks different, the relative positions of all the different data stays the same. This is because QGIS does something called projecting on the fly – if data is imported in a CRS different to the project CRS, it reprojects it to the project CRS for display on the screen. This is fine for just looking at data. However, it’s really intensive, so if your computer seems to be getting slower, that’s probably why. For any data processing, we would ideally have to reproject (resave) all the data into one CRS. We won’t do this just yet, but will be doing some of that later.

Save the project before continuing.


___
[Previous](./04_Adding_basemap.md) | [Next](./06_lake_symbology.md)