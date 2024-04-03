![UL Geography logo](./assets/images/GY4006_logo.png)

# Basemap

It would be really useful if we could have a base map, just so we can see where we are! Luckily, we can get this pretty easily, for the whole country even, without having to download it – but we have to add a plugin to get it. Plugins are optional add-ons to the main QGIS software. 

## Adding the Data<

From the menu, choose ```Plugins > Manage and Install Plugins```. In the search box, type ```QuickMapServices```; choose it from the list, and click ```Install Plugin```. 

When it’s done, click ```Close```. Then, from the menu, choose ```Web > QuickMapServices > Settings```. In the Settings window, click on the ```More Services``` tab, and click ```Get Contributed Pack```.

Click OK on the confirmation, and Save to close the settings window when done.

Now, from the menu, choose ```Web > QuickMapServices```, and you will see a large number of options. From the list choose ```Google > Google Road``` or ```OSM > OSM Standard```.

A Google Road or OSM Standard layer will appear at the bottom of the Layers panel, and you will see the basemap in the map canvas – where it’s not covered by the vector data you’ve added.

Save the project again.

You might be wondering why we bothered to get separate layers for the rivers and lakes if we can just look at them on the basemap. The answer to that is that while yes, we can look at them on the basemap, we can’t do anything more than look. Having separate data layers for them means we can do things with them.