#Task D: JavaScript Arrays and Control Structures

**Instructions:** First, copy over the directory [https://github.com/newmapsplus/geo409/session-05/task/](https://github.com/newmapsplus/geo409/session-05/) into the root directory of your personal *geo409* Git repository and rename it to `task-d` -- just like you previously did with tasks a to c. Modify the *index.html* within this directory to fulfill the requirements listed below. The goal of this task is to update the code written in task c to place 3 markers on the map for 3 different Kentucky cities using Arrays and looping structures, rather than separate variables for each respective city.

Save your changes to your *index.html* file and **commit changes to your local GitHub repository** as you work. 

1. Create an Array named `cities` that contains the String type names of your 3 cities.

2. Create a 2-dimensional Array named `cityCoords` that contains 3 elements, each an Array containing the latitude and longitude of each of the three cities listed in the `cities` Array. Be careful to ensure that the index for each Array of coordinates corresponds to the index for each city name in the `cities` Array.
3.Create two more Arrays, named `cityPops` and `cityCapitol`. The `cityPops` Array should contain the populations of the respective cities in the `cities` Array (again, be careful with the order of these as they should match). The `cityCapitol` Array should contain three Boolean values designating whether the cooresponding city in the `cities` Array is or is not the capitol of the Commonwealth of Kentucky.
4. After these data structures have been successfully build, edit the remaining code, replacing the "/* add code here */" comments with actual JavaScript. You'll need to:

    a. Provide the three expressions within the *for loop* parentheses to ensure the loop cycles through all the elements within the `cities` Array.
    
    b. Access the correct values within the `cities` and `cityPops` Arrays to contruct the popup content with the cities' names and populations
    
    c. Access the correct value within the `cityCapitol` Array for each city to complete the expression within the *if statement.*
    
    Once these steps have been successfully completed, the map should load and operate just as the solution for task-c did (only the underlying JavaScript code will be running more efficiently with Arrays and loops!).
    
5. Change the `h1` and `h2` tags to update your web document with an appropriate (even fun!) title and subtitle, and edit the text at the bottom of the page (e.g., author and meta information).
6. Sync your final solutions with your remote repository and provide a link within Canvas by the due date: **Tuesday, February 2nd, 11:00pm**.


