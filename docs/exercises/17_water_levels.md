![UL Geography logo](../assets/images/GY4006_logo.png)

# 17: Flood water levels ```[C-grades and above]```
___

You should have a nice looking map now - a base map from OSM/Google with a 3D-look from the DEM hillshade, with the lakes, rivers, and water level monitors for your area of interest. 

Having the DEM means you're now able to do some analysis to determine what areas would be flooded when the water level in the rivers rises to particular heights. Flooding happens when the height of the water level in a river has risen above the height of the land surface. The DEM gives you the height of the land surface. But what water level heights should you use in this analysis?

This would be much easier if someone had been recording the height of the water level for a river in your area, so you could look at how high the river water normally gets.

Oh wait, they have been! And you already have a map showing where they've been recording the data - that's your water level monitors layer. So, to help you decide what water level(s) you'll use to create your flood risk maps, you can look at the recorded data from a water level monitor in your area.

## Choosing the Data
___

The first step is to choose which water level monitor to use. Some areas have only a single water level monitor - if your area is one of these, you can skip ahead to the next step. If you have more than one monitor in your area, you can look at the positions of the monitors on the rivers to help decide which one is best to use. Your AOI hasn't been drawn randomly - it's a subcatchment area. All of the rivers in your area feed into each other, with the smaller streams coming together again and again until they all combine in one main channel, which flows out of the area at the outflow point. A monitor on a smaller tributary is only measuring water coming from a small proportion of your area - but one closer to the outflow point is measuring water coming from a much wider region. So you should choose the monitor closest to the outflow point for your AOI. 

The next step is to identify the monitor, so that you can look up the data from it. Click on your water level monitors layer in the layers panel to make it the active layer, and then use the ```Identify Features``` tool from the toolbar (look for an icon which is a blue circle with a letter "i" in it, and a cursor arrow pointing to it) to click on your chosen monitor.  

The Identify Results panel should appear on the right, and you should see the list of attributes of the monitor you picked. One of these will be a reference number for the station. Note this number (you only need the last 5 numbers – ignore all the zeros in the front). 

