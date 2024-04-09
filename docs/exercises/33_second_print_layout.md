![UL Geography logo](../assets/images/GY4006_logo.png)

# 33: A second print layout ```[C-grades and above]```
___
You can't show all of your data on a single map - some of the features would be obscuring or hiding other features. So, you need to create a few different maps to properly present all of your data.

Of course, you can do this by simply creating a completely new Print Layout, and repeating the process from your first Print Layout to create a second map showing different data.

However, it's also possible to simply copy your first Print Layout, and change which layers are visible.

Repeat this as necessary to create:

-  ```[C-grades only]``` a layout showing your raster flood risk areas, with:
    - Your raster flood risk areas 
    - Water level monitors
    - Rivers
    - Lakes
    - Your AOI
    - Base map
    - DEM
    - North arrow
    - Scale bar
    - Title
    - Legend
  
- ```[C-grades and B-grades]``` a layout showing your census thematic map, with:
    - Your census thematic map
    - Water level monitors
    - Rivers
    - Lakes
    - Your AOI
    - DEM (if visible)
    - Your buffer  ```[B-grades]```
    - Your vectorised flood risk areas  ```[B-grades]```
    - North arrow
    - Scale bar
    - Title
    - Legend
  
- ```[B-grades and above]``` a layout showing your satellite data, with:
    - Your downloaded satellite data visualisation  ```[B-grades]```
    - Your satellite data visualisation or custom land use map created in QGIS ```[A-grades]```
    - Water level monitors
    - Rivers
    - Lakes
    - Your AOI
    - Your buffer
    - Your vectorised flood risk areas
    - Your past floods digitised layer  ```[A-grades]```
    - Any other useful elements independently added  ```[A1-grades]```
    - DEM (if visible)
    - North arrow
    - Scale bar
    - Title
    - Legend
  
- ```[A-grades]``` a layout showing your georeferencing (such that all edges of the georeferenced screenshot can be clearly seen and compared to the base map), with:
    - Your georeferenced raster
    - Base map
    - North arrow
    - Scale bar
    - Title
    - Legend
  
- ```[A1-grades]``` any other layouts required to show all your independent work.



## Presenting the Data
___
Open your first Print Layout. If you had it closed, you can reopen it by choosing ```Project > Layouts > *your print layout name*``` from the menu. 

Before doing anything else, right click on the map in the layout, and choose **Item Properties**. In the Item Properties panel, scroll down to find the *Layers* section, and select ```Lock Layers```. This will ensure that any changes you make to layer visibility in the QGIS map canvas do not affect what is shown in this Print Layout.

Now, from the menu in your Print Layout, choose ```Layout > Duplicate Layout```. A dialog box will open asking for a name: give something appropriate for the data you will have on this Layout. When you have entered a name, click OK, and the new layout will open.

The new layout will be identical to your previous layout - so, you can make whatever changes you need to which layers are visible, or what is shown in the legend, but don't have to repeat adding the map, adjusting the scale, creating scale bar and north arrow, and so on.

### Changing which layers can be seen on the map

To change which layers are visible, right click on the map in the layout, and choose **Item Properties**. In the Item Properties panel, scroll down to find the *Layers* section, and deselect ```Lock Layers```. Now, return to the QGIS map canvas, and in the Layers panel, toggle off the visibility of any layers which you do not want to be shown on this new Layout; and toggle on the visibility of any layers you do want to show. When you've changed the visibility of any layers you need, return to your new Layout. You may not see the changes reflected immediately; if not, click the **Refresh** button in the toolbar above.

If the Layout is now showing the layers you need, go back to the Item Properties for the map and re-select ```Lock Layers```. 

### Updating the legend

If you have added or removed any layers from the map, you will need to add or remove the relevant layers from the legend as well. Right click on the legend and choose **Item Properties**, and in the Item Properties panel scroll down to find the *Legend Items* list. 

To remove a layer from the legend, click that layer in the *Legend Items* list, and then click the *Remove Selected Item(s) from Legend* button (red minus button) beneath the list.

To add a layer to the legend, click the *Add Layer(s) to Legend* button(green plus button) beneath the list; you can then choose the layers you wish to add in the *Add Layer to Legend* window which appears. Select the layers you want, and click OK to add them to the legend. 

You can use the up and down arrow buttons beneath the list to move layers up or down in the legend, and can again adjust names, symbols, fonts, number of columns and more using other options in the legend *Item Properties* panel.

### Updating the Title

To change the title, right click on the title and choose Item Properties. You can then change the title text in the *Main Properties* section.

### Save as PDF
When you've completed the layout, use the **Export as PDF** button in the main toolbar above to save a PDF copy. In the *Export to PDF* window, browse to your GY4006 folder, type an appropriate filename, and click Save. A *PDF Export Options* window will appear - you can leave all these options on default, and click *Save*. 


Save the project before continuing. Repeat the process to create any additional layouts required.


___
[Previous](./32_print_layouts.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | ```[C-grades and B-grades]```[Report](./35_report.md) | ```[A-grades]``` [Next](./34_multi-map_layouts.md)