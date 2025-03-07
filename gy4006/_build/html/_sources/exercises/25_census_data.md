![UL Geography logo](../assets/images/GY4006_logo.png)

# 25: Census Small Areas Data ```[C-grades and above]```
___
You now have a map of the Census 2022 Small Areas vector polygons for your area. Now you need to get the actual data to go with each of these polygons.

## Importing Processing Visualising the Data
___
Go back to the page for data from the 2022 census on the [CSO website](https://www.cso.ie/en/census/census2022/census2022smallareapopulationstatistics/), and the table under *Download Small Area Data and Boundary Files*. 

Last time, you downloaded the *CSO Small Areas* under *Ungeneralised Boundaries (UG)*. This time, you'll get the attribute data: click the ```CSO Small Areas 2022 (18,919)``` link in the first cell of the *CSV Download* column. The data should begin to download.

There's one more file you'll need here. Just above the table, you'll see a link to the ```SAPS 2022 Glossary (XLS 30KB)```. Click the link to download this file as well. You won't be adding this file to QGIS, but this is a glossary which you'll need to identify what each column in the Small Areas census data tables represesnts.

When the Census Small Areas data tables file has downloaded - as ```SAPS_2022_Small_Area_270923.csv``` - move it to the SAPS subfolder of your GY4006 folder.

We need to do something different to add the this census data tables file to QGIS – you can’t just drag and drop it in. 

From the menu bar, go to ```Layer > Add Layer > Add Delimited Text Layer```. 

*(A ‘delimited text’ file is a simple way of storing a lot of data. Rather than complex formatting into tables or the like, the data is stored as ordinary text, with the different columns which are delimited (meaning separated) by punctuation – e.g. a space, a tab, a semicolon, or a comma. In this case, the data is delimited, or separated, by a comma; there is a comma between every point of data. This is called a Comma Separated Values file, or CSV – hence the .csv at the end of the name.)*

The Data Source Manager should now be open: Click on the **Browse** button (...) next to the **File name** bar, browse to find and select the ```SAPS2016_SA2017.csv``` data file, and click *Open* to close the file select window. 

Make sure the following options are selected:
- Under File Format, select CSV (comma separated values)
- Under Records and Fields Options, select both First record has field names and Detect field types
- Under Geometry Definition, choose No geometry (attribute only table)
 
Now you can click Add, followed by Close. You should now see the ```SAPS2016_SA2017``` layer in the Layers panel, with an icon indicating that it is an attribute table, with no geometry definition. 


Save the project before continuing.


___
[Previous](./24_clip_census.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./26_join_census.md)