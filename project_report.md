

CSC110 Final Project:

Investigating the Implications of CO2 Levels on the Number of Forest

Fires in the US

Group Members: Leya Abubaker, Armaan Mann, Ansh Malhotra, Gabriel Pais

Monday, December 14, 2020

1 Introduction

1.1 Problem Description and Research Question

Research Question: Is there a correlation between CO2 Emissions and the Frequency of Wildﬁres in

the US?

Greenhouse gases are gases that trap heat inside the Earth’s atmosphere. Carbon Dioxide makes up most of the

greenhouse gas emissions in our world and is emitted through the burning of fossil fuels such as petroleum (“Overview

of Greenhouse Gases”, 2020). The United States was ranked second in the world’s CO2 emissions, which produced

approximately 5,269.5 million metric tons in 2017 (Frohlich and Blossom, 2019). Greenhouse gases, like carbon

dioxide, are major factors of global warming because they cause the Earth’s temperature to rise which can lead to

an increase in many forms of natural disasters (Osmanski, 2020). In particular, the hot and dry temperatures cause

the vegetation in forests to dry out and it increases the risks of forest ﬁres and the damages that it can cause. Forest

ﬁres can also increase the emissions of CO2 in the atmosphere, which continues to increase the global temperature

and in turn increases the frequency of extreme weather events (Gray, 2019).

It is important to note that the majority of forest ﬁres are caused by humans, so our project topic seeks to de-

termine whether CO2 emissions have an impact on the frequency of forest ﬁres and how much of an impact it may

have. We chose to study the relationship between CO2 emissions and the frequency of wildﬁres because we noticed

that there have been an increase of forest ﬁres reported in the news, especially in the US, and from our research we

discovered that the US CO2 emissions are very high. So, we wanted to determine if there is an actual connection

between the increase in the occurrences of wildﬁres in the US, to the amount of CO2 that is emitted. The project

topic that we wish to analyze directly relates to climate change because the damage that natural disasters, like forest

ﬁres, cause are increased due to global warming. So the focus for our project is to determine whether larger emissions

of CO2 speciﬁcally correlate to a higher frequency in forest ﬁres.

Changes Made from Original

Based on the feedback provided from the TA we reformulated our question into determining if there is a correlation

between CO2 emissions and forest ﬁres. To answer this question, instead of plotting a linear regression we decided

to plot a bar graph that displays the CO2 emissions of a particular state with a line graph that plots the number of

forest ﬁres that occurs each year. We also included a separate graph that displays this information for the United

States. From these plots we analyzed the trend between the year with the highest level of CO2 emissions and the

year with the highest number of forest ﬁres to check if our hypothesis is correct. In addition, we also changed our

ﬁnal output and computation. Instead of just producing a heat map, we decided to create a map of the US that

displays the amount of forest ﬁres that occurred in each area as clusters for one entity with the addition of a heat

map. In which each zoom level has more information for a particular location of the forest ﬁre. As well as an

interactive portion that shows extra information about the forest ﬁres in that particular state and provides a link

to extra information about the forest ﬁres. The heat map allows the user to ﬁlter to either the Vegetation, Fire

Magnitude, Wind at that time and Humidity at that time as a layer on top of the pre-existing map, to show how

various areas of the US are eﬀected.

1





1.2 Dataset Description

\1. We have used four datasets for this project, we manually created all of them. The ﬁrst one is the US Wildﬁre

Data (under the name of FireData5yrs.csv), which is used to create the US map and shows the values for each

forest ﬁre with its respective data. The dataset has been ﬁltered to just 5 years to maintain performance and

ensure that the graph is still interactive, any more than that would ﬁll the map with over 35,000 forest ﬁres and

would take a tremendous amount of time to load. This dataset contains the year when the wildﬁre occurred (

2010 - 2015), the state where the wildﬁre happened ( LA, MS, NY. . . ), the ﬁre size, ﬁre size class, the latitude

and longitude, vegetation, ﬁre mag, wind cont. See legend for details on what each value represents.

\2. The second dataset represents the same Wildﬁre Data (called FireData10yrs.csv), it contains the same values

as the previous dataset (FireData5yrs.csv), except for years. This data set is used to state names and the year

from the variables state name and Date (Year). We have ﬁltered this data to just 10 years (2005-2015) by

