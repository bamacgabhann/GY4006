![UL Geography logo](../assets/images/GY4006_logo.png)

# 22: Visualising Sentinel-2 Imagery in QGIS ```[A-grades]```
___
Downloading visualisations from the Copernicus Browser is fine, but there's two big drawbacks. First, you have no control over the colour scale etc. when you bring that into QGIS - so if you want to change anything, you have to go back to the Copernicus Hub and recreate it, modifying the colour scale, and download it again. Second, because QGIS has no control over the colour scale, it can't put it in the legend. It's also not possible to do anything further with the data - again you would have to go back to the Copernicus Hub, do what you want, and download the result.

Having the individual bands, as you do, means you have that much more control, and can do much more with the data, if you need to.

## Processing and Visualising the Data
___
Go down the list of imported TIFFs in the Layers panel, clicking to untick the checkboxes as you go down, just to see what each of them look like. You’ll see that all the individual band images are greyscale – they each just have a single channel. If I was you, at this point, I would rename all the layers to make them easier to distinguish – you don’t need the full ```2022-08-13-00_00_2022-08-13-23_59_Sentinel-2_L2A_``` (or whatever date yours is from) part on each. 

You should notice two other things going down the list. First, that some of the images are fuzzier than others. This is because for Sentinel-2 data, ```B02```, ```B03```, ```B04```, and ```B08``` have a spatial resolution of approx. 10m per pixel; for ```B05```, ```B06```, ```B07```, ```B8A```, ```B11```, and ```B12```, it’s around 20m per pixel, and for ```B01```, ```B09```, and ```B10```, it’s around 60m per pixel. 

Speaking of ```B10```, the second thing you should have noticed is that there no ```B10``` in what you downloaded. This is because you’re working with L2A data – bottom of atmosphere reflectance. ```B10``` is used for looking at clouds, which of course tend to be above the bottom of the atmosphere – hence its absence from L2A datasets. If you were working in L1C, ```B10``` would be there, although still not much use for land cover mapping.

### Build Virtual Raster
To create a visualisation like false colour or SWIR in QGIS, we need QGIS to show different bands in each of the red, green, and blue channels. However, all the bands are currently in the project as separate images – so, first, we need to combine them. We can combine all of the layers into what’s called a virtual raster – letting QGIS consider all the individual layers as different parts of a single combined image. From the menu, choose ```Raster > Miscellaneous > Build Virtual Raster```.

In the *Build Virtual Raster* window, click the Browse button beside Input Layers to open the Multiple Selection window. Click the checkbox beside each of the Band layers to include them, then click OK. 

Back in the Build Virtual Raster window, change Resolution from Average to Highest, and ensure Place each input file into a separate band is selected. These settings mean that the combined raster will have the same resolution as the highest resolution input raster, and each of the raster input layers will be treated as a separate band of the combined raster, rather than averaging the data. 

Click the Browse button, and choose Save to file. In the Save file window, browse to your Sentinel 2 folder, and type a filename Sentinel-2. Click Save to close the Save File window, then back in the Build Virtual Raster window, click Run. When it’s done, click Close. You should see a new layer, Sentinel-2, in your Layers panel.

### Simple Visualisations in QGIS
Open Symbology for the Sentinel-2 layer. Ensure Render Type is set to Multiband color, and set Red band to Band 4, Green band to Band 3, and Blue band to Band 2 – that’s natural red, green, and blue bands as red, green, and blue, to create a natural colour image. Set Contrast Enhancement to Stretch to MinMax – this setting maximizes the range of colours displayed in each band to the range of the data. Click the Min / Max Value settings and set Accuracy to Actual (slower). Click OK. In the map canvas, you should now see a natural colour image. 

What these settings are doing is relatively straightforward. Each of B01-B12 is now stored as a separate Band in the virtual raster. A computer screen can display 3 colours – red, green, and blue. You’re choosing here which Band displays as each of red, green, and blue on the screen – just as you were doing in the first custom visualization in Copernicus Browser. Choosing the actual RGB colours gives you a natural colour image – but you also have the possibility here of assigning the RGB colours to different raster bands, enabling you to visualize near infrared and shortwave infrared bands in colour. Do feel free to play around – you can try any combination you played around with in Copernicus Browser. You could always try the false colour visualization – and see how the QGIS version compares to the Copernicus Browser version.

