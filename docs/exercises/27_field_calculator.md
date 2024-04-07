![UL Geography logo](../assets/images/GY4006_logo.png)

# 27: Calculating a new social class attribute ```[B-grades and above]```
___
You've previously looked at the attribute data for the census layers, and should have seen the columns of census data they contain. If you scrolled all the way across, you would see a huge number of fields. Each of the numbers is a number of households or people – with the columns each representing a different census question. For example, there’s a column for each age group. There’s also columns for different types of occupations, health, how people commute, and every other question asked on the census.

Just looking at the column names, however, it's not obvious what each column represents. They all have names like ```T11_1_TDLW```. Obviously, we need a key to understand what each column represents. 

In fact, you should already have it. In [task 25](25_census_data.md), you should have downloaded the census glossary spreadsheet. If you look at the list of column names in that, you should see that ```T11_1_TDLW``` is ```Theme 11, Table 1: Population aged 5 years and over by means of travel to work, school or college - Train, DART, or LUAS to Work```. Have a look through the glossary file to see the range of questions asked in the census for which you now have data for your area.

Because you joined the census data tables to the census vector polygons, you now have all the census results for each area as an attribute of each small area polygon. If you want to find out more about who would be affected by the potential flooding you have mapped - well, there's plenty in here you can explore.

What you'll notice about many of the columns, though, is that wouldn't necessarily be the most useful to map them by themselves. To continue with the same example, creating a map based on the ```T11_1_TDLW``` column would tell you how many people were using some forms of public transport - but not all. It doesn't include people who get the bus to work. It also doesn't include all train, DART, or LUAS commuters: there's also people who would take the train, DART, or LUAS to school or college.

So, usually, it's much more informative to combine data from a few different columns. To continue this example, you might combine ```T11_1_TDLW``` with ```T11_1_BUW``` (bus to work), ```T11_1_TDLSCCC``` (Train, DART, or LUAS to school, college, or childcare), and ```T11_1_BUSCCC``` (bus to school, college, or childcare) to get the total numbers of people in each small area commuting by public transport. 

A total number like this can be useful - but if you're trying to compare the differences between small areas, you might prefer to have these numbers as a percentage of the total number of people in the area. In this example, you'd then also want ```T11_1_TT``` - the total number of people for that table.

In doing any analysis of this kind, the first step is looking at the data, and deciding what you need. That's the hard part. Once you've identified which data you want to use, and how you're going to use it, actually implementing that in QGIS is relatively straightforward.

In the case of your map, looking at commuting habits might be useful, but the objective we're trying to answer is ```Is there a socioeconomic bias to who is vulnerable to fluvial flooding in Ireland?```. So, for that, we'll want to look to ```Theme 9: Social Class and Socio-Economic Group```. In this theme, the data includes counts for the number of people in various categories of occupations. So, let's calculate the percentage of workers in each small area with an occupation in the generally lower-income Non-manual, Skilled manual, Semi-skilled, and Unskilled categories.


## Processing the Data
___
Calculating that percentage would involve adding together the numbers for Non-manual, Skilled manual, Semi-skilled, and Unskilled workers, dividing the result by the relevant total, and multiplying by 100 to convert the proportion to a percentage. 

Step 1 is identifying which columns of data are needed. So, in the census glossary spreadsheet, find the column names for the total numbers of Non-manual, Skilled manual, Semi-skilled, and Unskilled workers, plus the total from the same table.

Then in QGIS, first click on your census layer in the Layers panel to make it the active layer; then find and click the **Field Calculator** button in the toolbar (it looks like an abacus - red, green, and blue coloured circles on horizontal lines).

In the Field Calculator window, first ensure that ***Create a new field*** is selected. Your new attribute will need a name - so choose a relevant name, and type it in the ***Output field name*** box. 

The result of your calculation is going to be a number representing a percentage, and it's unlikely to be a whole number - so set the ***Output field type*** to ```Decimal number (real)``` (this is a variation of the *floating point number* data type discussed in the <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/GY4006_2_Data_Types.ipynb" target="_blank">Data Types notebook <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>.

Now, go to the Expression box below. Here is where you need to construct your formula to calculate the new attribute. This should take the form:

```( ( Non-manual + Skilled manual + Semi-skilled + and Unskilled ) / total ) * 100```

For the ```(```, ```)```, ```+```, ```/```, ```*```, and ```100```, you can just type those into the expression box in the right place. For the data attributes, you can find them in the box to the right, under **Fields and Values**; and you can type the column name into the search box to find them. Double-click the name in the list to add it to the Expression box.

When you have the formula constructed, click OK. This will toggle editing On for the layer - toggle it Off again by clicking the yellow pencil icon in the toolbar, or right-clicking the layer in the Layers panel, and choosing *Toggle Editing*. THis will save the layer with your new attribute.

Now you're ready to make a map with your new attribute!

Save the project before continuing.

## A second new attribute  ```[A-grades]```
___
There's a lot more data in the census layer - much of which would add some useful information towards the research objectives and research question. Using the glossary, choose a second aspect of the census data, identify which columns of data you'll need and how you'll use them, and repeat the above process using the Field Calculator to create a second new attribute of your choice.


___
[Previous](./26_join_census.md) | [Recommended order of tasks](./start.md#recommended-order-of-tasks) | [Next](./28_thematic_map.md)