![UL Geography logo](../assets/images/GY4006_logo.png)

# 12: Clipping Water Level Monitors

We also want to cut the water level monitors outside your AOI ```[C-grades]``` or AOI buffer ```[B-grades and above]```, but before we do that, let's have a quick look at the layer. Open the attribute table for the water level monitors by right clicking on the layer in the Layers panel, and selecting Open Attribute Table. You'll see that there are multiple points with identical names. We want the location of the water level monitors, but the OPW actually has sensors monitoring more than just the water level, so there are too many points here. 

We do want to clip the layer, but we also want to drop the extra points for other kinds of monitors. 

In the attribute table, you should see that for each point, we have a station reference number, station name, sensor reference, region ID, and more. You’ll see the same station reference numbers and names appearing a few times, because there’s multiple sensors at many monitor stations. The attribute we want to use is ```sensor_ref``` – the ones with a value of ```0001``` are the water level sensors we want on our map. You can use this attribute value to select all the points with this attribute, just like you selected your own AOI.

## Processing the Data

Go back to the toolbar button which looks like a yellow box with a grey box on top of it – the Select Features by Value tool –  and click it. In the ```Select Features by Value``` window, type ```0001``` into the box for ```sensor_ref```. If you click the Flash Features button, all the points with this attribute should briefly flash in the map canvas (move the Select Features window if it's in the way). This is a handy check. 

When you’re ready, click the Select Features button. You should get a message at the top of the screen saying ```454 matching features selected``` (the number might change a bit depending on how many sensors are working on the day you do this). Click Close to close the Select Features window. 

The data in the map canvas should not look any different. Selected features are usually shown in yellow – but in this case, there are points for other sensors at the same points (0002, 0003, and 0004) covering the selected features, so we can’t see that.

We want these features as a new layer - but we still need to clip the ones outside your AOI or AOI buffer, so we don't want to save it yet. Instead, from the menu, choose ```Edit > Copy Features``` and then ```Edit > Paste Features As > Temporary Scratch Layer```. You can leave the name as ```Pasted``` for now.

Now, repeat what you did to clip the rivers and the lakes to your AOI or AOI buffer, selecting ```Pasted``` as the Input Layer. This should produce a scratch layer called ```Clipped```.

Now we can save it. Right click on the ```Clipped``` layer in the Layers panel, and choose ```Export > Save Features As```. In the ```Save Vector Layer as...``` window, choose Geopackage for Format. Beside File name, click the Browse button […], navigate to your GY4006 folder, and type a filename OPW Water Level. Beside CRS, choose Project CRS: EPSG:2157 – IRENET95 / Irish Transverse Mercator. 

There's some extra data we don't need here, so let's drop it. Click the dropdown arrow beside ```Select fields to export and their export options```, and untick the checkboxes beside datetime, value, err_code, url, and csv_file. We don’t need these, so there’s no point having them in our new layer. Make sure the checkbox beside ```Add saved file to map``` is ticked. When ready, click OK to save the new layer, and you should see it appear in the Layers panel.

If you open the attribute table for the new layer, you should see only 4 columns, and sensor_ref should be 0001 for every row of data.
We don’t need two OPW layers, so right click on the original OPW water level layer, and choose Remove Layer. Click OK on the Remove Layers and Groups popup to remove the layer.

Save the project.


___
[Previous](./11_clipping_rivers_lakes.md) | [Next](./13_monitors_symbology.md)
