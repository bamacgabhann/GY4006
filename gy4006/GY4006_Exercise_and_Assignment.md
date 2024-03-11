<img src="https://raw.githubusercontent.com/bamacgabhann/GY4006/main/GY4006_logo.png" align=center alt="UL Geography logo"/>

<h1>GY4006 GIS Exercise / Assignment</h1>

At the start of the module, you were given a Research Question plus Aims and Objectives:

**Research Question**
What vulnerabilities to fluvial flooding exist in Ireland?

**Aims**
To inform future flood hazard mitigation planning

**Objectives**
What is people’s experience of fluvial flooding in Ireland?  
Is there a socioeconomic bias to who is vulnerable to fluvial flooding in Ireland?  
When is fluvial flooding most likely to occur in Ireland?  
Where is fluvial flooding most likely to occur in Ireland, and what is vulnerable there?  

You have addressed some of this in the survey task; we can now address the remainder through some mapping.

You will be assigned an individual area to work on. Everyone will be undertaking the same mapping, but on your own areas. So, you should be able to help each other out.

In order to address your objectives and help to answer the research questions, you're going to make some maps of your area - and analyse some of that map data. 

THe point of this exercise - which will ultimately produce a portfolio of maps for your second assessment - is to introduce you to geospatial analysis, to show you some of what's possible using geospatial analysis, and to show you that you can do some geospatial analysis. Now, I understand that not everyone has the same targets in college - some of you want to get a top grade, while others might just be looking to get a C and pass. That's fine and entirely up to you - and so the way I've constructed this exercise / assessment breaks it down into different levels of tasks depending on what grade you are aiming to achieve.

You should by now have gone through the 10 Notebooks, and have some idea of the difference between vector Point, Line, and Polygon data, attribute data, and raster data. You should also have some idea of vector and raster geoprocessing, and of the potential for changing the symbology of the data, i.e. how the data is visualised.

To get a passing grade in the module, you will have to use all of these to some extent - and to get a B-grade or A-grade, you'll have to go into greater depth or detail.

<h3>C-grade (40-54%) and above</h3>

**Data Import**
*Vector Point data* - Water level monitors
*Vector Line data* - Rivers
*Vector Polygon data* - Lakes
*Vector Polygon data* - Your assigned area
*Vector Polygon data* - Census Small Areas

*Attribute data* - Census Small Areas data tables

*Raster data* - Digital Elevation Model

*Tile data* - OpenStreetMap or Google Maps base map

**Data Processing**
*Vector Geoprocessing* - Clip other data to your area
*Attribute Geoprocessing* - Join the census polygons to the census data tables
*Raster Geoprocessing* - Create a flood risk map using the DEM and river water level data

**Data Visualisation**
*Vector Symbology* - adjust the water level monitors, rivers, lakes, and your area to display appropriately
*Raster Symbology* - Display the digital elevation model as a hillshade
*Tile Symbology* - Overlay the tiles on the hillshaded DEM
*Attribute Symbology* - Create a thematic map from the census data, using graduated or categorised symbology on an attribute

**Maps to submit**
A map showing the water level monitors, rivers, lakes, and your area over the tile basemap overlaying the hillshaded DEM
A copy of this map showing the flood risk map you created
A map showing the water level monitors, rivers, lakes, and your area over your census thematic map

All maps must have (1) North arrow, (2) scale bar, (3) title, and (4) legend.

**Report to submit**
A report outlining where, what, and who is vulnerable to flooding (using the maps to answer the objectives).

<h3>B-grade (55-69%) and above</h3>

Complete all of the C-grade level tasks, plus:

**Data Import**
*Raster data* - Multispectral satellite imagery processed in the Copernicus Browser (e.g. NDVI, NDMI)

**Data Processing**
*Vector Geoprocessing* - Create a buffer around your area to use in clipping other data
*Attribute Geoprocessing* - Create a new attribute in the census data from existing attributes using the Field Calculator
*Raster Geoprocessing* - Create additional flood risk map using the DEM and river water level data, for different water levels; vectorise the flood risk areas

**Data Visualisation**
*Vector Symbology* - Adjust the symbology of ALL vector features, including river symbology by stream order
*Attribute Symbology* - Your census thematic map should be based on the new attribute you created

**Maps to submit**
An additional map showing the water level monitors, rivers, lakes, flood risk zones, and your area over the multispectral imagery - with two maps (over NDMI and NDVI) on a single page. 

All maps must have (1) North arrow, (2) scale bar, (3) title, and (4) legend.


<h3>A2-grade (70-79%) and above</h3>

Complete all of the C-grade and B-grade level tasks, plus:

**Data Import**
*Raster data* - Multispectral satellite imagery (MSI) individual L2A bands

**Data Processing**
*Attribute Geoprocessing* - Create a second new attribute in the census data from existing attributes using the Field Calculator
*Raster Geoprocessing* - K-means clustering of MSI L2A bands to produce a land use map
*Raster Geoprocessing* - Georeference a map of past floods in your area/buffer
*Vector Geoprocessing* - Digitise the georeferenced map 

**Data Visualisation**
*Vector Symbology* - Customise the symbology of the digitised features and the land use clusters
*Attribute Symbology* - Your census thematic map should be based on the new attribute you created

**Maps to submit**
Past Floods digitised elements should be shown on all maps
An additional map showing the water level monitors, rivers, lakes, flood risk zones, and your area over your land use map
Census map should show both thematic maps side by side

All maps must have (1) North arrow, (2) scale bar, (3) title, and (4) legend.


<h3>A1-grade (80%+)</h3>

Complete all of the C-grade and B-grade and A2-grade level tasks at an excellent level, plus:

Flood risk maps should be created by exceedance probability
Import and appropriately display vector features for roads etc. from OpenStreetMap or other sources
Additional self-directed tasks e.g. supervised learning for land use, catchment analysis, or similar

**Maps to submit**
Maps should contain additional elements; extra maps may be submitted if warranted.

All maps must have (1) North arrow, (2) scale bar, (3) title, and (4) legend.