removing all empty lines and cutting out almost half of our original dataset.

\3. Our third dataset is a CO2 data set (named CO2 DataSet.csv). This dataset contains information about each

state with the level of CO2 emissions for each year between 2005 and 2015 inclusive. This dataset was also

ﬁltered to 10 years from 2005 to 2015.

\4. The last dataset has the name overlay.json and contains coordinates manually taken by us of the US border.

The ﬁle is used in our mapping to show the border of the United States.

All these ﬁles are csv ﬁles except the last one which is a json ﬁle.

We got our datasets from the following sources:

• “U.S. Wildﬁre Data (plus Other Attributes).” Kaggle, 6 Oct. 2020, www.kaggle.com/capcloudcoder/us-

wildﬁre-data-plus-other-attributes.

• The source of the CO2 Data is from the following website: https://www.eia.gov/environment/emissions/state/

• The source of the coordinates data is from the following website : www.geojson.io

Legend:

• Vegetation - Type of Vegetation. 1:Tropical Evergreen Broadleaf Forest, 2:Tropical Deciduous Broadleaf For-

est, 3:Temperate Evergreen Broadleaf Forest , 4:Temperate Evergreen Needleleaf Forest TmpENF,5:Temperate

Deciduous Broadleaf Forest,6:Boreal Evergreen Needleleaf Forest,7:Boreal Deciduous Needleleaf Forest, 8:Sa-

vanna , 9:C3 Grassland/Steppe, 10:C4 Grassland/Steppe, 11:Dense Shrubland 12:Open Shrubland, 13:Tundra

Tundra, 14:Desert,15:Polar Desert/Rock/Ice, 16:Secondary Tropical Evergreen Broadleaf Forest, 17:Secondary

Tropical Deciduous Broadleaf Forest, 18:Secondary Temperate Evergreen Broadleaf Forest, 19:Secondary Tem-

perate Evergreen Needleleaf Forest 20:Secondary Temperate Deciduous Broadleaf Forest, 21:Secondary Boreal

Evergreen Needleleaf Forest, 22:Secondary Boreal Deciduous Needleleaf Forest, 23:Water/Rivers Water 24:C3

Cropland, 25:C4 Cropland, 26:C3 Pastureland, 27:C4 Pastureland, 28:Urban land

• Fire size = the size of the ﬁre

• Fire size class = class of the ﬁre size (A - G)

• Latitude and Longitude = coordinates of the ﬁre on the map

• Fire mag = the magnitude of ﬁre intensity (scaled version of ﬁre size)

• Wind cont = wind in m/s at the location of ﬁre up to the day the ﬁre was contained

• Hum cont = humidity in percent at the location of the ﬁre up to the ﬁre was contained.

• Remoteness = the distance to the closest city

• Urls = diﬀerent links representing information about ﬁres from diﬀerent states, each state has a diﬀerent url

2





Computational Plan

To start oﬀ, we looked at the datasets called raw ﬁredata and raw co2 data. The raw data from the ﬁre dataset

was huge with many columns and numerous rows. Due to this, we had to shrink the domain of the years to 5 years

and 10 years. The two datasets are used throughout the code for visualizations and graphs. Speciﬁcally, the 10

year data set is used for the bar plot with line in plot.py and the 5 years dataset is used for the map.py. Next, to

obtain these smaller domain datasets, the raw sets were ﬁltered to 2005 to 2015 and all the empty cells along with

the rows they belonged to were removed. Likewise, the same steps were repeated for the other ﬁre dataset but for

only 5 years from 2010 - 2015 inclusive. In the ﬁle FireData5yrs.csv, we removed all the empty cells and respective

rows and also added one url for each state manually, and the column names were just ﬁltered to latitude, longitude,

ﬁre size, vegetation, ﬁre magnitude, wind contained at that time, humidity contained at that time and remoteness

(Same thing was done for FireData10yrs.csv but no urls were manually inputted as that ﬁle is used for the line bar

plots).

Since all the datasets were stored as csv ﬁles, the library import csv was used to extract the data from the ex-

cel ﬁle. There are 3 functions altogether which collects the data from the csv ﬁle and then stores the data into the

dictionary, with its keys being the column names, which are as follows: read data ﬁre (for 10 years from the forest

ﬁre dataset), read data co (for the CO2 data set) and read data map (for 5 years from the forest dataset). The data

