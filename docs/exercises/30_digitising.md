![UL Geography logo](../assets/images/GY4006_logo.png)

# 30: Digitising Features ```[A-grades]```
___
Now that you have the screenshot map of past floods georeferenced, you can see the positions of those past floods along with some of your other data. However, much like when you used the Raster calculator to make the flood risk maps, it covers up any data underneath. The only features of the georeferenced map which you want for your project are the the locations of previous floods. The rest is just a base map; and likely one which has been distorted by the georeferencing process. You already have a base map, so you don’t need a second, distorted version.

It might be possible to hide the base map portions of the georeferenced image, or extract the parts which are the past flood symbols, by using the colour values of the base map and symbols. However, there's a much easier and better solution. You can draw a new vector layer, adding features at the positions of the previous floods from the georeferenced image, and entering some other information from the OPW website as attributes. This is referred to as *digitising*.


## Processing and Visualising the Data
___
From the menu, choose ```Layer > Create Layer > New GeoPackage Layer```.

In the *New Geopackage Layer* window, click the Browse [...] button beside **Database**, and navigate to your *GY4006 / Georeferencing* folder. In the Save window, type a **File name** ```Past Flood Events```, ensure **Save as type** is set to ```GeoPackage (*.gpkg)```, and click *Save*. This should also auto-populate ```Past Flood Events``` in the **Table name** field; this is fine.

The next option to set is the type of geometry. Vector layers can have Point, Line, or Polygon features - but each layer can only have one kind. The features you'll be digitising are not polygon areas, or lines -  the past flood locations are marked on the georeferenced map as single points. So, set the **Geometry type** to ```Point```.

(If the areas covered by these flood events was shown – which it could have been, if we had turned on the Past Flood Event Extents layer on the OPW’s web map – we could have added a polygon layer, and traced over them. It works exactly the same way, except you’re tracing polygons instead of marking single points; and of course line features can also be digitised. Good to be aware of that, but we’ll just stick with the points for now.)

You should also set the **CRS** to the Irish Transverse Mercator EPSG:2157 coordinate reference system.

These settings would be enough to add the points to the map, but you may have noticed that there’s two different icons for the past floods – one for one-off events, and one for recurring events. If you clicked on any of these symbols on the OPW’s floodinfo.ie web map, you would have opened a panel with more details about the events: the date (if a one-off event), the source, the catchment, a name, and how accurate the location is (exact or approximate). If you simply draw the points in the correct locations, you would not be able to associate any of that information with the locations. To include some of this information, you can define some attribute fields to hold the data.

You don't need all of the information from the OPW web map, but it would be important to distinguish the dated floods from the recurring floods. It could also be useful to include the date, and the source of the flood (so that you can distinguish river floods from other kinds). 

You can add attribute fields for each of these in the **New field** section. For each of the new fields, you need to enter a field name, and the type of data to be stored in that field; some types of data also require you to specify the maximum length of the data. Once you have entered that information, you can click the **Add to fields list** button, and you should see the field appear in the **Fields list** below. You have three attributes to add in this way: 

- For the source of flood, there's a few different potential attributes, and you'll want to be able to type that information in - so that needs to have a **Type** of ```Text (string)```. There's a few different potential sources, including "river", "lake", and "coastal/estuarine waters"; the latter being the longest at 24 characters, so you should set the **Length** to ```24```.
- For the date of the dated floods, you can use a **Type** of ```Date```.
- For distinguishing one-off (i.e. *dated*) and recurring events, we could use another ```Text (string)``` field, but there's another option. You could think of this as a question: *"is this a recurring event?"*. From that perspective, we could use a True/False answer - which is the *Boolean* data type. So, give this field a name ```Recurring?```, and choose the **Type** ```Boolean```.

When you’ve got all 3 new fields added to the Fields list, click OK to create the layer.

You should see the new ```Past Flood Events``` layer in your Layers panel. Now, you can start adding the data to the layer. First, you need to turn editing on for the layer, so with the new ```Past Flood Events``` layer clicked in the Layers panel, find the **Toggle Editing**  button in the toolbar (looks like a yellow pencil), and click it to turn editing on for this layer.

Now click the **Add Point Feature**  button in the toolbar (looks like 3 green circles, with a yellow box in the corner). The points we want to add, of course, are visible in the georeferenced map: the flood locations. Click one of the past flood markers to add a point at its location.

When you click on the point, a popup will appear asking you to fill in the attributes for that point. Check the point you clicked back on the floodinfo.ie website, and enter the source, the date (you can leave this blank for recurring or undated floods), and click the *Recurring?* checkbox (Boolean!) if appropriate. hen that's done, click OK to add the point.

Now repeat for all the points in your AOI and buffer. When you’ve added them all, click the **Toggle Editing**  button again to turn off editing, and click **Save** on the popup to save the changes to the layer.

And that's it! You've digitised the data. You can now toggle off the visibility of the georeferenced image, and just use the new vector layer to view the past flood locations in context with all your other data.

One last thing to do - the symbols for the past floods are all a default circle, and they're all the same. So, edit the Symbology for this layer to show the one-off and recurring floods with different symbols, so that they can be easily distinguished.

Save the project before continuing.

## Going Further
___
pointers towards other options if applicable

More info: [Title](https://)

___
[Previous](./29_georeferencing.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./31_print_layouts.md)