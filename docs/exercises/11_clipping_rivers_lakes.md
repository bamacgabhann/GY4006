![UL Geography logo](./assets/images/GY4006_logo.png)

# Clipping Rivers and Lakes

If your area is in, say, Carlow, then the rivers in, say, Donegal are not exactly relevant for you right now. You want to concentrate on the data that’s within your area. So, let's cut out all the rivers and lakes outside your AOI ```[C-grades]``` or AOI buffer ```[B-grades and above]```. 

## Processing the Data

Let’s do the rivers first. From the menu, choose ```Vector > Geoprocessing Tools > Clip```. In the Clip window, choose ```WATER_RivNetRoutes``` as the Input layer, and AOI ```[C-grades]``` or AOI buffer ```[B-grades and above]``` as the Overlay layer.

What this will do is create a new layer, which contains only the river features which are within your AOI or AOI buffer. 

Click then Run. When it’s finished, click Close. You should see the new ```Clipped``` layer in the Layers panel, with a symbol resembling a computer chip. This is the symbol for what QGIS calls a scratch layer: a temporary layer that is not saved if the project is closed. We need to save this layer properly. 

Right click on the ```Clipped``` layer in the Layers panel, and choose ```Export > Save Features As```. In the ```Save Vector Layer as…``` window, make sure Format is set to ```Geopackage```, and CRS is set to ```EPSG:2157 IRENET95 / Irish Transverse Mercator```.

Click the Browse […] button beside File name, navigate to your GY4006 folder, type ```Rivers``` as the File name, and click Save. Click OK to save the new layer.

You should see the new Rivers layer in the Layers panel, and you can remove the ```Clipped``` scratch layer now.

Now, the new layer will have defaulted to single colour lines. We want the same colour scheme as our main rivers layer. We don’t need to go through all the settings again – we can just copy and paste the styles. Right click on ```WATER_RivNetRoutes``` in the Layers panel, and choose ```Styles > Copy Style > Symbology```.

Then, right click on the new ```Rivers``` layer, and choose ```Styles > Paste Style > Symbology```. The new ```Rivers``` layer should now have the same styling as the full layer, but with only the data in your area. 

You no longer need the ```WATER_RivNetRoutes``` layer, so you can remove it.

Repeat the Clip process for the ```WFD_LakeSegment layer```, calling the new layer Lakes.

Save the project before continuing.