wrangling for the forest ﬁres were made in two diﬀerent ﬁles because when creating the map there were too many

values which was causing the program to load for too long and eventually crashing chrome and pycharm. Therefore,

we decided to shrink the domain to 5 years. All the data wrangling was done in main.py.

Next, our program has two visualizations: one is based on states and another one is generalized to all of the US.

To begin, the get data ﬁre is used to get the number of years from the FireData10yrs.csv using the data wrangling

function called read ﬁle ﬁre which also obtains the y-values (ﬁre frequencies gets added per state) which is used for

the line graph portion. Also, the function get data co2 is used to collect the values for the bar graph portion of the

plot. The y-values in this case are obtained from the CO2 DataSet.csv from 2005 to 2015. Finally, we also used a

helper function which is used to add all the forest ﬁre frequencies using the FireData10yrs.csv. All the functions are

also in main.py.

Furthermore, the second ﬁle that was created just for the plots is called plots.py. This is the ﬁle which contains the

major visualization of the line bar plot. The ﬁle contains two functions that perform the visualization. The ﬁrst

function, state plot, displays a line bar plot that displays the relationship between CO2. emissions of a particular

state (chosen by the user) and the number of forest ﬁres in that state. The second function, entire plot, displays a

line bar graph that shows the relationship of CO2 emissions for the US as a whole and the total number of forest ﬁres

occurrences in the US. These visualizations were created using the plotly library. Speciﬁcally, we used the libraries

plotly.graph objects and plotly.subplots functions to help display our visualizations of the graphs. We decided to

use the plotly library because it has more features and is more interactive compared to other libraries. The data is

then analyzed by the functions check trend and check trend all which returns whether or not the data we collected

follows the trend we initially predicted.

For Map.py, the major computations performed were in regard to data wrangling. Firstly, we needed to orga-

nize and store the data from ‘FireData5yrs.csv’ in a way that would allow us to place markers on the map according

to the wildﬁre’s latitude and longitude. Therefore, out of the raw dataset, only latitude, longitude, ﬁre size, vegeta-

tion, ﬁre magnitude, wind contained at that time, humidity contained at that time and remoteness were stored. A

data frame was created to store all these key value pairs to be used in the map which is used by the library called

pandas.

Secondly, the os library was used to implement the json ﬁle in the visualization. First oﬀ, the json ﬁle called

overlay.json was created through a website that allowed the user to outline a certain area of the world map and then

after selecting the area stored the coordinates. Thus after transferring the coordinates to a json ﬁle, using the os

library we were able to add the outline to the map we created.

Next, the main library that was used to construct the visualization was folium. The following methods were

used from the folium library: folium.Map(), folium.plugins.MarkerCluster(), folium.Marker(), folium.GeoJson(),

folium.plugin.MiniMap(), folium.Fullscreen(), folium.TileLayer(), folium.LayerControl(), m.save(), folium.Choropleth().

Comments are attached to the code itself for more descriptive uses of the methods mentioned above.

3





Instructions: main.py and plots.py

\1. To begin you need to install the plotly package and the csv package. To do so, start oﬀ by opening Pycharm

and going to File → System → Project → Python Interpreter, click the add button and type plotly into the

search bar and click install to install the package. Do the same for the csv package.

\2. Next, with the ﬁles provided through Markus, download main.py, plots.py, FireData10yrs.csv and CO2 DataSet.csv

into the same folder. For the raw Fire Data and CO2 Data, check UTSend and download the data if needed(you

will not need the raw data to run this ﬁle or have any functions that use the raw data)

Claim ID: dUP2g9A9zepxR8ai

Claim Passcode: nBN2Auw8Dt9zNSfN

\3. Ensure that the folder in which you store all the ﬁles in is a source root folder, do not create a sub-folder since

it’s not needed.

\4. Import the libraries, check the requirements.txt ﬁle for all the libraries and their corresponding versions.

\5. In the main.py python ﬁle:

• The functions read file co and read file graph are used for data wrangling, it can be called to view the

processed data as a dictionary. In order to call the function, read file graph the user must call the function

in the console and pass “FireData10yrs.csv” as the argument to view the processed data. In order to call

the function, read file co the user must call the function in the console and pass “CO2 DataSet.csv” as

