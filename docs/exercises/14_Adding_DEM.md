![UL Geography logo](../assets/images/GY4006_logo.png)

# Task Title ```[C-grades and above]```

You should now have a map of your AOI with some essential data - the rivers, the lakes, and the water level monitors. Your getting closer to doing some analysis, but we need to add a bit more data first.

Flooding is when the height of the water level rises up to be above the height of the land surface. So if we want to know where might be flooded at particular water levels, we need to know the height of the land surface. We can get this from a digital elevation model, or DEM. 

A DEM is a raster dataset, with each pixel containing a value for the height of the land surface in the area covered by the pixel. 

## Importing Processing Visualising the Data

Before going straight to downloading the DEM, a note of caution that it's a *big* file. The resolution of the DEM is about 30m - meaning each pixel has sides around 25m x 25m. Imagine how many 25m x 25m squares there are in Ireland - that's how many pixels the DEM has. Storing all that data takes up a lot of memory - around 1Gb. 

You will find a link to download the file on Brightspace: download it, and move it to your GY4006 folder. Then in the QGIS Browser panel, find the file, which is called ```eu_dem_v11_Ireland.tif```. Click and drag it into the map canvas to add it to the project.

You’ll see the data in the map canvas – by default, it displays the GEOTIFF as a greyscale image, with the darker pixels indicating a lower elevation, and the lighter pixels indicating a higher elevation. You’ll also see the new layers in the map canvas, with a pixelated square symbol indicating raster data. Notice that this symbol also appears beside the Google Road layer, which is also raster data.

You might also notice that you can’t see some of the other data in the map canvas now – the DEM data is covering the features. This would happen if the DEM layer is above them in the Layers panel. So, in the Layers panel, click and drag the DEM layer to the bottom of the list. You should now see all the vector data on top of the raster.

Save the project before continuing.

___
[Previous](./13_monitors_symbology.md) | [Next](./15_clip_DEM.md)