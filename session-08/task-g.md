#Task G: Leaflet Map Basics

**Instructions:** First, copy over the directory [https://github.com/newmapsplus/geo409/tree/master/session-08/task](https://github.com/newmapsplus/geo409/tree/master/session-08/task) into the root directory of your personal *geo409* Git repository and rename it to *task-g/*. Modify the *index.html* within this directory to fulfill the requirements listed below. 

The goal of this task is to create a Leaflet map with a unique basemap of your choosing. When the user clicks once on the map, the map is recentered on that click point and zoomed to a desired zoom level. Furthermore, the JavaScript calculates two pieces of information: 1) how far (the distance in meters) that point click is from the Red Iguana restaurant (located in Salt Lake City at latitude 40.7718 and longitude -111.9124), and 2) how far the Red Iguana is from the Southwest corder of the recentered map view.

Save your changes to your *index.html* file and **commit changes to your local GitHub repository** as you work.

Open the starter *index.html* file in your text editor and examine the provided JavaScript code:

    ```javascript
        var map = L.map('map', {
            center: [40,-94],
            zoom: 4
        });

        var redIguana = L.latLng(40.7718,-111.9124);
        
        map.on('click', function(e){
            console.log(e.latlng);   
        });
    ```
    
You'll see that a Leaflet map object has already been created, centered on latitude 40 and longitude -94, with a zoom level of 4. Also, a Leaflet LatLng object has also been created using the coordinates of the Red Iguana restaurant and assigned to the variable `redIguana`. Additionally, the Leaflet map *on* event method is being called and listening for a click event. The callback function then logs the LatLng object of that click event to the Console. Open the file in your browser (remember to also open your JavaScript Console) to test. Note that you will not see a tiled basemap yet.

1. First, modify the Leaflet map options to constrain the map's minimum zoom level to 4 and maximum zoom level to 12.

2. Look through the Leaflet-providers preview and choose a basemap of your liking ([http://leaflet-extras.github.io/leaflet-providers/preview/](http://leaflet-extras.github.io/leaflet-providers/preview/). Add this basemap tileset to the Leaflet map. Save your file and refresh the browser to verify that the map is now loading a tiled basemap.

3. Within the *on* method's callback function, replace the *console.log()* statement with the following:

    a. a statement that stores the click event's LatLng object (i.e., its location) as a variable
    
    b. a statement that uses this variable to calculate the distance between it and the redIguana's location, storing the result as a variable
    
    c. a statement that logs the previously created variable to Console (i.e., logs the distance between the click event and the Red Iguana to the Console)
    
    d. a statement (or statements) that determines the LatLng object of the Southwest corner of the map view's current bounding box and stores this value as a variable
    
    e. a statement that calculates the distance between the Red Iguana and the Southwest corner of the updated bounding box
    
    f. finally, a statement that logs the result of the previous calculation to Console.

4. As usual, change the `h1` and `h2` tags to update your web document with an appropriate (even fun!) title and subtitle, and edit the text at the bottom of the page (e.g., author and meta information).

5. Sync your final solutions with your remote repository and provide a link within Canvas by the due date: **Thursday, February 12th, 11:00am**.

 





