![UL Geography logo](../assets/images/GY4006_logo.png)

# 34: Multi-map Print Layouts ```[A-grades]```
___
Sometimes, you will have multiple datasets which you'd like to compare - but you can't put them on a single map, because one layer would hide or obscure another.

For cases such as these, you can do a side-by-side comparison by putting multiple maps on a Print Layout in QGIS.

Use this to create a layout showing both of your census thematic maps on the same page. Each of the two maps should have:
- One of your census thematic maps
- Water level monitors
- Rivers
- Lakes
- Your AOI
- Your buffer
- Your vectorised flood risk areas
- Your past floods digitised layer
- Any other useful elements independently added  ```[A1-grades]```
- DEM (if visible)

The layout should also have a North arrow, Scale bar, Title, and Legend; these elements can appear on each map individually, or they may be shared if appropriate (e.g. scale bar can only be shared if both maps are shown at the same scale).


## Presenting the Data
___

### Adding a second map to the Layout

At a fundamental level, this is not particularly complicated. Use the *Add Map* tool from the left toolbar to add one map - leaving enough space on the layout for a second. Select *Lock Layers* in the *Item Properties* of the map, then return to the main QGIS map canvas, and change which layers are visible. Return to the print layout, and ue the *Add Map* tool from the left toolbar again to add a second map. Since you locked the layers of the first map, it will continue to show the original layers; the second map will show the changed set of layers. 

You can also duplicate the existing map by selecting it, and then from the menu, choose ```Edit > Copy``` and then ```Edit > Paste```. This will create a copy of the map - you will need in this case to unlock the layers of this map, change the visibility of layers in the QGIS map canvas, then return to the print layout, refresh the view, and re-lock the layers. 

In this case, the only change necessary is to toggle off the visibility of your first census thematic map, and toggle on the visibility of the second.

You can do this by starting from a new, blank layout, and adding all the elements. 

Alternatively, you can start by duplicating a single-map layout. In this case, you can reduce the size of the existing map to leave space for a second map. Adjust the scale of the map as necessary to make it a round number, with your entire AOI and buffer visible. Then copy the map, and move the copy so that the two maps can be seen side by side. 

### Scale bar and North arrow

You can add a second scale bar and north arrow; these elements are linked to a specific map, and will change if you adjust the map they are linked to. If you select the scalebar in the Items list, you will see the first item under *Main Properties* is an option to select which map it is linked to. If you add a scale bar or north arrow to each map, ensure that they are linked to the correct map.

### Legend

Since most elements of the maps are shared, there is no need to duplicate the legend. You can have a single, shared legend which includes a key for both thematic maps, as well as all the shared items (rivers etc.). Alternatively, you can add multiple legend items - perhaps a shared legend for the shared items to go between the two maps, with a separate legend underneath each map for the census thematic themes. You will have already adjusted the legends for previous maps - adjusting a shared legend or multiple legends is done in the same way.

### Title

There is no need for multiple titles - but depending on your layout and legend choices, you may wish to use the **Add label** tool from the left toolbar (which you used to add a title) to add subtitles for each of the two maps.

### Save as PDF
When you've completed the layout, use the **Export as PDF** button in the main toolbar above to save a PDF copy. In the *Export to PDF* window, browse to your GY4006 folder, type an appropriate filename, and click Save. A *PDF Export Options* window will appear - you can leave all these options on default, and click *Save*. 


Save the project before continuing.

___
[Previous](./33_second_print_layout.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./35_report.md)