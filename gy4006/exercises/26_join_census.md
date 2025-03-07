![UL Geography logo](../assets/images/GY4006_logo.png)

# 26: Join the census polygons to the census data tables ```[C-grades and above]```
___
While the census data table layer you've just added contains the census data, it’s currently not being displayed in any form, because it’s just numbers without any map data for QGIS to show.

In some of the earlier tasks, you looked at the attribute tables for a couple of layers. You can think of the census data table layer as an attribute table which is not tied to any geographic data. 

The geographic data to which it should be linked is, of course, the census vector polygon layer. What we want is for the census data table layer to act as part of the attribute table for the census vector polygon layer. QGIS allows us to do just that.


## Processing the Data
___
In order to join them, there needs to be some data which appears in both layers, so that QGIS knows which row of attribute data to join to which vector polygon. We can check this by opening the attribute tables. First, right click the census vector polygon layer in the Layers panel, and choose Open Attribute Table. You'll see a few things which could be reference numbers: note the column ```SA_GUID_2022```.

Now close this, and open the attribute table for the census data tables. You can see there's just 3 columns before you're into the actual census data - and while none of them is ```SA_GUID_2022```, one of them is ```GUID```. Since this is the table of data for small areas - SA - from 2022, it's pretty reasonable to infer that this is the same as ```SA_GUID_2022```. Close the attribute table.

From the menu, choose ```Processing > Processing Toolbox```. In the search bar of the Processing Toolbok panel, type ```join```, and find ```Join attributes by field value``` under ```Vector general``` in the list of tools. Double click this to open it.

Set the **Input layer** to be your census vector polygons layer, with **Table field** ```SA_GUID_2022```.

Set the **Input layer 2** to be your census data tables layer, with **Table field** ```GUID```.

Leave **Join type** as ```Take attributes of the first matching feature only (one-to-one)```.

Select ```Discard records which could not be joined``` - this will drop all the rows from the data table layer for the census areas outside your AOI.

Under **Joined layer [optional], click the Browse [...] button, choose ```Save to Geopackage```, and in the *Save to Geopackage* window, find the ```census.gpkg``` file you saved earlier, and select it. It will ask you for a layer name: call it ```Small Areas 2022```.

Click Run. A new ```Small Areas 2022``` layer should appear in the Layers panel. If you open the attribute table for this new layer, you should see that it contains all the attributes from both the original vector polygon and data table layers - including all the census data.

You can now remove the individual vector polygon and data table layers - you don't need them anymore.

Save the project before continuing.


___
[Previous](./25_census_data.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./27_field_calculator.md)