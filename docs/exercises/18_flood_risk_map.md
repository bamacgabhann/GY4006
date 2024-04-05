![UL Geography logo](../assets/images/GY4006_logo.png)

# Creating a Flood Risk Map ```[C-grades and above]```
___
The DEM raster layer has a height value for every pixel - the height of the land surface. 

The water level(s) you’ve just got from the OPW, or calculated – that’s also a height value, for the water level in the river. 

Now you can create an inundation map, showing what areas would be flooded for a particular water level, if we simply check – which areas of the DEM are below that water level?

## Processing the Data
___
To do this we’re going to use a tool called the Raster Calculator. In QGIS, from the menu, choose ```Raster > Raster Calculator```. 

In the Raster Calculator window, we are going to define a formula to calculate a new raster layer which will be showing the areas where the 1% water level is higher than the height of the land surface.

The formula is really simple. In the Raster Calculator Expression box, first type the number of your chosen water level for your monitor. Then click the ‘greater than’ symbol ```>```. Then double click the DEM layer in the Raster Bands box. 

That’s it, that’s the formula. 

What this formula does is check, for each pixel of the DEM in your area, is that water level higher than the height of the land surface in the DEM? If the water level is higher, the formula will label that pixel with a boolean value of 1, for TRUE. If the water level is lower than the height value from the DEM, it will label that pixel with a boolean value of 0, for FALSE. So the new raster layer you produce from this will have pixels with values of either 1 or 0, with the areas covered by pixels with a value of 1 being the areas at risk from a flood at that water level.

One more quick thing to do here before we click OK: we need to set our save location. Click the Browse button beside Output layer, go to your GY4006 folder, type a filename e.g. ```floodrisk.tif```, and click Save. 

Click OK when ready. You should see the new ```floodrisk``` (or whatever name you chose) layer in the Layers panel, and in the map canvas you will see your area is now black and white.

Save the project before continuing.

## Second flood risk map ```[A-grades]```
___
Repeat this for your second water level to create your second flood risk raster layer, giving it a different filename.

Save the project before continuing.


___
[Previous](./17_water_levels.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next]()