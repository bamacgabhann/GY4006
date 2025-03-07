![UL Geography logo](../assets/images/GY4006_logo.png)

# 21: Multispectral Satellite Imagery ```[B-grades and above]```
___
Now that you have a GeoJSON version of your AOI buffer, in the WGS84 coordinate reference system, you can use this to work on your area in the [Copernicus Browser](https://browser.dataspace.copernicus.eu/) to access Sentinel-2 multispectral satellite imagery. 

You have previously been introduced to this kind of data in [Notebook 10. Multi-band Raster Data: Passive Remote Sensing](https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/GY4006_10_Multi-band_Raster_Data-Passive_Remote_Sensing.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/GY4006_10_Multi-band_Raster_Data-Passive_Remote_Sensing.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Visualising the Data
___
### Find cloud-free imagery
In the [Copernicus Browser](https://browser.dataspace.copernicus.eu/), look at the column of tools on the right. The top tool is shaped like a yellow pentagon – click this to expand the options, and then choose the left-most tool (with an arrow pointing upwards). This is the *File upload* tool.

Use the File upload tool to upload the GeoJSON file you just created of your AOI buffer. When you have done this, the map should zoom to your area, and you should be able to see your AOI buffer area outlined. 

Now it knows where to look, it’s time to find some data. In the search tab of the main panel, you can see a list of data sources, which are different earth observation satellite programmes. Select SENTINEL-2.

You will  see two options become available: L1C and L2A. Choose L2A. 

When satellite images are taken, they’re just images: they need to be processed before they can be used fully, projecting the image to a map, and so on. L1C data is processed to what is called *top of atmosphere reflectance*. L2A data is processed a bit further to remove the effects of the light travelling through the atmosphere, and is labelled *bottom of atmosphere reflectance*. This is the processing stage that is most useful for analysing data about the Earth’s surface.

In the search panel, ensure you have only Sentinel-2 selected, and that you have chosen the L2A option. The cloud coverage slider allows you to search for images with lower cloud cover, but we’ll leave that alone this time. By default, the Time range (at the bottom of the search panel, you’ll need to scroll down to see it) is set for the last month – we can leave it on that for now. Click Search.

The Results tab will now open, displaying all available images which meet the search criteria – which in this case are quite broad.

The map area will now be blue - but you may see a couple of different shades of blue. The Copernicus Browser shows the area covered by each available satellite image with a blue polygon. If you have one or more satellite images which only partially cover your area, you may see a line dividing two shades of blue. You don't want a partial image - you want imagery which covers the whole area of interest.

Scroll down the list, and note how frequently the images are collected, as well as the times and cloud cover. Find a recent image with a low cloud cover percentage and click Visualize. This will open the Visualization tab, and show the image.

This might also show the issue with the Max. cloud coverage search option – there might be only 1% cloud coverage, but that 1% might be the exact part of the image you want!

You have have to look at a good few images before you find one without any clouds in your AOI. You will find one, just keep looking until you do. There may be other issues as well, for example if there’s snow covering the ground, that will get in the way of your analysis: you want to analyse the ground itself, not snow lying on that ground.

You may have to go back to the Search to expand the data range – this is Ireland after all, cloud free days are rare! Alternatively, you can click the left arrow beside the data displayed at the top of the Visualization tab to cycle through previous images. 

### Simple Visualisations
The imagery is shown initially as a true colour photograph: but that’s not all the data. The Visualize tab shows a list of different Visualization options. We’ll look at a few of these in turn. Start with the False color – click on this, and click the down arrows beside it for an explanation of what it shows.

You can refer back to the explanation in [Notebook 10. Multi-band Raster Data: Passive Remote Sensing](https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/GY4006_10_Multi-band_Raster_Data-Passive_Remote_Sensing.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/GY4006_10_Multi-band_Raster_Data-Passive_Remote_Sensing.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a> if you need to, particularly the ```False Colour Visualisations``` section - that's what we're looking at here.

In short, we can create visualizations of the Sentinel-2 data using any combination of the 13 visible and infrared bands – but we can only see three at any one time. This is because our eyes are basically multispectral sensors with three bands – red, green, and blue. Every colour we see as a combination of these. Computer screens work the same in reverse; they show everything using combinations of red, green, and blue light, every other colour on a screen is just a combination of these. 

Any visualization of Sentinel-2 data shows data in each of these red, green, and blue channels. A true colour image uses ```B04``` (red light) in the red channel, ```B03``` (green light) in the green channel, and ```B02``` (blue light) in the blue channel. 

The false colour visualization uses ```B08``` (near infrared) in the red channel, ```B04``` (red light) in the green channel, and ```B03``` (green light) in the blue channel. It might seem strange to represent red as green, and green as blue, but it works really well to visualize the combination, so we can see differences easily. Using false colour visualizations like this, we’re not trying to show things as they are – *we’re trying to make it as easy as possible to see differences in the results*.

This false colour visualization is really useful for distinguishing vegetated areas (which show up red), urban areas (which show up grey), and water (which shows up black).

Next, look at the SWIR visualization – this uses ```B12``` (shortwave infrared, SWIR) in the red channel, ```B8A``` (near infrared) in the green channel, and ```B04``` (red light) in the blue channel. Click the down arrows to read the explanation.

### Remote Sensing Indices

Displaying one band in each of the red, green, and blue colour channels gives us nice colour composite images, but sometimes the different intensities of different bands means that nice looking images don’t tell us as much as they could. It’s often more useful to create much more complex Visualizations, based on calculations.

Again, you can refer back to the explanation in the ```Indices``` section of [Notebook 10. Multi-band Raster Data: Passive Remote Sensing](https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/GY4006_10_Multi-band_Raster_Data-Passive_Remote_Sensing.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/GY4006_10_Multi-band_Raster_Data-Passive_Remote_Sensing.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a> if you need to.

For example, plants don’t reflect much red light - they absorb it (in fact plants normally absorb both red and blue light, which is why plants are usually green), but they also reflect near infrared in ```B08```. To use this, we can set up what we call a normalized difference formula: ```(B08-B04)/(B08+B04)```. This formula will produce values close to 1 for areas with a lot of plants, because they’ll have high values in ```B08``` and very low in ```B04```; whereas low values will result in areas without plants, because there will be high values for ```B04```. 

How to show this formula? Since it produces a single number for each pixel, there’s two ways of showing it – either we can use just a single colour channel (e.g. green), and show e.g. darker green for higher values and lighter green for lower; or we can categorise the results, and show different colours for different categories, e.g. blue for -1 to -0.5, grey for -0.5 – 0.5, green for 0.5-1.0. 

Calculations done on remote sensing data, instead of using the raw band data, are known as an index. In this case, we’re dividing the difference by the total; that’s a type of index known as a normalized difference index. This particular index is the Normalised Difference Vegetation Index, or NDVI – it’s extremely well-known in remote sensing.
Because NDVI is so commonly used, it’s built in to the Copernicus Browser. You will see NDVI in the Visualizations list – click it to show the NDVI Visualization using a green scale, and click the down arrows to read the explanation. You can follow the links in that explanation to learn more about the NDVI.

There’s two other normalized difference indices we can use here. The Normalised Difference Moisture Index (NDMI) uses near infrared ```B8A```, and SWIR ```B11``` with the formula ```(B8A-B11)/(B8A+B11)```; this shows moisture in vegetation, so healthy vegetation will have values close to 1, unhealthy vegetation will be close to 0, and values close to -1 are bare soil or rock. Click on this to see the Visualization, and read the description.

We can also use the Normalised Difference Water Index, which uses ```B03``` (green light) and ```B08``` (near infrared), with the formula ```(B03-B08)/(B03+B08)```. This shows vegetated areas generally below 0, urban areas around 0, and water above 0.5 (rivers, lakes, sea etc).

### Beyond the built-in Visualisations 

It’s possible to create visualisations with any possible band combination, or even to use far more complex calculations than normalized difference indices to analyse the data. At the bottom of the Visualization list, choose Custom. Here, there are options for creating customised visualizations. In the Composite option, the default, you can drag and drop any band onto any of the three colour channels to create any combination of bands you like. Try it out.

Play around with different combinations. Try to bear in mind, while playing around, what the different bands show. If you were doing this for real research, this would be where literature review comes in – you would have previously read how other researchers have used different band combinations for what you want to do. For now, you can refer back to the information about the different bands to see what each might be showing.

Try putting ```B11``` in the red channel, ```B08``` (note: not B8A) in the green channel, and ```B02``` in the blue channel. 

This is a standard visualization for agricultural monitoring, quite widely used. ```B11```, in the red channel, highlights moisture in vegetation and soil, so red areas are wet vegetation and soil. ```B08```, in the green channel, is good at detecting vegetation, so green areas are vegetated. ```B02```, in the blue channel, is absorbed by plants, so more blue means less plants. In combination, red areas will be wet soil (```B11``` in red, plus ```B02``` in blue in more purply areas), green areas will be vegetated, more densely where there’s denser vegetation (```B08``` in green, and not much in red or blue), and yellow-orange areas will be drier soil (some ```B11``` red) with less vegetation (some ```B02``` blue).

We can also create a customised visualization of an index. Select the Index option, and you can drag and drop any two bands into the normalized difference index calculation. You can also set threshold values, so that only values in a particular range are shown. Try a few different bands and thresholds yourself, just to see the results. 

We can do even more by writing code (using the javascript language) to control the visualization in however complex a manner we want. (Don’t be scared - I’m not making you learn javascript, I just want to show you what’s possible.) Click the Custom Script option. What you should see initially in the Custom Script window is the actual code generated by the drag-and-drop you just did – because actually all the options you’ve been selecting until now have been running javascript code behind the scenes. Delete all the code from the Custom Script box, and paste the code below to replace it.

```
function clamp (a) {
  return a<0 ? 0 : a > 1 ? 1 : a;
}
function sigNDVI (b4, s4, b8, s8) {
  var sum = b8 + b4;
  var ndvi = (b8 - b4)/sum;
  var s_ndvi = 2 / (sum*sum) *
      Math.sqrt(b8*b8*s4*s4+b4*b4*s8*s8);
  var darkness = clamp(1-2*s_ndvi);
  return [
    0.9*clamp(1-ndvi)*darkness,
    0.8*clamp(ndvi)*darkness,
    0.1*darkness];
}
return sigNDVI(B04, 0.02, B08, 0.03);
```

It’s not important to understand this code – the point is to show you that you can do complex visualisations using code. Again, my main purpose in these exercises is to show you what’s possible. If you ever get to this point in your own work, you can learn what you need to. Though feel free to try and decipher what this code does, if you want! 

It actually implements a formula to incorporate ranges of uncertainty into the calculation of the NDVI index. It displays the NDVI using a scale from red (-1) to green (1), with results having a greater uncertainty shown in darker colours.

Once you’ve pasted the code in the box, scroll down and click ```Refresh Evalscript``` to visualize the results.

Now, seeing all the different visualizations on screen is interesting, but we don’t have our rivers, lakes, monitors, and flood risk maps here. It will be much more useful to see some of this in QGIS with the rest of our data. 

### Download the data ```[B-grades]```

Find the Download button on the right, and click it to open the download options. Choose the Analytical tab, and:
- Set **Image format** to ```TIFF (32-bit float)```
- Set **Image resolution** to ```Custom```, and enter ```10``` for both *Resolution X* and *Resolution Y*.
- Set **Coordinate system** to ```UTM29N (EPSG:32629)```
- Turn **Clip extra bands** off (this allows TIFF files with more than 3 bands)

Either:
- Choose one of the visualisations to download - either a custom visualisation you have produced, or one of the built-in visualisations. ```[B-grades]```

Or:
- Select all options under Raw ```[A-grades]```


Once you have selected the options, scroll down and click Download.

This downloads a zip file with all the raw images. In your GY4006 folder, create a new folder called ```Sentinel 2```, and extract the contents of the downloaded zip file into this new folder. 

*(Note: you may get errors while trying these. Copernicus Browser may give you an error when downloading, about sampleType – this isn’t a problem for what we’re downloading, so we can safely ignore it. Windows may give you an error when extracting the zipped files, saying the parameter is incorrect – I don’t know why this happens, but check Apply to All and click Skip, and it will extract the files anyway. I think Windows just doesn’t like this kind of file and throws a hissy fit.)*

You can close the Copernicus Browser window once you have the imagery unzipped in the folder. Go back to QGIS, and add the downloaded imagery to the map canvas from the Browser panel. You should see the imagery listed in the Layers panel - ensure that it's above the base map, but below your rivers, lakes, water level monitors, and flood risk maps, allowing you to see what's in the flood risk areas of the imagery.

Save the project before continuing.


___
[Previous](./20_aoi_geojson.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./22_bands_in_qgis.md)