the argument to view the processed data (make sure to include quotations). It includes helper functions

to get the points of each plot. The functions get data fire and get data co2 is used to return the x and

y-values for the line and bar graph per state. To call these functions, the user must pass a state name in

the form of an abbreviation as a parameter. For example New York - ‘NY’, Florida - ‘FL’. Finally, the

helper function total fire is used to obtain the y-values of the total number of forest ﬁres in the US.

\6. In the plots.py python ﬁle:

• The function state plot is used to display the graph of a particular state. When calling this function the

user must pick a state that they would like to see a graph of and pass its abbreviation as a parameter.

For example New York - ‘NY’, Florida - ‘FL’.

Untitled.png

4





• The function entire plot is used for the second visualization. It displays a bar and line graph representing

the total number of forest ﬁres in the US in comparison to the total CO2 emissions of the US per year

(this function does not have any required parameters).

usa.png

• The function check trend requires the user to pass a state abbreviation as a parameter. The last two

functions, check trend and check trend all are used to analyze the plots and determine whether or not

the data proves our hypothesis.

Instructions: Map.py

\1. To begin, you need to ﬁrst install the folium package

\2. Start oﬀ by opening Pycharm and going to File→ System → Project → Python Interpreter, click the add

button and type folium into the search bar to install the folium package. Alternatively, you can also type

pip install folium in the Pycharm terminal.

\3. Next, with the ﬁles provided through Markus, download map.py, overlay.json, requirements.txt, FireData5yrs.csv

into ONE folder. For the raw FireData, check UTSend and download the data if needed (you will not need the

raw data to run this ﬁle or have any functions that use the raw data)

\4. Ensure that the folder in which you store all the ﬁles in is a source root folder, do not create a sub-folder since

it’s not needed.

\5. Import the libraries, check the requirements.txt ﬁle for all the libraries and their corresponding versions.

\6. Also, the overlay.json ﬁle should be left alone, it is simply used to enhance the visualization created in this ﬁle.

\7. Now that we have done all the preliminary steps, there are two 2 functions within Map.py. Note that the two

functions within Map.py are called: read file map and make map.

\8. read file map can be called to view the processed data set, which has been formatted in the form of a Dict,

where the keys represent the columns within the FireData5yrs.csv, and the values corresponding to the keys

represent the data within the cells of the columns in the FireData5yrs.csv. Importantly, to call the function all

the user needs to do is call the function in the console and pass “FireData5yrs.csv” as the argument to view

the processed data.

\9. However, this function is optional, it is not needed for the subsequent function to work. This is just for

visualizing how the processed data looks like to have a better grasp over the wildﬁre data. If you do plan on

running the function, USE PPRINT, it’ll be easier to view the data.

5





\10. Finally, the last function remaining within the ﬁle is called make map, you can simply call it within the console,

without any arguments needing to be passed within the function call.

NOTE: It will take couple of seconds for the map to load, since the data is moderately large.

\11. After the function has successfully ran, you should be taken to your browser, where you should see an interactive

world map, speciﬁcally zoomed to where the US is the central focus (outlined) along with other US territories.

fullmapgood.png

Figure 1: Initial view of the map upon launch

\12. Once the html ﬁle loads, the initial result should look identical to the picture provided above. The map above

visualizes all of the information that was returned from the ﬁrst function, read file map and speciﬁcally the

(FireData5yrs.csv). Next, the map itself has a lot of features, ﬁrstly as you can see the circles on the map

represent clusters of forest ﬁres within a certain region. These dots are interactive, therefore by clicking one of

the circles, it zooms in the user and the circle expands to smaller circles, which once again representing smaller

clusters of forest ﬁres.

zoom1.png

Figure 2: After clicking on the 6000 Wildﬁre Cluster

6





\13. For example, the picture above is a result of clicking the 6985 dots(near Georgia/Alabama), which has now

expanded out to other smaller dots, as you can see the number of forest ﬁres within a cluster decreases every

time you click on it. This process can be repeated until there are no more clusters of forest ﬁres within a region

but instead a speciﬁc forest ﬁre.

zoom2.png

Figure 3: Zooming to a Speciﬁc Wildﬁre and Hovering Over it

\14. As shown above, the red ﬁre markers represent instances of forest ﬁres that happened at a certain location.

