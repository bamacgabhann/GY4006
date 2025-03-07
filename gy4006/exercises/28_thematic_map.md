![UL Geography logo](../assets/images/GY4006_logo.png)

# 28: Thematic maps of census data ```[C-grades and above]```
___
You have a map showing flood risk areas - and you should be able to see enough on your map to think about *what* would be at risk if the water level in the rivers rose to the level you mapped. You also have census data which you could use to think about *who* would be at risk - but none of that data is actually being shown on the map; just the polygons defining the census small areas. It's time to make some of that data visible.

Most of the data you've added so far has just had a simple symbology. The Lakes are all one colour. All the water level monitors are represented by the same symbol. Even the census small areas are currently all the same colour. There's one layer where you may have done something more complicated - the rivers, which you might have coloured differently according to size, using a Categorised symbology. A *Categorised* symbology uses a different colour or symbol for different features which have been assigned to different defined categories. In the case of the rivers, this would be one colour/line thickness/etc. for rivers with stream order 1, a different colour/line thickness/etc. for rivers with stream order 2, and so on. Another example of a Categorised symbology would be a land use map, where you might have forests in dark green, grass in light green, urban areas in grey, agricultural land in brown, and so on.

Categorised symbology is used for *discontinuous* data. There's no such thing as a river with stream order 1.5, for example; it's either 1 or 2. The numbers for stream order aren't measuring anything - they're really just labels, a way of sorting the rivers into categories. 

That's not what the census data is like. The numbers in the census data aren't labels or categories. The census data is *continuous* data. It's counting people - and so the numbers can vary continuously from zero upwards.  

There's another kind of variable Symbology we can use to visualise continuous data, like the census data. *Graduated* symbology uses a colour ramp to visualise how values change from a minimum to a maximum. The colour ramp may be changing shades of a single colour, or changing from one colour to another, or changing through a defined series of multiple colours. Elevation on topographic maps is commonly shown using a graduated symbology - changing from blues underwater to greens on land at low elevations, through to browns and whites at high elevations. You've already seen this in the <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/GY4006_9_Single-band_Raster_Data.ipynb" target="_blank">Single-band Raster Data notebook <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>.

You can use a Graduated symbology to visualise the census data.


## Visualising the Data
___
Open the Symbology for your census layer, and at the top, where it says ```Single Symbol```, click the bar to open the dropdown menu, and choose ```Graduated```.

Beside **Value**, click the dropdown arrow, scroll down, and choose the one of the attributes:

- ```[C-grades]```: use the glossary you downloaded in [task 25](25_census_data.md) to choose an attribute related to social class or socio-economic group;
- ```[B-grades and above]```: use one of the attributes you calculated in the previous task.

Beside **Color ramp**, click the dropdown arrow top see the range of colour scales available. Hover over **All Color Ramps** to see the full range available. Choose one that you think works for your chosen attribute. 

That tells QGIS what attribute column to use, and what colours to use. We haven’t yet told it how to classify the values of that attribute along the chosen colour ramp. To start that, click **Classify** below the central panel. You’ll now see the panel populated with colours, values, and legend entries.

To see a visual spread of the data in the different colour bands, click the **Histogram** tab above the central panel, beside **Classes**, and click the **Load Values** button to see the data. You’ll notice the data is pretty well spread out. This is because the default setting for defining the different classes is **Equal Count** – so there will be an equal number of small areas in each colour class.

However, this might not be the most useful way to class the data. There are some other options, let’s have a look at those. Click the **Classes** tab to go back to the classes, and look at the dropdown menu beside **Mode**. By default it’s set to ```Equal Count (Quantile)```. Change it to each of the other options in turn, for each one clicking on the histogram tab to see how the data is distributed across the different colour classes. You should also feel free to adjust the number of classes.

When you’re happy with the classification, click OK to exit the Symbology window. There will be a delay while QGIS processes the different colours, but when it finishes, you should see the various small areas shown in different shades of your chosen colour ramp, depending on the values of your chosen attribute in each small area.

This is called a thematic map - because it's illustrating the geographic variation of a particular topic or *theme* across an area.

Save the project before continuing.

```[C-grades and B-grades]``` Congratulations - you now have enough data on your map to address your objectives and help answer your research question. Along the way, you've covered all the basics of working with data in GIS - you've added vector point data, vector line data, vector polygon data, raster data, and attribute data; you've done some basic geoprocessing on both vector and raster data (e.g. clipping, selecting by attribute value, and using the raster calculator), and you've visualised data in multiple different ways (simple, categorised, and graduated vector symbology, raster hillshade, and possibly more). Your final tasks are to arrange all this data into some print-ready maps for submission, and to interpret what you can see in the maps for your report.


## A second thematic map ```[A-grades]```
___
If you have calculated and want to illustrate a second attribute - well, you can't have two different symbologies on a single layer at the same time.

However, there's no reason you can't have the same layer *twice*, with each copy using a different symbology.

Right click on your census data layer, and choose **Duplicate Layer**. This doesn't make a new file, or change the data in any way. it simply shows the same layer - the same data source - a second time. 

Repeat the steps above on the duplicated layer, using a different colour ramp to show your second attribute. I would also advise changing the layer names (right click on the layer and choose Rename Layer) to indicate which layer is showing which data. 

Save the project before continuing.


___
[Previous](./27_field_calculator.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | ```[C-grades and B-grades]```[Print Layouts](./32_print_layouts.md) | ```[A-grades]```[Next](./29_georeferencing.md) 