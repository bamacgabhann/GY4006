![UL Geography logo](../assets/images/GY4006_logo.png)

# 15: Clipping the DEM ```[C-grades and above]```
___

Because vector files contain co-ordinates for points, lines, or polygons, they can easily be redrawn at any scale level. For example, the vector shapefile for the OPW water level monitors, which you downloaded last week, is smaller than 1Mb, despite the fact that it contains data for all of Ireland. 

Raster files are image files, made up of pixels. In a photograph, the raster pixels contain colour information. The DEM you have just added to the project is a raster image – but rather than colour information, each pixel of the DEM is a height value in metres. These are large files, because the DEM literally contains a height value for every single pixel in the image – and in this DEM, each pixel covers an area 25m along each side. There’s a lot of 25m x 25m squares in Ireland. This means there are a lot of pixels, which makes for a very big file.

Much as for the OPW water level monitors, the lakes, and the rivers, we don’t need all this. You clipped the vector data to your AOI or buffer. We can do exactly the same for the DEM.

## Processing the Data
___

From the menu, choose ```Raster > Extraction > Clip Raster by Mask Layer```.

This tool allows us to extract (clip) part of a raster layer which is within the extent of another layer (using it as a mask layer). In this case, we will extract the parts of the DEM which are within your AOI ```[C-grades]``` or buffer ```[B-grades and above]``` layer.

In the Clip Raster by Mask Layer window, choose ```eu_dem_v11_Ireland``` as the Input layer, and your AOI ```[C-grades]``` or buffer ```[B-grades and above]``` layer as the mask layer. Set ```Assign a specified nodata value to output bands [optional]``` to ```-999```. Make sure that ```Match the extent of the clipped raster to the extent of the mask layer``` is selected. Scroll down to find ```Clipped (mask)```, click the Browse [...] button beside it, and choose ```Save to file```. In the Save File window, navigate to your GY4006 folder, type a filename ```DEM.tif```, and click Save. Now click Run, and close the window when it’s done.

You should now see a new layer called DEM in the Layers panel. You can now remove the ```eu_dem_v11_Ireland``` layer.

Save the project before continuing.


___
[Previous](./14_Adding_DEM.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./16_DEM_hillshade.md)