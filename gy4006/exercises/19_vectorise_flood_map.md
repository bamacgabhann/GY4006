![UL Geography logo](../assets/images/GY4006_logo.png)

# 19: Vectorise the flood risk map(s) ```[B-grades and above]```
___
We can edit the raster layer symbology to hide the areas in black, but we have a second option here – convert the raster to a vector layer. We can do this because there’s only two values here, 1 and 0, so it’s relatively easy to record the vector co-ordinates of the shapes of the 1 and 0 (black and white) areas. Let’s do this.

## Processing the Data
___
From the menu, choose ```Raster > Conversion > Polygonize (Raster to Vector)```.

In the Polygonize (Raster to Vector) window, choose your flood risk map as the Input layer, and type ```flooded``` in the Name of the field to create. Then click Run, and click Close when it’s done. 

You will see a new layer, ```Vectorized``` (a scratch layer) in the Layers panel, and see the new layer in the map canvas as a single colour (if you don’t see it, it may be under the flood risk raster layer; click the checkbox beside the raster in the Layers panel to make it invisible). It’s covering the whole area because it’s showing the same colour for areas which are 0 and 1. We don’t need the 0 areas, so let’s extract the 1 areas. 

We will do this in the same way that you selected your individual AOI – Select Features by Value. Click the Select Features by Value button in the toolbar. In the ```flooded``` field, type 1, and click Select Features.

Click Close to close the Select Features window. We now have the areas at risk of flooding for this water level selected – what we want now is to make these a new layer, and we’re going to do it the simplest way possible: copy and paste. From the menu, choose ```Edit > Copy Features```. Then from the menu again, choose ```Edit > Paste Features As > Temporary Scratch Layer```.

You’ll get a dialog box asking for a layer name: you can leave it as the default name ```Pasted```. You should see this scratch layer appear in the Layers panel. You might not see it clearly on the map though, so turn off the visibility of the flood risk raster layer and the ```Vectorized``` layer by clicking the checkboxes beside them in the Layers panel. You should now see the ```Pasted``` layer more clearly. It should have some coloured areas: these are the areas where your chosen water level is higher than the land surface height from the DEM.

Now, the new ```Pasted``` layer has multiple polygons. For what we’re going to do with it eventually, we need it to be all one polygon. Normally, we can do this with ```Vector > Geoprocessing Tools > Dissolve```. If you want, you can try this – just select ```Pasted``` as the Input layer. However, experience tells me that if you try this, because of how this file was made there’s a very good chance you’ll get an error, with QGIS saying the layer has invalid geometry. So first, we’re going to make sure that we fix any invalid geometry.

From the menu, choose ```Processing > Toolbox```. You’ll see the processing toolbox panel open on the right side of the screen. Find ```Vector Geometry```, and click the arrow beside it to expand. Scroll down and find ```Fix Geometries```. Select ```Pasted``` as the Input layer, and click ```Run```. Click Close when done. You’ll see a new layer in the Layers panel called ```Fixed geometries```.

Now, you can run a dissolve – from the menu, choose ```Vector > Geoprocessing tools > Dissolve```. Select ```Fixed geometries``` as the Input layer, and click Run. Click Close when done. You’ll see a new scratch layer ```Dissolved``` in the Layers panel.

This scratch layer is our inundation map, so we want to save it as a permanent layer. Right click on the ```Dissolved``` layer, and choose ```Export > Save Features As```. Change Format to ```GeoPackage```. Click the Browse button beside File name, go to your GY4006 folder, type a File Name ```Flood Risk```, and click Save. Back in the Save Vector Layer As window, type a Layer name ```Annual Max Flood``` ```[B-grades and A2-grade]``` or ```100-year flood``` ```[A1-grade]```, or a different name which indicates the significance of the water level for this flood risk map. Ensure the CRS is set to ```Project CRS: EPSG:2157 – IRENET95 / Irish Transverse Mercator```. Ensure ```Add saved file to map``` is selected. When you're ready, click OK to save the layer - you should see it appear in the Layers panel.

Now, we have a lot of scratch layers which we don’t need anymore. Remove the layers ```Dissolved```, ```Fixed geometries```, ```Pasted```, ```Vectorized```, and the flood risk raster layer (in the Layers panel, right click and choose Remove Layer; you can hold the control key and click on layers to select multiple layers, and remove them all at once).

Finally, open the Symbology for the new flood risk vector layer (in the Layers panel, right click and choose Properties, then Symbology), and change the colour to something appropriate; maybe adjusting the transparency, so you can see what’s underneath the flood risk area.

You've just made a flood risk map! Save the project before continuing.

## Vectorise your second flood risk map ```[A-grades]```

Repeat the above process for your second flood risk raster. When you come to saving the final vector layer, save it to the same geopackage file called ```Flood Risk```, but with a different layer name (again, choose a layer name which indicates the significance of the chosen water level for this flood risk map). Give it a slightly different colour, again with a decent level of transparency, so that both flood risk raster layers can be seen, but it's still possible to see what's on the map under them. 

Again, save the project before continuing.

## Going Further
___
What you've done in the last couple of steps is essentially a version of what the OPW and other organisations would be doing in order to create flood risk maps. It is simplified - but not as much as you might think. There's a lot more can be done for hydrological analysis in QGIS, particularly with DEMs - analysing slope angles and producing maps to show how water falling as precipitation on any place would travel into and through the river system. If you want to know more, I recommend the book ```QGIS for Hydrological Applications``` by Hans van der Kwast and Kurt Menke, which you can find in the library. THere's also a little in the QGIS manual showing you how to use some of the tools.

More info: [QGIS Training Manual / 17. The QGIS processing guide / 17.16. Hydrological analysis](https://docs.qgis.org/3.34/en/docs/training_manual/processing/hydro.html)

___
[Previous](./18_flood_risk_map.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./20_aoi_geojson.md)