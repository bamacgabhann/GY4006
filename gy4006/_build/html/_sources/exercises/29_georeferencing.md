![UL Geography logo](../assets/images/GY4006_logo.png)

# 29: Georeferencing ```[A-grades]```
___
You have added a lot of data to your map, of different kinds - vector point data, vector line data, vector polygon data, single-band raster data, and multi-band raster data, in formats including ESRI shapefiles, OGC geopackages, GeoJSONs, and GeoTIFFs.

These data types are hugely varied, but there's one thing they all have in common: they all have defined geometry. Whether in a raster transform, or in vector geometry attributes, they all have coordinate information to specify where the data should be displayed on the map.

You have also added one layer of data which *didn't* have that: the census data tables layer, which you added as an attribute-only table with no geometry. Of course, you were easily able to add geometry to this layer by joining the features to the census vector polygon layer. It's not that this attribute table didn't have geometry - it's just that the geometry information was stored in a different layer.

But what about times when you don't have a quick and easy Join which lets you add coordinate information to a layer without geometry? How do you add geometry information to a layer when you don't have the coordinate information ready and stored in another file?

This can be a common issue which you might come across if:

- you want to use a historic map,
- you want to use older satellite imagery captured on film,
- you have a printed map on which you've recorded data while doing fieldwork,
- you have a scanned image or screenshot of a map.

In all of these cases, you'll have a raster image with no coordinate information. So, how do you add it?

This is an issue you face right now - because while you have a pretty good map, it really is missing something. You have a base map and topography; you have the water features in the rivers and lakes; you have the locations of the monitors measuring the water levels in the rivers; you've generated flood risk maps to show what areas could be flooded at particular water levels; and you have satellite data from which you've made land use maps and census data from which you've made thematic maps to illustrate what and who would be affected by this flooding. What you *don't* have ia anything about what flooding has occurred in your area before now.

It would be really useful to have some data about past floods on your map. Previous flood occurrences would be useful data in itself - but even more than that, it would also be a good check on your flood risk areas. How does the record of previous flooding compare to your flood risk areas? Is all previous flooding within those areas, or has flooding happened in other parts of your area?

Fortunately, some data about previous flooding is available.

Unfortunately, it's only available as an online map, from which you can't download the data.

However, it is possible to take a screenshot of the online map. So how do we add the coordinate information? That's a process called *georeferencing*.

