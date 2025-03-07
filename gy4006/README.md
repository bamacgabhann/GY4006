![UL Geography logo](./assets/images/GY4006_logo.png)

# GY4006: GIS and Geospatial Data Analysis
___

Welcome to the supporting materials for the geospatial / GIS component of module GY4006. In this module, you'll be using computer software to map geospatial data. 



## Part 1 - Notebooks
___

The exercises for this module involve analysing data and creating maps using GIS. In order to understand what you are doing, you need to learn some of the key concepts in working with GIS and geospatial data - like what do we mean by "data", what are the different kinds of geospatial data, how is it stored and accessed on the computer, what kinds of analysis are possible, and more. 

So, to supplement the lectures, I have compiled the background information into a series of online Notebooks. These have some explanatory text and sections of Python code which are run to illustrate various examples. Don't worry - you don't need to write, learn, or understand the Python code itself! It's all pre-written. You only need to see what it produces.

There are two ways of using these Notebooks. 

1. You can simply read them as an online book, looking at the explanatory text and the outputs (which are usually maps, or tables of data). In this case, you can pretty much ignore the code, and just look at what it produces.
2. You can run them interactively on Google Colab, to produce the results as you read.

Using Google Colab is easy and free - you don't need to install anything, all you need is a Google account, and you can open it on any internet connected device. Running the Notebooks interactively on Google Colab is the far superior option, because it's more interactive - plus, you can change things if you want to play around a bit to figure things out.

I know the temptation for many will be to think "well, there's no marks for this" and either go through them just to go through them, or even skip them entirely. If you do this, and don't actually use them to learn the concepts, then you really won't understand what you're doing in the exercises; they'll be much harder, and will take you longer to complete than the time it would have taken to go through the Notebook content first and actually learn from them, and then do the exercises. 

There are 10 Notebooks to work through. The first is just a written introduction - the other 9 contain code cells to run as well as the explanatory text.

1. [Geospatial Software and Programming Languages](notebooks/GY4006_1_Geospatial_Software_and_Programming_Languages.ipynb)  

2. [Data and Data Types](notebooks/GY4006_2_Data_Types.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_2_Data_Types.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

3. [Vector Data](notebooks/GY4006_3_Vector_Data.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_3_Vector_Data.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

4. [Attribute Data](notebooks/GY4006_4_Attribute_Data.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_4_Attribute_Data.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

5. [Coordinate Reference Systems](notebooks/GY4006_5_Coordinate_Reference_Systems.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_5_Coordinate_Reference_Systems.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

6. [Geospatial Data Files](notebooks/GY4006_6_Geospatial_Data_Files.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_6_Geospatial_Data_Files.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

7. [Vector Geoprocessing](notebooks/GY4006_7_Vector_Geoprocessing.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_7_Vector_Geoprocessing.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

8. [Introduction to Raster Data](notebooks/GY4006_8_Introduction_To_Raster_Data.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_8_Introduction_To_Raster_Data.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a> 

9. [Single-band Raster Data](notebooks/GY4006_9_Single-band_Raster_Data.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_9_Single-band_Raster_Data.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

10. [Multi-band Raster Data: Passive Remote Sensing](notebooks/GY4006_10_Multi-band_Raster_Data-Passive_Remote_Sensing.ipynb) <a href="https://colab.research.google.com/github/bamacgabhann/GY4006/blob/main/gy4006/notebooks/GY4006_10_Multi-band_Raster_Data-Passive_Remote_Sensing.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>



## Part 2 - GIS Exercise / Assignment
___

At the start of the module, you were given a Research Question plus Aims and Objectives:

**Research Question**  
What vulnerabilities to fluvial flooding exist in Ireland?

**Aims**  
To inform future flood hazard mitigation planning

**Objectives**  
What is people’s experience of fluvial flooding in Ireland?  
Is there a socioeconomic bias to who is vulnerable to fluvial flooding in Ireland?  
When is fluvial flooding most likely to occur in Ireland?  
Where is fluvial flooding most likely to occur in Ireland, and what is vulnerable there?  

You have addressed some of this in the survey task; we can now address the remainder through some mapping.

You will be assigned an individual area to work on. Everyone will be undertaking the same mapping, but on your own areas. So, you should be able to help each other out.

In order to address your objectives and help to answer the research questions, you're going to make some maps of your area - and analyse some of that map data. 

The point of this exercise - which will ultimately produce a portfolio of maps for your second assessment - is to introduce you to geospatial analysis, to show you some of what's possible using geospatial analysis, and to show you that you can do some geospatial analysis. Now, I understand that not everyone has the same targets in college - some of you want to get a top grade, while others might just be looking to get a C and pass. That's fine and entirely up to you - and so the way I've constructed this exercise / assessment breaks it down into different levels of tasks depending on what grade you are aiming to achieve.

You should by now have gone through the 10 Notebooks, and have some idea of the difference between vector Point, Line, and Polygon data, attribute data, and raster data. You should also have some idea of vector and raster geoprocessing, and of the potential for changing the symbology of the data, i.e. how the data is visualised.

To get a passing grade in the module, you will have to use all of these to some extent - and to get a B-grade or A-grade, you'll have to go into greater depth or detail.

The instructions here are broken down by what grade you're aiming for. [You can find the instructions here](./exercises/start.md).

