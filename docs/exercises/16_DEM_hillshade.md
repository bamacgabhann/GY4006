![UL Geography logo](../assets/images/GY4006_logo.png)

# Hillshading the DEM ```[C-grades and above]```

Now you have the raster DEM only for your area of interest – but either it’s hiding the data in your area, or else hidden under other layers itself. That's not very useful.

What we’d like to do with the DEM layer is to display it in a 3D visualisation. On a flat screen, this can be done with a style called hillshading – displaying the DEM as if it was 3D, and being lit by an imaginary light source: the same as the sun illuminates the landscape.


## Visualising the Data

In the Layers panel, move the DEM layer so that it is above only the tile map layer (OSM or Google). 

Now, right click on DEM layer, and choose Properties then Symbology on the left. Change ```Render Type``` from ```Singleband grey``` to ```Hillshade```, and click OK.

Now you should see a very different grey area on the map, which looks somewhat 3-dimensional. You can see where the upland and lowland areas are. Often, the rivers will line up with the uplands and lowlands. 

It's still hiding the base map layer though. Go back into Properties and Symbology, and in the Layer Rendering section of thet Symbology dialog, change ```Blending Mode``` to ```Multiply```. Click OK again.

You should now see your base map layer - with the DEM hillshade applied to it, giving the base map the same 3D effect. 

Save the project before continuing.

## Going Further

You can make this look even better by changing some of the options. Go back to the Symbology dialog, and play with the settings to see what works. I suggest increasing the Z factor, and changing the Resampling options to Bilinear, with Oversampling set to 1.00. If you move the Layer Properties window so that you can see the map underneath, and click Apply after making changes, you can see how the changes affect the map without closing the Symbology dialog, which makes playing around with the settings a bit easier.

___
[Previous](./15_clip_DEM.md) | [Next]()