Further, these markers are also interactive, simply by hovering over the markers we can come to know that

it says “Click For More Information”. Hence, by clicking on the marker it provides informative information

about the speciﬁc forest ﬁre. Speciﬁcally, the marker popup provides insight towards ﬁre size, ﬁre magnitude,

vegetation, wind contained, humidity contained and remoteness (check the legend for more information on

the keywords). To add, a feature that was added within the popup was a hyperlink, the ﬁnal line in the box

relays additional information about forest ﬁres within the state the marker is in and by clicking the link “More

Details” it guides the user a link that provides that information

zoom3.png

Figure 4: Clicking on a Speciﬁc Wildﬁre Pops Open a Box

\15. Next, as you can see in the image below, in the top right portion of your screen there are many options available.

The ﬁrst two options are simply for zooming in and out (also possible by scrolling your mouse). The third

option is to full screen the map. Finally, the last option displayed below drops down a menu. Within the menu

7





the user can select a type of map to their liking and ﬁnally the last options work like ﬁlters. Where if you

do not want the outline of the US to be there, you can check the box oﬀ, similarly, if you do not want the

marks/clusters on the map you can also turn those oﬀ.

zoom4.png

Figure 5: Drop Down Menu on the Right Adds Additional Features to the Map

\16. As an extra bonus, you can toggle the heat map on and oﬀ by ﬁltering it with diﬀerent values, like Vegetation,

Fire Magnitude, Wind or Humidity. As well as a mini-map was created at the bottom which tracks your

movements as you navigated through the map. It also contains a toggle which allows the user to minimize it

using the diagonal arrow in the bottom right of the mini-map.

bOnus.png

Figure 6: Example a the Heat Map, ﬁltered on Vegetation

8





Discussion Section:

Do the results of your computational exploration help answer this question?

• The results of the computation did not prove our hypothesis that CO2 emissions has a correlation with forest ﬁre

frequency because through our implementation of the check trend all function and check trend, the visualization

proves that there is little to no correlation between the CO2 levels and the number of forest ﬁres in the US.

This trend can be understood by examining the major causes of wildﬁres within America. Concisely, the main

cause of forest ﬁres within the US is due to human factors, a study shows “Nearly 85 percent\* Wildland ﬁres

in the United States are caused by humans. Human-caused ﬁres result from campﬁres left unattended, the

burning of debris, equipment use and malfunctions, negligently discarded cigarettes, and intentional acts of

arson” (“Wildﬁre Causes and Evaluations”). Therefore, the results from the visualization are valid, as CO2

levels have little to no correlation with the number of forest ﬁres within an area. This discovery allows us to

conclude that there is not a visible correlation between CO2 emissions and the frequency of forest ﬁres in the

US. This is useful for future modelling because we can now try and ﬁgure out what actually has a direct impact

to forest ﬁre frequencies.

What limitations did you encounter with the datasets you found, the algorithms/libraries you

used, or other obstacles?

• Within the study conducted, there were many instances where the shortcomings of the visualizations were

due to limitations within the dataset and speciﬁc libraries chosen. First, the forest ﬁre data set created many

challenges during data wrangling. Due to the sheer size of the data (55, 000 rows), it made it challenging to

ﬁlter data to our needs, speciﬁcally, due to the access number of dates, it was time-consuming to ﬁlter the years

to a smaller domain.

• Additionally, both datasets also contained some blank cells. This was problematic, especially with the map, as

this meant that some information was missing when the markers were clicked. Therefore having to manually

remove rows which contained blank cells. Additionally, the FireData10yrs.csv was not used for the simulation

since the size of the ﬁle was signiﬁcantly larger than the 5 year data set and would simply take too long for

the html ﬁle to load.

• Next, the folium library also had many limitations. We were hoping to implement a toggle for time (years),

such that if an individual were to hit the “play” button it would cycle the forest ﬁres based on the years.

However, that was not possible with the package since the toggle is only available for heat maps, which did not

ﬁt the design we were hoping to achieve. Additionally, we wanted to implement hyperlinks within the marker

pop-ups, thus through extensive research, we came to know that no method/call within folium would allow us

to create hyperlinks, thus we had to end up implementing the hyperlinks using HTML (language), which was

tedious since it required extra research for the implementation.

