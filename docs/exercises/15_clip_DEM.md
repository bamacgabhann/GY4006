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

### IF YOU GET AN ERROR

If trying this results in this error:
```
GDAL command output:
ERROR 1: PROJ: laea Invalid latitude
```

This appears to be a consequence of a bug which has caused a problem with the CRS of the AOI/buffer layer you are trying to use to clip the raster. 

If you get this error, first right click on your AOI/buffer layer (the layer you are using to clip the raster) in the Layers Panel, and choose *Layer CRS*. 

If the top option is ```Undefined geographic SRS``` or anything other than ```EPSG: 2157 - IRENET95 / Irish Transverse Mercator``` then choose *Set to EPSG:2157* if that is an option; or if not, choose *Set Layer CRS*. In the Set Layer CRS window, ensure the dropdown menu at the top is set to *Predefined CRS*; then type ```2157``` in the **Filter** search box. You should see ```Projected > Transverse Mercator > IRENET95 / Irish Transverse Mercator EPSG: 2157``` in the list of Predefined Coordinate Reference systems below (you may have to expand the headings by clicking the arrows): select this and click OK.

Now if you right click on this layer in the Layers Panel, and choose *Layer CRS*, it should list ```EPSG: 2157 - IRENET95 / Irish Transverse Mercator```.

Once this is correct, right click on the layer and choose ```Export > Save Features As```, and re-save the layer with a different file name. Keep the format as geopackage; click the browse button beside File Name to open the save file window, navigate to your GY4006 folder, and give it a new file name: it doesn't matter what, as long as it's different, e.g. buffer2. Click Save to return to the *Save Vector Layer As* window, ensure *Add saved file to map* is selected, and click OK. You should see the new version appear in the Layers panel.

Right click on this layer in the Layers Panel, and choose *Layer CRS* to confirm that it lists ```EPSG: 2157 - IRENET95 / Irish Transverse Mercator```.

Now, use this new layer as the *mask layer* in *Clip Raster by Mask Layer*.

Save the project before continuing.


___
[Previous](./14_Adding_DEM.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./16_DEM_hillshade.md)