Be aware: the bands in QGIS don’t retain the original names, unfortunately. QGIS Bands 1-8 are B01-B8, but since there’s no B10 in what you downloaded from Copernicus Browser, the QGIS Band 10 is actually B11, the QGIS Band 11 is actually B12, and just to complete the confusion, QGIS Band 12 is actually B8A. QGIS lists the rasters as bands in numerical order of the listing when selecting the raster files to combine. 

To show the SWIR visualization we looked at in Copernicus Browser earlier, use:
- Red – Band 11 (```B12```)
- Green – Band 12 (```B8A```)
- Blue – Band 04 (```B04```)

### Indices in QGIS

In the last exercise, you used the Raster calculator to visualize flood risk maps using water level data and a digital elevation model (DEM) raster. We can also use the Raster calculator to calculate indices, such as the Normalised Difference Vegetation Index (NDVI).

Remember that in a raster image, each pixel has a value. If we have the same pixel in two raster images, we can subtract one from the other to calculate the difference. The Normalised Difference Vegetation Index is ```(B08-B04)/(B08+B04)```. We can put this into the Raster calculator, and that calculation is done for every pixel across the image.

From the menu, choose ```Raster > Raster calculator```. Click the Browse button beside Output Layer, navigate to your Sentinel 2 folder, type a filename ```NDVI.tif```, and click Save. Leave Output Format as GeoTIFF. 

In the Raster Calculation Expression panel, type an open bracket ```(```, then double click the ```B08``` raster above. Then a minus ```-```, then double click the ```B04``` raster. Close bracket ```)```, divide ```/```, open bracket ```(```, then double click ```B08``` again, then plus ```+```, then ```B04```, and finally close bracket ```)```.

When you've done this, click OK. The resulting image in the map canvas will be greyscale – it only has one band.

To visualize it better, let’s use a colour ramp. Right click on the NDVI layer in the Layers panel, choose Properties and then Symbology. Change Render Type to Singleband pseudocolor. Expand Min/Max Value Settings and set Accuracy to Actual (slower). Under Mode, select Continuous. For the Color ramp, the exact green-brown-grey colour scale the Copernicus Browser uses isn’t built-in for QGIS; we could probably recreate it, but the BrBG colour ramp (available from the All Colour Ramps list) which is close enough. Click OK to see the result.

You should now see a false colour visualisation with healthy dense vegetation in green, shrub and grasslands in blue-green, urban areas in greys and white along with bare rock and soil, and water in brown - and you should be able to see your flood risk areas above this, allowing you to learn more about what's in your flood risk areas.

### Unsupervised Classification of Multispectral Data ```[A1-grade]```

Showing the data in all these different ways is great – especially in QGIS, where you can have your area, rivers, lakes etc. on top of the visualizations. But we can do even better. 

In this task, we’ll create an unsupervised classification of the data. QGIS will look at the pixels at the same point in multiple images, and classify all the points into different clusters depending on how they show in different bands. Essentially, trying to figure out how different land uses show across the bands – agriculture, forest, urban, water etc. It’s unsupervised because QGIS does this without input from us. There’s a different technique called supervised classification where the user selects points with particular land uses, and QGIS will try to use the values for those points to run a classification. I’d like you to be aware that supervised classification exists, but it’s a bit too complicated for us to try at this point.

We’ll use the data you downloaded from the Copernicus Browser for bands ```B02```, ```B03```, ```B04```, ```B05```, ```B06```, ```B07```, ```B08```, ```B8A```, ```B11```, and ```B12```. (Why not the others? Because ```B01``` and ```B09``` have a spatial resolution of 60m per pixel, whereas the other bands are 10m or 20m per pixel. The lower resolution images don’t help much here.)

Now, you’re going to use an advanced feature. For this we need to add a plugin, so from the menu, choose ```Plugins > Manage and Install Plugins```. In the search box of the plugins window, type ```SAGA```. You should see ```Processing Saga NextGen Provider```in the list - select it, and click ```Install Plugin```. Close the plugsins window when done.

Now, from the menu, choose ```Processing > Toolbox```. In the search bar, start typing ```K-means clustering for grids``` – it should appear in the list under ```SAGA Next Gen > Image analysis```. Double click it to open.