## Importing and Processing the Data
___
The OPW (from whom you obtained the water level monitors data) has a great website which shows the flood risk and previous floods in Ireland: [https://www.floodinfo.ie/map/floodmaps/](https://www.floodinfo.ie/map/floodmaps/). On the site, you can view a number of different layers. I do encourage you to look at the River Flood Extents – Present Day layer, to see how similar their flood risk maps are to the ones you produced. However, for the purposes of this exercise, I want you to turn off the River Flood Extents – Present Day and Coastal Flood Extents – Present Day layers, and turn on the ```Past Flood Events > Past Flood Event``` layer. This layer shows the locations of previous floods recorded by the OPW. As you can see, there are a lot.

Find and zoom into your area on this map, ensuring that the entirety of your AOI and buffer is visible on the screen. Take a screenshot (if you don’t know how, on a PC it’s usually press Function + Print Screen on the keyboard (Fn+PrtScr), and if it’s different you can easily google ‘how to screenshot’ to figure it out). Use an image editing program to crop the screenshot (cutting out the toolbars etc. so only the map is left; again, if you are not sure how to do this, Google it – there are plenty of guides online, and this can be done in built in programs like MS Paint).

Create a new subfolder called Georeferencing in your GY4006 folder, and save the cropped screenshot image there with the name ```Past Events```.

If we try to just open this image with QGIS as we did for the Sentinel-2 remote sensing imagery, it won’t work, because QGIS doesn’t know where to put it on the map. It has no coordinate data associated with it. The Sentinel-2 images had coordinate data saved in the image files, but this is just a picture. If we want to be able to use this in QGIS, we need to tell it where the image should go. We do that by *georeferencing* the image: selecting points on the image, and linking them to points on the base map. 

QGIS has a built-in georeferencing tool. To open it, from the menu choose ```Layer > Georeferencer```. When the Georeferencer window opens, from the menu choose ```File > Open Raster```, browse to your ```GY4006``` / ```Georeferencing``` folder to find your ```Past Events``` image, and open it. 

The next step is the main step – setting what we call control points. These are points we identify on the image and also in the main map canvas in QGIS – so that QGIS knows where they are. We need a minimum of six control points – and the more the better.

Control points have to be as accurate as possible, so it’s no good to just drop one in the centre of a town and hope it’s close enough. We need to be precise. Maps with a coastline can be easier to georeference, because coastlines have enough unique shapes which can be found on both base maps and the image being georeferenced. A few of you will have coastlines of lakes and can use that, but most of you won’t. For a map like this, perhaps the best control points are road junctions.

The roads are visible on the image, and since you have a base map Google Road or OpenStreetMap layer, they’re on your map as well. You can use these to add control points. Use the Zoom tool to zoom in to an easily locatable road junction in the screenshot image - one that you’ll be able to find on your map in QGIS. Select the *Add Point* tool from the toolbar (looks like Earth with a red circle, and a yellow box at the corner), and use it click the centre of the junction. 

A popup will appear asking you to enter map coordinates. Click the *From Map Canvas* button. This will minimize the Georeferencer window, letting you see the QGIS map canvas. Zoom to the same junction, and click on it. (How do you find the same junction? Look for matching patterns in the roads. Pick junctions that will be easy to find.)

The Georeferencer window will reopen (if you need to reopen it sooner, by the way, it minimizes to the bottom left corner of QGIS), showing the coordinates of the point you clicked in QGIS. Click OK to confirm the point. You will see a red dot appear at the point on the image, and a row will be added to the GCP table panel (GCP = Ground Control Point), with details of the coordinates of the point.

That’s your first control point added! Now do at least 5 more. For best results, spread them out as much as possible over the image, trying to add control points as close as possible to each corner and the middle of each side of the image, as well as a couple around the middle. The more control points you add, the more accurate the result will be.

Once you’re happy that you have enough points, it’s time for QGIS to figure out how to match the image to the coordinate system – so the next thing we have to do is tell QGIS which coordinate system we want it to use. Click the ```Transformation Settings``` (looks like a yellow cogwheel) button to open the options. 

If you click the **Transformation Type** dropdown, you'll see a few different options. These vary depending on how much the image needs to be changed to fit to the map. If you are trying to georeference a printed map which is already in the coordinate reference system you want, it only needs to be put the the right place; but if your image is in a different coordinate reference system, it will need a much more complex mathematical transformation to ensure that all parts of the image are transformed to the right location. If you want to know more, check out the QGIS documentation here:  [QGIS Available Transformation algorithms](https://docs.qgis.org/3.34/en/docs/user_manual/working_with_raster/georeferencer.html#available-transformation-algorithms). For now, you can change the **Transformation Type** to ```Polynomial 2```. 

Set the **Resampling method** to ```Nearest Neighbour```, and **Target CRS** to ```EPSG:2157 IRENET95 / Irish Transverse Mercator```. Click the Browse button beside **Output raster**, navigate to your *GY4006/Georeferencing* folder, and type a filename ```PastEvents_modified```; ensure **Save as type** is set to TIF files, and click Save.

Select **Save GCP points**, and select **Load in project when done** to automatically add the georeferenced raster to QGIS. Now click OK to close the Transformation Settings window; and click the **Start Georeferencing** (blue triangle) tool to georeference the image.

Once you get the message to say georeferencing has finished, return to the main QGIS window. You should see the new *PastEvents_modified* layer in the Layers panel. Move the layer so that it’s below your AOI, Buffer, Rivers, Lakes, Water Level Monitors, and Flood Risk layers, but above everything else.

In the map canvas, zoom in to the edges of the georeferenced image to check if it matches the base map. Check all the way around the edges - see if features like roads and rivers line up from the georeferenced map to the base map. Toggle the visibility of the georeferenced map on and off so that you can see how the georeferenced map compares to the base map underneath. If the georeferenced map lines up well - great! Much more likely, there will be some areas where the match is not exact; it's rare that the transformation is perfect first try. 

You'll get another guide from looking at the control points: these will be marked by red dots, with a red line extending away from them, showing the difference between where you placed them, and where the transformation has calculated them. If any of the lines are particularly long, it's possible the point has been placed in the wrong position. 

You can return to the georeferencer, and delete control points with large error lines, and add more control points around areas where the transformation could be improved. Keep adding or replacing points until the transformation has the georeferenced image matching as close as possible to the base map. 

When you're satisfied with the match, save the project before continuing.


___
[Previous](./28_thematic_map.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./30_digitising.md)