Now, go to the OPW water level data website: [https://waterlevel.ie/hydro-data/](https://waterlevel.ie/hydro-data/)

In the ```Search stations``` box top right, enter the 5=digit reference number, and it should zoom the map in on that monitor. Click on it to open the station information page.

This will open to a graph showing how the water level in the river at that point has varied over the last week. You should also see some coloured dashed lines on the graph - some with percentage values, and some with written labels. The percentage values indicate that the water level in the river is at or above that height that percentage of the time, e.g. the water level is at or above the 25% line 25% of the time. The median annual maxima line is essentially an average value of the highest water levels recorded every year, and the Highest Annual Maxima is the highest water level ever recorded in the river by that monitor.

(*note: some monitors may have been installed more recently, and so might not have much historic data. If you have chosen a monitor without much data, return to QGIS and select a different monitor.*)

### The Highest Annual Maxima ```[C-grades and B-grades]```

If you're going to make a flood risk map, the Highest Annual Maxima value might be a good place to start. The water level has only reached that height once, so it's not common, but we know it can reach that height - and if it has reached it once, it will almost certainly reach it again. 

To get the measurement for that water level height, choose ```Annual Max``` in the menu on the left to open the table of annual maximum water level readings. Find the highest water level, and make a note of that number - that's the water level you're going to use in the next task.

### Choosing a second water level ```[A2-grade]```

If you're going to make two flood risk maps, remember that the second one isn't just a flood risk map in itself - but it can provide an interesting comparison to the first flood risk map. Areas shown as flood risk in the first map but not the second map demonstrate how much bigger an area could be flooded for that much higher of a water level.

You could choose the median annual maximum - to find this, it's easiest to copy the annual maximum table into Excel, sort the table in order of water level heights, and choose the middle value - or use Excel's built-in median function to calculate it.

You could also choose the 1% water level. The water level in the river is at or above that height 1% of the time; there's 365 days in a year, so the water level would be expected to be at or above that height for 3.65 days every year. To find the value of the 1% level, click on ```Statistics``` in the menu on the left, and look at the numbers in the table under ```Levels equalled or exceeded for the given percentage of time``` (*not* the ```flows equalled...``` table!!). 

### Exceedance Probability and Recurrence Intervals ```[A1-grade]```

The percentages in the graph could also be referred to as *exceedance probabilities*. Think about the 1% water level - if the water level is at or above that height 1% of the time, then you could also think of that as there being a 1% probability of the water level being at or above that height. 

The flip side of this is the *recurrence interval* - if the water level is at or above that height 1% of the time, that's one day in every one hundred. So you could think of this as a *one hundred day-water level* - you'd expect the water level to reach this height once every one hundred days, on average. 

Water levels which are reached every year aren't the biggest problem. The more serious flood risk is the much rarer occasions when the water level rises far above normal, to levels only seen once or twice in a decade or century, or longer. Maybe the river water level only gets to that height once every hundred *years* - but that 'once' could be next week.

I didn't pick one hundred years randomly - that's the standard normally used, and you might even have heard the term on the news when significant flooding is being reported. 

If you're going to make a flood risk map, a 100-year flood would be a useful water level to map.

The statistics here don't list the 100-year water level height, but we can calculate it from the data provided, using a little bit of stats in Excel.

For simplicity, we'll do the calculation based on the annual maximum values. If we wanted to be really accurate, we'd use the full dataset (which is available through the ```Download``` link - the ```Complete high-res Data``` file, if you're feeling very committed!). However, for our purposes here, using the annual maximum values will be fine. Choose ```Annual Max``` from the menu on the left; you should see a button on the top right of the table. Clicking this should download the table. Open the downloaded file - it should open in Excel.

The first step is to rank the water levels in order of height, with 1 being the highest water level. It's a bit time consuming to do this manually, but you can use a formula to have Excel do it for you. 

The following instructions assume that the table is in columns A-G with the water level data is in column B, starting on row 9. If your table is different, adjust the formulas accordingly.

Type ```Rank``` in cell ```H8``` as a column header. In cell ```H9```, enter the formula ```=RANK.EQ(B9,B$9:B$xx)``` - replacing the ```xx``` with the row number of the last row of data. A number should appear in the cell - that's the rank value for the water level in that year. Click on the cell - you should see a small black square at the bottom right corner. Double-click this - it should fill down the formula into the cells below, down to the bottom of the table. That should be the ranks for every year.

The next step is to calculate the exceedance probability. This can be calculated as ```Rank / (number of years + 1)```. You can also think of this as the percentage of all these years that the water level for a particular year was equalled or exceeded. Again, we can use a formula to calculate this. In cell ```I8```, type ```EP``` as a column header. In cell ```I9```, enter the formula  ```=H9/(COUNT(H$13:H$xx)+1)``` - again replacing the ```xx``` with the row number of the last row of data. A number should appear in the cell between 0 and 1 - click on the ```%``` icon in the ```Number``` section of the Ribbon to show this as a percentage. Again, double-click the small black square at the bottom right corner of the cell to fill the column. This is the exceedance probability for every year of the dataset. 

Now we have to calculate the Recurrence Interval. This can be calculated as ```1 / Exceedance Probability```. Once again, we can use a formula to calculate this. In cell ```J8```, type ```RI``` as a column header. In cell ```J9```, enter the formula  ```=1/I9```, and once again double-click the small black square at the bottom right corner of the cell to fill the column. This is the recurrence interval for every year of the dataset. 

You now have the Exceedance Probability and Recurrence Interval for each year of the dataset, but we don’t yet know how often bigger events might occur. We can extrapolate the current dataset to explore such larger events. The easiest way to do this is by creating a graph.

In Excel, create a scatter plot with Recurrence Interval as the X-axis, and water level as the Y-axis. To do this, choose ```Insert``` in the menu, and in the ```Chart``` section of the ribbon, choose ```Scatter```. A scatter plot should appear, and the ```Chart Design``` ribbon should open. Click ```Select Data```; choose the Recurrence Interval data in column J as ```Series X Values```, and choose the water level data in column B as ```Series Y Values```.

Now, change the X-axis to logarithmic with a maximum value of 100 by right clicking on the X-axis, choosing ```Format axis```, and selecting ```Logarithmic Scale``` in the panel which appears; then at the top of the panel, enter 100 as the ```Maximum under Bounds```.

Add a power trendline which extends to a Recurrence Interval of 100 years by right clicking on the data points on the graph and selecting Add Trendline; in the trendline options, choose ```Power```, and enter 100 as ```Forward``` under ```Forecast```; also select ```Display Equation On Chart```.

You should now see a curved trendline on your graph through all points, and extending to 100 years on the X-axis. 

What is the water level where the trendline reaches 100 years? This is the forecast water level for a 100-year flood event. You can also use the trendline equation to calculate the value more exactly. The equation should be in the form <code>y = a*x<sup>b</sup></code>; or to use the terms, <code>water level = a * recurrence interval<sup>b</sup></code>. Calculate the water level y for recurrence interval x = 100 years (i.e. <code>a * 100<sup>b</sup></code>).

That's the first water level you'll use to make a flood risk map.

For your second flood risk map, choose a different recurrence interval. You might want to map an even larger flood - say a 500-year flood, or a 1000-year flood. Or perhaps you might like to compare your 100 year flood to something which might happen more often, say a 10-year flood, or even a 1-year flood. Use the same <code>water level = a * recurrence interval<sup>b</sup></code> formula to calculate your second water level.

Now we can go back to QGIS and make the maps.


___
[Previous](./16_DEM_hillshade.md) | [Next]()