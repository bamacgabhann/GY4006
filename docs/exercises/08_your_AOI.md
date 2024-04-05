![UL Geography logo](../assets/images/GY4006_logo.png)

# 08: Your Area of Interest (AOI) ```[C-grades and above]```
___

There’s no way you could feasibly analyse the entire map area - there's far too much data. It’s time to focus on your own area. You should already have the ```GY4006 Areas``` layer; this contains all of the indivudual AOIs. Let's extract yours.

## Processing the Data
___

If you open the attribute table for the ```GY4006 Areas``` layer, you’ll see each shape has two attributes: an area number, and a student ID. Your ID will be in this list (if it’s not, you better get in touch with me – and Academic Registry! – pretty quickly). 

Scrolling through the list to find yours would be frustrating. Thankfully, there's a much easier way.

In the toolbars, you will see a button which looks like a yellow box with a grey box on top of it – this is the ```Select Features by Value``` tool. Click this.

This tool allows you to do what it says - type in a value, and then select the features which have that value. Such as the ID field containing a value which is a particular student number. Yours, for example.

In the ID field, type your student number. Click Flash Features to see your area flash (if you can't see it, move the Select Features window - it might be covering it). Click Select Features then Close to select it.

Now you need to save your area as a separate file. Right click the ```GY4006 Areas``` layer in the Layers panel, and choose ```Export > Save Selected Features As```. 

In the ```Save Vector Layer As...``` window, select ```Geopackage``` for ```Format```. Click the Browse […] button beside ```File name```, navigate to your GY4006 folder, and type a filename ```AOI``` (this stands for Area Of Interest). Make sure the CRS is set to ```Project CRS: EPSG:2157 – IRENET95 / Irish Transverse Mercator```, and that the checkbox beside ```Add saved file to map``` is ticked. When ready, click OK to save the new layer, and you should see it appear in the Layers panel. 

You no longer need the full GY4006 Areas file, so you can right click on it and choose Remove Layer. Save the project.


___
[Previous](./07_river_symbology.md) | [Next](./09_AOI_symbology.md)