• Furthermore, there was a major issue with the “level of detail” in the map, we hoped to have the markers

decrease when zooming out and increase when we zoomed in. This task was essential due to the sheer size of

the data and to prevent lag and increase usability of the map. This was originally intended to be an easy task

as the leaﬂet (interactive JavaScript library for maps) contained a simple function .getZoom(), which would

allow us to implement our intended idea. However, the same function or something similar to that was not

part of folium, therefore, reading through the folium documentation, we were able to ﬁnd something similar to

getZoom() that implemented clusters of markers instead.

• Moreover, some obstacles that we faced when trying to create the graph visualizations was when we were trying

to plot our original csv ﬁle that contained information of the CO2 emissions for cars and trucks we realized

that the data was inaccurate and did not contain the information we needed. To remedy this, we found a new,

reliable data set that represents the CO2 emissions for each state per year and plotted that information to

draw our ﬁnal conclusion.

What are some next steps for further exploration?

• Some next steps we can take to further explore our problem domain is to ﬁnd a dataset that covers forest

ﬁres and CO2 emissions from 2021. We can also try and analyze data for other countries and compare the

results in order to verify if the conclusion we drew form the results were accurate and come up with the actual

reasoning behind why certain countries may have higher or lower amounts of forest ﬁre. Potentially, we can

9





expand the domain of the question from CO2 emissions to other sorts of greenhouse gasses and substances

that can aﬀect the frequency of forest ﬁres. As mentioned before, we can do this globally or even for speciﬁc

countries. The goal would remain the same where we are interested in observing the relationship between the

predictor (diﬀerent greenhouse gasses and response variables (forest ﬁres)). Additionally, we believe that it

would be insightful to study human behaviors to have a better understanding of forest ﬁres. Since most forest

ﬁres are due to humans, whether that is due to cigarettes, intentional ﬁres, or camping (not at a campsite).

Overall, it would be interesting to observe the relationship between human behaviorisms, or lack thereof, and

its implication on the environment and forest ﬁres.

10





Works Cited

“Average Monthly Temperature: NOAA Climate.gov.” www.climate.gov/maps-data/data-snapshots/data-source-

average-monthly-temperature.

“Bar Charts.” Plotly, plotly.com/python/bar-charts/.

Frohlich, Thomas C., and Liz Blossom. ”These Countries Produce the Most CO2 Emissions.” 14 July 2019. Web.

13 Dec. 2020.

“Folium — Folium 0.11.0 Documentation.” Python Visualization, 2020, python-visualization.github.io/folium.

Gray, Ellen. “Satellite Data Record Shows Climate Change’s Impact on Fires – Climate Change: Vital Signs of

the Planet.” NASA, NASA, 11 Sept. 2019, climate.nasa.gov/news/2912/satellite-data-record-shows-climate-changes-

impact-on-ﬁre/.

“Line Charts.” Plotly, plotly.com/python/line-charts/.

Multiple Axes. (2020). Python — Plotly. https://plotly.com/python/multiple-axes/

Osmanski, Stephanie. “How Do Carbon Emissions Aﬀect the Environment?” Green Matters, Green Matters, 30

Mar. 2020, www.greenmatters.com/p/how-do-carbon-emissions-aﬀect-environment.

The source of the coordinates data is from the following website : www.geojson.io

State Carbon Dioxide Emissions Data - U.S. Energy Information Administration (EIA).

www.eia.gov/environment/emissions/state/.

“U.S. Wildﬁre Data (plus Other Attributes).” Kaggle, 6 Oct. 2020, www.kaggle.com/capcloudcoder/us-wildﬁre-

data-plus-other-attributes.

“Wildﬁre Causes and Evaluations.” U.S. National Park Service, www.nps.gov/articles/wildﬁre-causes-and-evaluation.htm.

11





Extra links used just to display on the map for each state

https://www.reuters.com/article/idUSKCN0R203U20150902?edition-redirect=ca

Scatter Plots. plotly.com/python/line-and-scatter/.

https://www.scemd.org/prepare/types-of-disasters/wildﬁres/: :text=The

https://en.wikipedia.org/wiki/Bastrop County Complex Fire: :text=The

https://www.courier-journal.com/story/news/local/2016/11/15/27-wildﬁres-remain-southeastern-kentucky/93913974/

https://en.wikipedia.org/wiki/1998 Florida wildﬁres

