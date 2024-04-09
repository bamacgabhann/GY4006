![UL Geography logo](../assets/images/GY4006_logo.png)

# 02: Water Level Monitors ```[C-grades and above]```
___

If we want to know about flooding, a map of the rivers is useful, but it’s only a starting point. Floods happen when the water level in the rivers gets too high. So is there any data about the water level in rivers? Yes there is – the OPW (Office of Public Works) is the office responsible for monitoring flooding in Ireland, and they operate a network of sensors in Irish rivers to track the water level. We can download their location data from the OPW page on the Government’s Open Data website. In fact, what we’ll be downloading is the latest readings from all of their sensors, but we’ll be ignoring the latest readings and just using them for the location.

## Adding the Data
___

Go to [https://data.gov.ie/dataset/opw-hydrometric-network-water-level-data-latest-reading](https://data.gov.ie/dataset/opw-hydrometric-network-water-level-data-latest-reading)  and click ```Download```. 

If this opens what looks like gibberish in your browser instead of downloading, go back and right click on the ```Download``` button and click ```Save Link As``` to download it. 

If you get an error saying ```download.json can’t be downloaded securely```, click the up arrow and choose ```Keep``` – that’s just the browser not being used to this file type. 

Save the file to your GY4006 folder (if it saves to your Downloads folder by default, move it to your GY4006 folder). This data is in a vector format called JSON, which stands for Javascript Object Notation. This is a very common format for sending data over the internet. The new JSON file should appear in the Browser panel in QGIS. Click on the file in the Browser panel and drag it into the map canvas to add it to the project. You should now see this listed in the Layers panel, with a dot beside it, indicating vector point data. Right click on this layer and choose Rename Layer, and give it the name ```OPW```.

Save the project again (```Project > Save```, or click the 'save' icon, or use keyboard shortcut ```Ctrl-S```).


___
[Previous](./01_Adding_Rivers_Lakes.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./03_Adding_The_AOIs.md)