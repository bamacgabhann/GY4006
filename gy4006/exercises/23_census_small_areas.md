![UL Geography logo](../assets/images/GY4006_logo.png)

# 23: Census Small Areas ```[C-grades and above]```
___
You now have a map showing the flood risk areas, and should be able to say something about *what* would be affected by flooding, should the water reach the level you mapped.

But what about *who* would be affected by this level of flooding? You can explore this by using data from the Census of Population. 

You’ve spent the last few tasks working with raster data – a digital elevation model, and multispectral passive remote sensing data. In both cases, we had a raster layer made up of pixels. Each pixel had a shape, and each pixel had data. In the DEM, each pixel has a measurement of the height of the land surface. In the satellite imagery, each pixel had values for the Sentinel-2 bands, or calculations based on them. Think about that for a second. The raster pixels weren’t just defining a shape – they held information about that shape. 

Vector data doesn’t have to have extra information about the shape it’s defining. Sometimes, it’s just a shape. The vector polygon for your area of interest, for example – that's just defining the shape, outlining the area you’re interested in. 

But some of the vector data you’ve used has had some extra information associated with it. You’ve already used this in a couple of cases. For example, the OPW Water Level Monitors layer has information including the reference number for the station – you used the Identify Features tool to find this, and then used that to look up the water level data on the OPW website. You AOI even - you extracted that by finding the AOI which had your student ID.

This extra information associated with vector data is called *attribute data*. You can see the attribute data for any vector layer by right clicking on it in the Layers Panel, and choosing Open Attribute Table. Each row in the attribute table corresponds to one feature, and each column has data for a particular aspect of that feature – which can be text, a number, a date or time, or various other types of data. For example, a reference number, a name, a year, a true or false answer to a particular question, or a measurement of some kind.

Attribute data is where GIS becomes especially powerful, and you're going to see this a little in this next task. The Census data attributes contain a huge amount of information about the areas their features define. You'll be working with data from the 2022 census, use this data to explore the people who are living in the areas we’ve mapped as at risk from flooding in the previous tasks.

To map the census data, we need two things:
- Vector data defining the map areas
- Attribute data for each area

The census data is made available at a range of geographic levels – you can look at the data by Dáil Éireann electoral constituency, by administrative county, by local Electoral Division, by province, by European statistical (NUTS) region, and more. 

The highest resolution we can use is by Small Area. The Small Areas are defined within the Electoral Divisions – averaging around 100 addresses, and generally within natural features such rivers, and anthropogenic features such as housing estates.

The Central Statistics Office (CSO) publishes the census data, but the map areas come from Tailte Éireann Mapping Division – formerly the Ordnance Survey Ireland. So we need to download the vector and attribute data separately, and join them together.



## Importing the Data
___
The data from the 2022 census is available from the [CSO website](https://www.cso.ie/en/census/census2022/census2022smallareapopulationstatistics/). Open this page, and scroll down to the section *Download Small Area Data and Boundary Files*. 

You should see a table with two columns: *CSV Download*, and *Ungeneralised Boundaries (UG)*. 

First, we'll download the vector data. 

The first entry in the table under *Ungeneralised Boundaries (UG)* is *CSO Small Areas*. This is the vector data we need. Clicking this link will bring you to the page for this dataset on the Government's Open Data portal. On this page, click the *Download* link. You'll see a list of options for different file types to download: scroll down to find ```GeoJSON```, and click *Download*. The file should begin downloading. 

It is quite a large file (around 500Mb), so it might take a little time. When it's downloaded, create a new folder called SAPS *(this stands for Small Area Population Statistics)* in your GY4006 folder, and move the file into that.

Find this file in the Browser panel, and drag it into the map canvas to add it to the project.


Save the project before continuing.


___
[Previous](./22_bands_in_qgis.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./24_clip_census.md)