<img src="https://raw.githubusercontent.com/bamacgabhann/GY4006/main/GY4006_logo.png" align=center alt="UL Geography logo"/>

<h1>Rivers and Lakes</h1>

If we’re going to look at river flooding, an obvious place to start is mapping the rivers. We don’t need to do this ourselves, because other people have already done it, and we can simply use their maps. In Ireland, the EPA have responsibility for monitoring the status of waterbodies under the EU Water Framework Directive, so we can get maps of the rivers from them.

<h2>Adding the Data</h2>

Go to <a href='https://gis.epa.ie/GetData/Download'>https://gis.epa.ie/GetData/Download</a>, select ```Water / Water Framework Directive``` from the sidebar, and scroll down to find ```OSI Rivers and Lakes – 06/02/2020``` under Rivers and Lakes. Click the button to select it. At the bottom of the page, you will have to enter your email address twice, and click the button to confirm that you’re not a robot, and click Send to have a download link emailed to you. 

When the email arrives (it should be quick), click on the link to download a zip file. 

A zip file is a compressed archive file which can contain multiple files, stored in such a way that it reduces their size for storage or downloading. Before using the files stored in the zip archive, you must extract (or ‘unzip’) the contents. Extract the contents of this zip archive to your GY4006 GIS folder.

You will see there is a folder called ```Shapefiles``` containing 16 files. This data is in a vector format known as a shapefile. This data format uses multiple different individual files to store the complete dataset: you can think of this as one main .shp file which contains the co-ordinates, and additional files which describe what those co-ordinates mean.

Go back to QGIS and look at the Browser panel. Expand the Rivers and Lakes Shapefiles folder; you will see two shapefiles, WATER_RivNetRoutes.shp and WFD_LakeSegments.shp. First, right click on WATER_RivNetRoutes.shp and choose Add Layer To Project.

You will now see WATER_RivNetRoutes listed in the Layers panel, with a line beside it, to indicate that it is vector line data. You will also see the data in the map canvas – all the rivers in the 26 counties. 

Now add WFD_LakeSegments in the same way. This data should also be displayed now in the map canvas, and you should see WFD_LakeSegments listed in the Layers panel, with a coloured square beside it, indicating vector polygon data.

Save the project again (```Project > Save```, or click the 'save' icon, or use keyboard shortcut Ctrl-S).