What this tool does is check the value of the pixels in the same place in each raster, looking for areas which have generally similar values across multiple bands, and so dividing the areas of the images into categories or clusters.

Click the Browse button beside Grids, and click the checkboxes beside bands ```B02```, ```B03```, ```B04```, ```B05```, ```B06```, ```B07```, ```B08```, ```B8A```, ```B11```, and ```B12``` to select them. Click OK.

Back in the ```K-Means Clustering For Grids``` window, for **Method**, select ```Combined Minimum Distance / Hillclimbing```. For **Clusters**, choose ```7```. Click the checkbox to select ```Normalise```. 

Scroll down, and beside **Clusters**, click the Browse button and choose *Save to file*. Navigate to your Sentinel 2 folder and give it the file name ```Clusters```.
Under **Statistics**, deselect *Open output file after running algorithm*. Click **Run** to run the tool. 

It will take a while – at least a couple of minutes. You might get a few errors while running it – if it says SAGA had a problem and needs to close, just click close on the popup – it will restart itself. When it (finally) finishes, you’ll see a greyscale image. 

Colour is more visual, so open Symbology for the Clusters layer. Change Render type to Paletted/Unique values. Leave the Color ramp on Random colors, and click Classify below the panel to see the colour map. Click OK to close the Symbology.

QGIS should have now identified 7 different categories, and coloured them. (It may have filled in the background as a colour as well; we can fix that, but it’s not important right now, so eh, whatever. We’re interested in what’s inside your area anyway.) The next step would be to identify which colour represents which type of land cover. Zoom in to the image and look at what each colour is representing – water, fields, buildings, etc. You can toggle the visibility of the Clusters layer on and off to look at what's on the base map under particular Clusters colour areas. It might also help to add a Google Satellite map layer. 

The options we chose – the method, and the number of clusters – might not be ideal for the particular area you’re looking at. If you were doing this properly, you might consider trying again a couple of times until you have a result you're happy with. But the point here is mainly to introduce you to this kind of analysis, showing you what’s possible, not trying to get it perfect. This is another place where literature review would really help. Anyway, what I'm trying to say is, don't worry if it's not perfect.

One thing I would like to change though is the colour scheme. Right now, the colours don’t match the land use by any conventional colour use. Going into the Properties and Symbology, and double clicking on any colour, allows you to change that colour. You can also change the label. By comparing your clusters to the other raster layers, you should be able to identify land uses – comparing to the NDVI should let you identify vegetation areas, for example. Label each of your 7 land uses, and give them appropriate colours.

You can also go back into the Symbology options and set Blending Mode to Overlay, and turn off the visibility of all the layers between the clusters and the DEM so it shows up 3D. If you do this, you might also want to play with the Brightness, Gamma, Contrast, and Saturation settings to try and make it look better.

Congratulations - you've just created a land use map. You can now see what kinds of land uses are within your flood risk areas - and would even be able to do calculations, like determining what percentage of the flood risk areas has each land use. 

By the way, there's another, more general name for this kind of classification, one you might have heard before. It's also called machine learning.

Save the project before continuing.

Obviously this is all really confusing when you’re doing it for the first time, but I hope you’ll agree that actually getting the data from the Copernicus Browser and changing how it’s displayed in QGIS is not massively complex to do – the data is there, it’s just a case of dropping the right bands in the right channel, or calculating the right index. 

Knowing how to use it – which bands to use, which index to calculate, what all the results mean – that’s the trick! But, that’s the sort of thing you learn from literature review when you need to know it, and doing it over and over again. For now, it’s enough that you’ve seen what data is out there, and some of what you can do with it.


## Going Further
___
The next step after this kind of unsupervised classification would be *supervised classification*, where you identify the land use of some example points, and the computer uses those examples to learn how to classify the different land uses. There is a QGIS plugin which you can install called the *Semi-Automatic Classification Plugin* which has been built to do this. Feel free to try it out, if you're so inclined.

More info: [SACP Tutorial 1: Basic Land Cover Classification](https://semiautomaticclassificationmanual.readthedocs.io/en/latest/tutorial_1.html)

___
[Previous](./21_sentinel_2.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./23_census_small_areas.md)