![UL Geography logo](../assets/images/GY4006_logo.png)

# Task Title ```[C-grades and above]```

You should now have only the water level monitors inside your area or buffer on your map. However, they're still the default symbol, a small circle with a thin black outline and a random colour fill. That doesn't scream "water level monitor" to me! There's probably better symbols we could use, so let's change it.

## Visualising the Data

Right click on your water level monitors layer in the Layers Panel, and choose Properties, then Symbology.

In the Symbology dialog, you should see the layer is set to Single Symbol, with a Simple Marker. You should see some basic options for changing the symbol colour, opacity, size, and rotation. Below that is a panel with some symbols - if you scroll down the list you will see some diamonds, circles, triangles, and a couple more specific symbols. You can choose one of these, and adjust the colour, size etc. to your liking.

If you'd like more options, click on ```Simple Marker``` at the top. You'll see more options now, including ```Symbol layer type```, a drop-down which is currently set to ```Simple Marker```. Change this to ```SVG Marker```. Now, if you scroll down, you should see a panel of SVG images which can be used as symbols. There's a couple that might suit. If you click on one to choose it, and scroll back up to the options, you can change the colour of the fill, the colour of the stroke (i.e. the outline), the size, and more. You can play around a bit until you're happy with it.

Save the project before continuing.

## Going Further

There's actually a lot more you can do with the symbols. 

Clicking the green plus at the top of the Symbology dialog allows you to add one or more additional symbol layers - so you can have the symbol be an SVG Markers above a Simple Marker, or any other combination you like. 

If you're not happy with the variety of symbols available, you can add more. Probably the easiest way to do this is using the ```QGIS Resource Sharing``` plugin. You can add this by choosing ```Plugins > Manage and Install Plugins``` from the menu, and typing "resource sharin" in the search bar. Find the plugin in the list, and click the ```Install Plugin``` button. Now if you go back to the ```Plugins``` menu, you'll have a ```Resource Sharing``` option, and clicking this will open a dialog with numerous sets of symbols and styles which you can add by clicking ```Install```. Now, if you go back to the Symbology, and choose SVG Marker, you should be able to find the symbol set you just added, and choose one of them.

More info: [QGIS User Guide / 14.2. The Symbol Selector](https://docs.qgis.org/3.34/en/docs/user_manual/style_library/symbol_selector.html)

___
[Previous](./12_clip_water_level_monitors.md) | [Next](./14_Adding_DEM)