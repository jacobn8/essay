# Essay
## Jacob Nelson

## Reuter's: "Looking for Lead"

## Introduction:

### Goal:

This project was made in order to help understand which area's are most at risk for lead poisoning, and to help educate the public. The project specifically looks at cases of lead poisoning amongst children in 34 states. Despite efforts to combat it, child lead poisoning is still rather widespread due to lead paint and pipes from the past remaining in homes, playgrounds, and wellwater. According to reuters, the national estimate for lead poisoning in children, is that 2.5% have an elevated blood level of lead.
This was also released at the height to the crisis in Flint Michigan, and seeks to show a newly interested audience that Flint isn't the only american city with a lead problem.

### The Major functions

![The Map](/img/map.png)
The project itself is a webmap showing the percent of children in a given zip code or census tract whose blood tests showed elevated lead levels. Each zip code or census tract polygon is color coded based on th the percentage of children with elevated lead levels.
![Popup](/img/map2.png)
Each zip code area, when moused over, displays a pop up with more detailed information. This pop up shows the number of tested children, the percentage with elevated lead levels, the zip code, and state.
![Drop down list](/img/map3.png)
The map also has a drop down list of 9 cities with particuarly high levels of lead in their children.
Each option brings the to a preset zoom and extent to best view the problem area.
It also gives a brief description of the nature of the city's lead problem
It also has standard zoom in zoom out functionality.

### The Target Audience:
Reuters is a news organization, with a global audience. This map is aimed at the average reuters reader, especially those wishing to learn more about the lead crisis. This map also targets those reading about the lead problem in Flint Michigan who may not know the full extent of America's lead problem.

### The Authors and their affiliation.
This project is attributed to Charlie Szymanski, Christine Chan, Matt Weber, and  M.B. Pell.
All four  are journalists working for Reuters, a globally read news organization.

## System Architecture
The system architecture seems pretty standard for a webmap. The web client handles most of the processing, and communicates with the pieces of the map not hosted by Reuters directly like leaflet plugins and openstreetmap resources.

It also seems as though every map related file is stored on the same webserver: reuters.com/investigates

## Code Inspection

### Data
Aside from their integrated social media tracking, the only data flowing between the client and server beyond the initial html, javascript, and CSS files seems to be leaflet map tiles.
![From the network tab of the chrome console](/img/code.png)
![From the network tab of the chrome console](/img/code2.png)
Most of the files appearing under the network tab when the webpage is run, and the map interacted with are pbf files and mvt files. Which are an XML alternative and mapbox vector tiles respectively.

### Libraries
The code is a little difficult to parse considering just how much of it is dedicated to giving information to advertisers, but the code does also refrence leaflet, and Ajax.
![It's all one line](/img/code2.png)
The authors of this map seem to have put most of their code into a javascript file that consists of one very long line of code.
However, it doesn't show any non-tracking sources beyond ajax and leaflet.
Leaflet is a open source javascript library that serves as the foundation for this map, and many others.
Leaflet loads data, draws and displays the map. It provides most of the map's functionality.
Ajax runs in the background and allows for the web page to request and recive data, update, and communicate with a server without reloading the page.

### Repsonsive Design
The map and webpage work just fine on both desktop and mobile browsers. The mobile browser even adds pinch/pull zoom control, in addition to the plus and minue zoom buttons

## Data Sources

### Vectors
The map is pretty much entirely made up of vector tiles, displaying polygons and holding data.
### Rasters
There do not appear to be any rasters used in this map.

### UI/UX Critique
The interface and experience are quite good overall. The color palate is simple and easy to understand.
It looks very clean and professional.
The 'Troubled Communities' Menu is a nice touch, hovever the descriptions frequently obscure the informational popups, forcing the user to pan the map in order to see the percentage of children with elevated lead blood levels.
I also kept instinctively trying to zoom in and out with the mouse scroll wheel, to no success. Not sure if thats just a limitation of the technology, but its disapointing nonetheless.

## Basemap, thematic layer, and interactive features

### Basemap
The basemap is a simple streetmap with a white and grey color palette, seemingly sourced from openstreetmap.

### Thematic Layer
The thematic layer is the elevated lead level data. Its a series of polygons representing zip code areas or census tracts depending on the format of the source data for the individual state,
These polygons are colored using a white to dark red color ramp, based on the percentage of children's blood tests with elevated lead levels.
Its not immediately clear if the layer is semi-transparent, or if the roads are just loaded over the feature layer, but the major roads and highways are clearly visable at every zoom level.

### Interactive Features
At most, but not all zoom levels, hovering the mouse over a polygon gives a small descriptive popup window with the tract name or zip code (depending on the state), alongside the number of tested children and the percentage of those with elevated lead levels.
There's also the previously mentioned troubled communities window, hovering in the upper right hand corner of the map. This lets the user jump to any of nine problem areas, and gives a description of their lead problem.

### Map Elements
This map lacks both a scale bar and a compass. It does however have a legend.
The legend is broken into 10 categories based on percentage of children with elevated lead levels in their blood:

1. No Data
2. less than 5%
3. 5-10%
4. 10.1-15%
5. 15.1-20%
6. 20.1-25%
7. 25.1-30%
8. 30.1-35%
9. 35.1-40%
10. More than 40%

## Strengths and Weaknesses
This map is very clear, clean and focused. The visual design is also very good. The clean black squares and simple white text add a layer of professional sophistication. The pale pink, skin like nature of the polygons in the low lead level areas contrasts with the dark magentas of the high lead areas to give an impression reminicient of a pox, disease, or open wound in the troubled areas.

I also appreciate the map's troubled communities window, as it allows the viewer to easily find lead hotspots, view them in a well framed manner, and contextualizes the data in a way a lot of maps do not.

On the other hand, I think the map could be improved in a few ways. For instance, the different states sort of bleed together, I think adding some borders to the states could improve the visual presentation of the map.
I also think the pop up window could stand to have some more details added. Just having the state and the zip code or census tract number feels cold and impersonal, and rather non descriptive. Having the name of the town or city attached would make it feel more personal.


## Reflection
This map clearly serves the common good in a pretty understandable way. Flint Michigan's water crises was a horrific event that captured the public conciousness in a visceral way, and the same thing is happening all across the country. This sort of project could be used for a more directly practical goal, like parents picking a place to move that won't poison their kid, or activists looking for at risk locations to prioritize. However, spreading awareness, and keeping the issue of lead poisoning in the public conciousness is also important, as it makes it harder for those in a position to do something about it to ignore the problem.
There's a pretty big power divide between the average person, and the business and political leaders who control our lives. Projects like this seem to amplify the Strengths of the little guy: Numbers.

On the other hand, business in the information age thrives on gathering data. While examining the code, I was continually disturbed by the large percentage of code dedicated to tracking the viewer, and sending data to social media companies and google. There weren't any buttons to share the map on social media, which would've been understandable. Some of it might be for their own use, but its still an unfortunate reminder of the surveillance we live under.