https://abc3340.com/news/local/more-than-350-wildﬁres-in-september-as-alabama-is-under-a-statewide-ﬁre-alert

https://www.audubon.org/news/alaskas-big-ﬁre-seasons-are-new-normal-and-reshaping-landscape: :text=The

https://talkbusiness.net/2018/01/arkansas-has-its-highest-wildﬁre-numbers-in-ﬁve-years-during-2017/: :text=In

https://www.knoxnews.com/story/news/local/tennessee/2016/12/11/how-bad-2016-ﬁre-season/95217380/

https://www.wtnh.com/news/largest-brush-ﬁre-in-recent-connecticut-history-burns-in-cornwall/

https://earthobservatory.nasa.gov/images/51670/ﬁre-in-great-dismal-swamp-virginia: :text=Land

https://www.insurancejournal.com/news/southcentral/2019/08/20/536644.htm

https://en.wikipedia.org/wiki/Bugaboo Scrub Fire: :text=The

https://en.wikipedia.org/wiki/Great Baltimore Fire: :text=The

https://en.wikipedia.org/wiki/Great Fire of New York: :text=The

https://en.wikipedia.org/wiki/Great Michigan Fire

https://mrcc.illinois.edu/living wx/wildﬁres/index.html: :text=The

https://idahonews.com/sponsored/spotlight/important-facts-about-major-wildﬁres-in-idaho-history: :text=The

https://wildﬁretoday.com/tag/jasper-ﬁre/

https://www.kansascitymag.com/kansas-now-has-a-wildﬁre-season-heres-what-that-means/: :text=In

https://www.clarionledger.com/story/news/2017/03/24/mississippi-wildﬁres/99573416/

https://en.wikipedia.org/wiki/Las Conchas Fire: :text=The

https://www.areawidenews.com/story/1875438.html

https://earthobservatory.nasa.gov/images/18693/milford-ﬂat-ﬁre-utah: :text=Land

https://bringmethenews.com/minnesota-lifestyle/remembering-the-monster-wildﬁres-of-minnesotas-history

https://www.greatfallstribune.com/story/news/2020/10/03/montana-ﬁres-most-destructive-wildﬁres-2020-bridger-foothills-

bobcat-ﬁre/5894963002/

https://en.wikipedia.org/wiki/Martin Fire

https://www.wbur.org/earthwhile/2020/09/15/new-hampshire-wildﬁre-risk-climate-change

https://en.wikipedia.org/wiki/New Jersey Forest Fire Service: :text=In

https://www.hawaiiwildﬁre.org/news-center

https://spectrumnews1.com/oh/columbus/weather/2020/10/20/wildﬁre-threats-in-ohio: :text=In

https://www.cnn.com/2020/03/08/us/oklahoma-412-ﬁre/index.html

https://stateimpact.npr.org/pennsylvania/2016/04/27/pocono-forest-ﬁre-destroys-more-than-8000-acres/: :text=The

https://history.nebraska.gov/publications/prairie-ﬁres: :text=Some

https://en.wikipedia.org/wiki/Bastrop County Complex Fire: :text=The

https://www.newenglandhistoricalsociety.com/four-days-may-1942-rhode-island-forest-ﬁres/

https://www.maine.gov/dacf/mfs/forest protection/1947 ﬁre.html: :text=In

https://www.opb.org/news/series/wildﬁres/oregon-biscuit-ﬁre-history-largest-ever/: :text=In

https://www.5280.com/2020/10/the-10-largest-wildﬁres-in-colorados-history/

https://en.wikipedia.org/wiki/Evans Road Wildﬁre: :text=The

https://www.nps.gov/jeca/learn/nature/jasperﬁre.htm

https://earthobservatory.nasa.gov/images/50999/wallow-ﬁre-arizona: :text=On

https://www.wgbh.org/news/local-news/2020/09/08/western-mass-blaze-serves-as-reminder-of-states-rich-history-of-

wildﬁre

https://www.scemd.org/prepare/types-of-disasters/wildﬁres/: :text=The

https://www.ﬁrehouse.com/operations-training/article/10502384/wildland-ﬁre-sweeps-iowa-countryside

https://dnr.wisconsin.gov/topic/forestﬁre/wisconsinﬁres: :text=Peshtigo

12

