![UL Geography logo](../assets/images/GY4006_logo.png)

# 24: Clipping the Census Small Area vector polygons ```[C-grades and above]```
___
You now have a vector polygon map layer of the 2022 Census small areas - but much like the rivers, lakes, and other data, this layer has data for the entire State. You certainly don't need that - but we can do what we did for the other vector layers, and clip the layer to show only the area we want.

## Processing the Data
___
First, it will speed things up immensely if you toggle off the visibility of the census small areas polygons layer. QGIS will be using quite a lot of computer resources to keep drawing the polygons on the map canvas. We don't need that, so let's not waste the resources. 

From the menu, choose ```Vector > Geoprocessing Tools > Clip```. 

In the *Clip* window, choose your census vector polygon layer as the **Input layer**, and your AOI ```[C-grades]``` or buffer ```[B-grades and above]``` as the **Overlay layer**.

What this will do is create a new layer, which contains only the census features which are within your AOI or buffer. 

Click then Run. When it’s finished, click Close. You should see the new ```Clipped``` scratch layer in the Layers panel. We need to save this layer properly. 

Right click on the ```Clipped``` layer in the Layers panel, and choose ```Export > Save Features As```. 

In the *Save Vector Layer as…* window, make sure **Format** is set to ```Geopackage```, and **CRS** is set to ```EPSG:2157 IRENET95 / Irish Transverse Mercator```.

Click the Browse […] button beside **File name**. In the *Save Layer as…* window, navigate to your GY4006 folder and SAPS subfolder, type ```census``` as the **File name**, and click *Save*. 

Back in the *Save Vector Layer as…* window, type ```Small Areas``` as the **Layer name**, and ensure ```Add saved file to map``` is selected. Click *OK* to save and add the new layer.

You should now see the new Census layer in the Layers panel. Remove the original census vector polygon layer and the ```Clipped``` scratch layer - you don't need these anymore, and they're hogging resources.

Save the project before continuing.


___
[Previous](./23_census_small_areas.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./25_census_data.md)