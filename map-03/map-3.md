#Map Assignment 3

**Scenario**:

You've been hired to make an interactive web map of US electric power generation. Your client would like users to be able to compare the power produced from *3 distinct fuel sources* of your choosing. At least one of these sources should be either Coal, Natural Gas, or Nuclear. The other two are up to you. The client has also given you the follow requirements the map should meet:

**Map requirements (which are also the suggested order for coding)**:

* shows power plant power generation using proportional symbol size to visually encode the amount of power produced from a *particular fuel source*
* allows the user to easily compare 3 distinct fuel sources (of any amount of generating capacity) by visually encoding the proportional symbols with distinct colors (i.e., make the symbol for each fuel source a different color). (hint: consider using [http://colorbrewer2.org/](http://colorbrewer2.org/)'s qualitative color schemes for some hexi-decimal color values).
* provides the user with a layer control to toggle on and off the visibility of various power plant data layers
* styles the label text within the layer control to correspond with the color used to encode a specific power fuel source
* when the user *clicks* on the map once, the map display will change to only show plants within **500 km** of the click event
* when the user *double-clicks* on the map, the map display will change to only show plants with **200 km** of the click event
* after the user *clicks* or *double-clicks* on the map and then clicks on any power plants currently visible the will retrieve specific information about the plant, including the plant's name, its fuel source, and the distance from the plant to the the click point
* the default zoom behavior that happens on a double-click event should be disabled
* tailor the map for the client by providing appropriate title and other information.

You will use and adapt the code presented in Lab 12 to solve this map assignment.  

**Map due date**: The client needs the final map submitted via Github and a link through Canvas no later than ***5pm on Thursday, March 12th***

**Extra Credit**:

Enhance the map display so that upon clicking or double clicking, a "spotlight filter" circle shows the areal extent of the distance (i.e., 200km or 500km radius). You may style this circle however you deem appropriate, but note that the circle should be drawn so that it doesn't cover the proportional symbols and thereby disables their click to retrieve the popup functionality. The solution may look like this:

![Spotlight filter showign extent of search/filter radius](spotlight-filter.png)

**Extra Extra Credit**:

Beyond displaying the spotlight filter circle, the client would also like to know some summary statistics from the area within that search filter. Modify the code so that, upon clicking on the map, the the aggregate amount of power for each fuel source is made available within a popup on the spotlight filter, opening immediately upon clicking or double-clicking on the map. The popup would look like this:

![Summary statistics for the popup of the spotlight filter](summary-popup.png)