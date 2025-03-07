![UL Geography logo](../assets/images/GY4006_logo.png)

# 20: Saving your AOI buffer as a GeoJSON for export ```[B-grades and above]```
___
So far, you've imported, geoprocessed, and visualised vector data in QGIS to produce a map showing the rivers, lakes, and water level monitors within an area of interest; and you've imported, geoprocessed, and visualised raster data to show the topography of the land surface, and create flood risk maps for particular chosen ricer water level heights. 

Now that you have produced a map showing flood risk areas, you know *where* flooding might happen. Now, you need to consider *who* and *what* might be affected if this flooding happens. 

We'll look at the *what* first. You can use the base map to some extent here, simply looking at what features have been mapped in the flood risk areas. However, we can also get some additional data to help with that. One kind of data which can be really useful for this kind of analysis is satellite imagery. 

So, this is our next task - using QGIS to analyse raster data collected by remote sensing satellites. In particular, what we want to download or produce a visualisation which we can put our flood risk layers over, which might help us to understand what's in our flood risk area.  

We will be using raster data from the European Union’s Copernicus programme Sentinel satellites. Specifically, we will be using multispectral images taken by one of the Sentinel-2 satellites.

You will access this data through the [Copernicus Browser](https://browser.dataspace.copernicus.eu/). You'll need to register - but registration is free, and only takes a minute.

This site will give us access to years of satellite data, for the entire planet. Finding your area might be a bit tricky - but fortunately, we can upload a vector polygon to the Copernicus Browser to define the area of interest. The uploaded file needs to be in a particular format, so let's start by saving our area in that format.

## Processing the Data
___
In the Layers panel, right click on your AOI buffer layer, and choose ```Export > Save Features As```. In the *Save Vector Layer as* window, set the **Format** to ```GeoJSON``` (this is a version of the format that you downloaded the OPW monitors data in, it’s a very useful format for sharing geographic data), and set the **CRS** to ```Default CRS: EPSG: 4326 – WGS84```. Click the Browse **(…)** button beside **File Name**, and in the *Save Layer As* window, navigate to your GY4006 folder, give it an appropriate filename, and click **Save**. Back in the *Save Vector Layer as* window, uncheck ``Add saved file to map`` (we only need to save it, we don’t need a second version of the layer on the map) and click **OK**. 

Save the project before continuing.


___
[Previous](./19_vectorise_flood_map.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./21_sentinel_2.md)