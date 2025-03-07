![UL Geography logo](../assets/images/GY4006_logo.png)

# 32: Print Layouts ```[C-grades and above]```
___
Now you have a very nice looking collection of data. But it’s not much good just on your screen, you want to be able to show this to people. Perhaps you’d want to use this to create maps for a report (hint hint, those of you doing geography FYPs) – or maybe you might use this to make a map for a school field trip if you’re a teacher in future, or a map for orienteering, or planning a kayaking or hiking trip, or maybe you just want a nice map to share online or put on your wall. You can’t send people all the project files and tell them to install QGIS – you want to be able to save a PDF or an image. We can do this using the Print Layout tool.

You have several different final maps to create. This task will walk you through creating your first map.

## Presenting the Data
___

### Preparing to create your first Print Layout
The Print Layout will initially show whatever is visible on your map canvas. So, before doing anything else, you should right click your AOI ```[C-grades]``` or buffer ```[B-grades and above]```, and choose *Zoom to Layer*. This will set the extent of the map canvas to show your area filling the screen as much as possible.

You should also now adjust which layers are visible, so that the right data is shown on the map. For this first map, you want:

- the basemap
- the DEM
- the rivers
- the lakes
- the water level monitors
- your AOI
- your vectorised flood risk zones ```[B-grades and above]```
- your past floods digitised features ```[A-grades]```
- any appropriate elements added as an independent task ```[A1-grades]```

Make sure all these layers are visible, and other layers have visibility toggled off. 


### Creating the Print Layout
From the menu bar, select ```Project > New Print Layout```. Give the layout a name, and click OK.

The main map canvas you've been working with allows you to prepare a map digitally, and you can save what’s on the screen to an image. However, saving from the map canvas doesn’t include some elements which you would expect on a published map – for example, a north arrow, a scale bar, a title, a legend, or annotations. The Print Layout window allows you to add these items and more to the map, for saving as an image, or for printing.

The main window of the Print Layout displays the frame on which the map will be designed – this could be sized for a particular image, or for a sheet of paper. 

To the left, you will see buttons to add various items to the layout – map, pictures, labels, legend, scale bar, shapes, arrows. 

To the right are the Items list, which shows you a list of what you’ve added to the layout; and tabs for Layout Properties and Item Properties. 

At the top are buttons for exporting the composition, navigating within the composition and some other graphic tools (grouping/ungrouping etc).

Your first task will be to set the paper size. The default paper size should be A4 – right click on the page and select Page Properties, and you should see A4 listed as the page size. If you don’t, change it to A4. The default Orientation is Landscape – this might not suit everyone, some of the areas are long and thin. Change it to Portrait if it suits your area better.

Now you can start to add elements to your layout, using the buttons on the left. Moving the mouse cursor over any of these buttons will produce a small tool tip to appear with the name of the tool. 

### Adding the map
The most obvious thing your map will need is, well, a map. Find the **Add map** tool and click to select it. Now, use the mouse to click and drag a box on the page where you’d like the map to go. You want people to be able to see the map as large as possible - but remember that you’ll need room for a title, a scale bar, a north arrow, and a legend. You can adjust the size later if you need to, so don't worry too much - you can also put elements such as the north arrow and scale bar on top of the map, as long as they can be seen clearly.

With the map selected, click on the **Item Properties** tab. You should see a series of buttons across the top of this panel for controlling the map extent. Again, hovering the mouse cursor over these will show the name of each tool. Click the *Set Map Extent to Match Main Canvas Extent* button. This will do what it says - it will set the map on the Print Layout to show the same extent which is currently visible in the main QGIS map canvas. If you have the main map canvas showing the full extent of your area, the Print Layout map should now change to show just your area. If not, go back to the main QGIS window, right click on your AOI or buffer and choose *Zoom to Layer*, then return to the Print Layout and click the *Set Map Extent to Match Main Canvas Extent* button again.

