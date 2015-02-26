#Task H: Creating and Drawing GeoJSON data withe geojson.io and Leaflet

**Instructions:** First, copy over the directory [https://github.com/newmapsplus/geo409/tree/master/session-10/task](https://github.com/newmapsplus/geo409/tree/master/session-10/task) into the root directory of your personal *geo409* Git repository and rename it to *task-h/*. Modify the *index.html* within this directory to fulfill the requirements listed below. 

The goal of this task is to create a tourist map of four Places of Interest in a town or city of your choosing that also displays a recommended route for visiting these places on a day trip.

Save your changes to your *index.html* file and **commit changes to your local GitHub repository** as you work.

Steps (refer to the examples provided in Module 10 to complete this task):

1. Go to [http://geojson.io/](http://geojson.io/).

2. Login using your GitHub credientials (so your map can be saved).

3. Zoom in to a city of your choosing and:

    a. Using the "Draw a marker" tool, create 3 markers for Places of Interest (POI) best represented as Point features. Include two properties for each: a name for each place and a description. If you want more of a challenge also include a radius value for later use in step six. Be thoughtful about how big this radius is since you want it to be appropriate for the POI and your map.
    
    b. Using the "Draw a polygon" tool, create 1 Place of Interest best represented by a Polygon feature (e.g., a park, baseball stadium, or racetrack) and include a name and description of it as well in its properties.
    
    c. Using the "Draw a Polyline" tool, create a recommended route connecting your 4 POIs.
    
    d. copy the entire GeoJSON code produced to the clipboard.
    
4. paste your GeoJSON data into your *index.html* and assign it to a variable.

5. write a statement that creates a Leaflet GeoJSON layer from these data and adds it to the map (first test to see if your GeoJSON data has been drawn to the map).

6. modify the previous statement to include Leaflet GeoJson options *pointToLayer* and *onEachFeature* to:
    
    a. convert the default markers/points to small Leaflet *Circle* objects (choose an appropriately small radius given the map scale). If you included a size variable in step three you can use it to dynamically size the circles.
    
    b. provide the circles with a distinct style.
    
    c. provide the polygon with a distinct style.
    
    d. provide the polyline with a distinct style.
    
    e. bind popups to the the circles and polygon containing the name and description you defined in step 3.
    
    f. defines a style option that universally applies a path option to the stroke of the features so that they are dashed and have a width of 10 pixels.

7. As usual, change the `h1` and `h2` tags to update your web document with an appropriate (even fun!) title and subtitle, and edit the text at the bottom of the page (e.g., author and meta information).

8. Sync your final solutions with your remote repository and provide a link within Canvas by the due date: **Thursday, February 26th, 5:00pm**.