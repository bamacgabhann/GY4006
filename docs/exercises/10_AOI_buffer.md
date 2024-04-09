![UL Geography logo](../assets/images/GY4006_logo.png)

# 10: AOI Buffer ```[B-grades and above]```
___

If your area is in, say, Carlow, then the rivers in, say, Donegal are not exactly relevant for you right now. You want to concentrate on the data that’s within your area. Shortly, we’re going to do that – cut out all the river and lake and monitors data that’s not relevant to you. However, the rivers and other data which might be of interest to you doesn’t stop sharply at the borders of your area - it’s always good to think about what’s just outside, for context. 

## Processing the Data
___

To help with this, we can ask QGIS to draw what we call a buffer around your area. From the menu, choose ```Vector > Geoprocessing Tools > Buffer```. 

In the Buffer window, make sure Input Layer is ```AOI```.

Now you need to set the size of the buffer area. Some of the individual areas are bigger than others, and some have an OPW monitor while others don’t. I suggest setting this to 5km initially.

Be careful - sometimes if you change the units first and then the number, the units can reset - I've had too many students create 5-metre buffers around their AOIs. Not particularly useful, I think you'll agree.

When it's definitely set to 5km (or a distance of your choice), click Run to create the buffer area. 

You will see a new layer called Buffered in the Layers panelc. We’ll save it in a moment, but first check to see if there is a relevant OPW water level monitor within the buffer.

If there is not an OPW monitor in this buffered area, you should create a new, larger, buffered area, so that the closest relevant OPW monitor is included within the buffer area. For some areas with a monitor, 5km might be too big – feel free to go smaller.

When you have a buffer area you’re happy with, you need to save this as a new layer. To do this, right click on the ```Buffered``` layer in the Layers panel, and choose ```Export > Save Features As```. In the ```Save Vector Layer as…``` window, make sure Format is set to ```Geopackage```, and CRS is set to ```EPSG:2157 IRENET95 / Irish Transverse Mercator```. Click the Browse […] button beside File name, navigate to your GY4006 folder, type ```AOI Buffer``` as the File name, and click Save. Click OK to save the new layer. When this is done, you can remove the scratch layer called ```Buffered```.

(One potential issue here – sometimes the newly saved Buffer layer will have a symbol with a question mark beside it in the layer panel. Hovering over this symbol will show a warning that the layer has no associated CRS. If this happens, click the symbol, type 2157 into the search box, select EPSG:2157 – IRENET95 / Irish Transverse Mercator, and click OK. This should solve the problem.)

This buffer layer is useful to have – we’re about to use it in the next task – but it’s certainly not useful to have it covering your area of interest in solid colour, hiding the only part of the map you should be focusing on! You could change how the AOI Buffer layer is displayed using Properties and Symbology, in the same manner as you did for your area itself – but honestly, it doesn’t need to be visible at all. Click the check box beside the AOI buffer in the Layers panel – this will turn off display of the layer. It now exists, but it’s not shown on the map.

Save the project again.


___
[Previous](./09_AOI_symbology.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./11_clipping_rivers_lakes.md)