This is good, but you should see now that **Scale** is set to an awkward number. We’d prefer a nice round number, preferably ending in three or more 0s. You can just click in the box to edit the number; try changing it until have a nice round number for the scale, with your full area visible on the page.

If you need to change which part of the map you can see, use the **Move Item Content** button from the left toolbar. This allows you to move the map content in the map frame without changing where the map is on the page. It’s normal to have to adjust it a bit. 

### Adding a legend
You have multiple different layers on your map; anyone looking at the map will need a key to understand what features are being represented on the map, and how they are represented. 

In the left toolbar, find the ***Add new legend** tool, and use it to drag a box on the page where you want your legend to go.

Your legend will appear - but it will run well off the page. You need to do some tidying to make it usable. For a start, there are many layers in your project which aren't shown in this map - so they don't need to be in the legend. There's also some items in the legend which need clearer names.

In the **Item Properties** window for the legend, find and deselect the **Auto Update** option under *Legend Items*. Once you've done that, you can remove any layers which you don't need included in the legend by clicking on the layer in the *Legend Items* panel, and clicking the **Remove Item** button (the red minus). If you remove something by mistake, you don't need to start again; you can add them back with the **Add Layer(s) to Legend** button (the green plus).

You can change the order of items in the legend by clicking on the layer you want to move, and using the *Move Item Down* and *Move Item Up* buttons (blue up and down arrows) beneath the list. 

You can change the name of a layer in the legend by clicking on the layer you want to rename, and using the *Edit Selected Item Properties* button beneath the list (looks like a pencil writing on a page). 

Further down the **Item Properties** for the legend, you can find options to change the fonts, split the legend into columns, adjust the spacing, add a background or a frame around the legend, and many other formatting options. You can adjust these as needed until you're satisfied.

### Adding a title
Your map needs a title. Use the **Add new label** tool from the left toolbar to drag a box on the page where you'd like the title to appear. The text box can be resized by clicking and dragging the squares at the corners and middles of each side. By default the text box will have the placeholder text *Lorem ipsum*. Using the *Item Properties* tab, *Main Properties* section, replace this text with an appropriate title.

In the *Appearance* section of the *Item Properties*, you can click the *Font* button to open the *Text Format* window. Change the font and size to something appropriate. Below the font settings are some alignment settings; you can use this to set the Horizontal and Vertical alignment, depending on where you want the title on your page.

### Adding a scale bar
Every map needs an indication of scale, so that anyone looking at the map has a visual guide to the size of features on the map. In the left toolbar, find the **Add Scale Bar** tool, and use it to drag a box where you want the scale bar to go on the page. 

In the scale bar’s *Item Properties*, you have many options for customising the scale bar. I suggest changing the units to kilometres; you can also increase the number of segments, change the height, change where labels are positioned, and more. Again, you can tweak this until you’re satisfied.

### Adding a North arrow
Every map also needs an indication of orientation - typically using a north arrow. Find the **Add North Arrow** tool in the left toolbar, again clicking and dragging a box to the location and size you want. You can customise this as well - you should have options for a couple of different north arrow styles, and can change the colour, outline, alignment, and more, until you're satisfied.

### Save as PDF
That should be all the elements you need - so you should be ready to save the map. In the main toolbar at the top, find the **Export as PDF** button and click it. In the *Export to PDF* window, browse to your GY4006 folder, type an appropriate filename, and click Save. A *PDF Export Options* window will appear - you can probably leave all these options on default, and click *Save*. 

You should get a message to say that your map has been saved, with a link to the saved PDF. Click the link to open the PDF to check how it looks. You can go back and change anything you want, and save it again if needed; if you're satisfied, congrats! You've prepared your first final map. You can move on to your next map.

Save the project before continuing.

## Going Further
___
You can find more information about the tools and options in the Print Layout composer in the QGIS documentation.

More info: [QGIS User Guide / 22.1. Overview of the Print Layout](https://docs.qgis.org/3.34/en/docs/user_manual/print_composer/overview_composer.html)

___
[Previous](./31_self_directed.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./33_second_print_layout.md)