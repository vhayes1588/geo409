#Module 07: JavaScript Objects and Methods

##Overview

This lab does the following:

* introduces you to JavaScript objects
    * creation of objects
    * accessing object properties
    * looping through a JavaScript object
* introduces you to JavaScript methods

###Working files

You should try out the code in this lab using the index.html file located in the session-07/lab/ directory from the course Github repository. Remember to sync your local version of the course repository with the online version.

##Required Readings

Chapter 4 of *Eloquent JavaScript*: [Objects and Arrays](http://eloquentjavascript.net/04_data.html)

##What are JavaScript Objects?

In Module 05 we learned how to store data within a data structure known as an Array, which ordered elements within it according to their specific index. While Arrays are very useful in web programming, the real power of JavaScript comes with another complex data type: the *object*. Rather than storing information in a specific order (like we see in an Array), objects store information as a collection of *properties*. Each property comprises a *name* and an associated *value*. The property name is also sometimes referred to as a key ... as in, properties are made of key/value pairs. JavaScript objects are sometimes referred to as "associative arrays," because key identifers are associated with their respective values. If you are familiar with other programming languages, the object data structure is also similar to dictionaries (such as in Python) or hash tables (in R and Ruby).

You may have heard of something known as "object-oriented programming." In programming terms this means that we attempt to treat collections of information as if they were real objects in the world. For example, if we say "coffee cup" you know  what we mean and what you can do with it. We don't have to provide details on things like it can hold hot liquids, has a handle, etc.  And since our goal with programming is  to *map* actual lived spaces and geographies in the world, using objects modeled on the real world and maps makes sense for us. 

Objects in the real world can be characterized by two things: particular *properties* they exhibit and *things they do*. 

For example, an iguana has particular properties such as a name, weight, skin color, dreamy eyes, ambition for world domination, etc. These are all properties of a particular iguana, and we can use JavaScript objects to capture these properties. And there may be some properties that are appropriate for other objects like "coffee" that don't make sense for an iguana, such as level of caffeine content. Although I guess it depends on the iguana.

Iguanas also do things: they may eat leaves, stare at you with their dreamy eyes, introduce themselves in clearly articulated English and demand your servitude (the world dominating variety of iguanas, of course). JavaScript objects also capture this aspect of *doing things* that real world entities exhibit. This will make more sense through the examples below, but first let's get the syntax down for creating and accessing objects.

###Creating and Accessing JavaScript Object Properties

While we do store the reference to the object in a variable, the syntax of an object is, as we'd expect, different from that of an Array. The difference is relatively minor visually - rather than using square brackets a JavaScript object uses curly braces - but absolutely, fundamentally, uncategorically different when JavaScript encounters it. So be careful and pay attention!

```javascript
    var myObject = {};  // declare and define an empty object
    console.log(myObject); 
```

Within those curly braces: 

- Objects encode information through one or more properties. 

- A colon separates the property's name from its value, and properties are separated by commas. 

- Property names are always written to the left of the semicolon, and must be unique within that object (i.e., there can be only one property name of *height* within an object). While we often don't write the property names with quotation marks around them, we can, as technically they are Strings. (Later on in Geo409 we'll be working with a specific kind of object known as a JSON object, which will require property names to be written using quotation marks.)

- The value associated with a property name may be of any data type (i.e., Numbers, Booleans, Strings, Arrays ... even other objects or functions!).

Let's start by building a simple object that represents our friendly iguana:

```javascript
    var iguana = { 
        name: "Jack",   // a string value
        weight: 4.2,    // a numeric value, assume kilograms
        age: 8,         // a numeric value
        eyes: "dreamy", // a string value
        questForWorldDomination: true  // a boolean value
    }
    console.log(iguana);
```

Note that there is no inherent order to the property/value pairs within an object. We could have just as well defined our object as:

```javascript
    var iguana = { 
        questForWorldDomination: true,  
        age: 8, 
        eyes: "dreamy",
        name: "Jack", 
        weight: 4.2 // assume kilograms
    }
    console.log(iguana);
```

We can also assign objects as the value of an object property, a practice known as "nesting objects." Say our iguana has a toolkit he brings with him when on his quest for world domination (and apparently he wants to listen to heavy metal and wear cool sunglasses):

```javascript
    var iguana = { 
        questForWorldDomination: true,  
        age: 8, 
        eyes: "dreamy",
        name: "Jack", 
        weight: 4.2,
        toolkit: {
            conquestFlag: "red",
            surrenderFlag: "white",
            food: true,
            music: "Anthrax",
            coolSunGlasses: 8
        }
    }
    console.log(iguana);
```

Okay, how do we then access property values within an object? We used bracket notation and the index value for accessing values within an Array, but because objects have no inherent order, this doesn't work. In other words, we can't count on the fact that the property questForWorldDomination will always be the first value. Instead, we use the property names themselves. Kinda of clever, huh? Well, you have to be if you're dealing with a power-mad iguana.  Accessing property values using objects is also computationally fast, as opposed to looping through an Array, which is also good. We like fast.

There are two ways we access property values. One is to use dot notation:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // assume kilograms
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true  
    }
    console.log(iguana.name); // output "Jack"
    console.log(iguana.weight); // output 4.2
```

We can even combine this with some of the control processes we've learned.

```javascript
    if (iguana.questForWorldDomination == true){
        console.log("I for one, salute our new Iguana overlords.");
    }
```

What about that nested object? Using dot notation we can string together property names to "drill down" into the structure:

```javascript
    var iguana = { 
        questForWorldDomination: true,  
        age: 8, 
        eyes: "dreamy",
        name: "Jack", 
        weight: 4.2,
        toolkit: {
            conquestFlag: "red",
            surrenderFlag: "white",
            food: true,
            music: "Anthrax",
            coolSunGlasses: 8
        }
    }
    console.log(iguana.toolkit.music); // will output "Anthrax"
```

The other way is to use bracket notation, though note how we need to write the property name with quotation marks around it:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // assume kilograms
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true 
    }
    console.log(iguana["name"]); // output "Jack"
    console.log(iguana["weight"); // output 4.2
```

Similarly, we can use bracket notation to access our nested object property values, or even mix and match!

```javascript
    var iguana = { 
        questForWorldDomination: true,  
        age: 8, 
        eyes: "dreamy",
        name: "Jack", 
        weight: 4.2,
        toolkit: {
            conquestFlag: "red",
            surrenderFlag: "white",
            food: true,
            music: "Anthrax",
            coolSunGlasses: 8
        }
    }
    console.log(iguana["toolkit"]["music"]); // will output "Anthrax:
    console.log(iguana["toolkit"].coolSunGlasses); // will output 8
```

We can also use both of these approaches to change/modify property values, as well as add new properties to an existing object. Let's update our iguana's information first (let's pretend that Jack is getting older and putt on on some more weight). Perhaps the quest for world domination is not going as well as he hoped.

We can use the dot notation with an assignment operator:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // assume kilograms
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true 
    }
    console.log(iguana.weight); // output 4.2
    console.log(iguana.age); // output 8

    iguana.weight = 5.2;
    iguana.age = 9;

    console.log(iguana.weight); // output 5.2
    console.log(iguana.age); // output 9
```

You could even use the same logic to change his plans for world domination. Can you see how?  Try changing questForWorldDomination to false and test your code by using a console.log command (as in the examples above).

We can also use the bracket notation to do the same thing, again using an assignment operator:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // assume kilograms
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true 
    }
    console.log(iguana.weight); // output 4.2
    console.log(iguana.age); // output 8

    iguana["weight"] = 6.1;
    iguana["age"] = 10;

    console.log(iguana.weight); // output 6.1
    console.log(iguana.age); // output 10
```

We can also use both dot and bracket notation to easily add new properties to our object. Let's provide our iguana with some additional properties:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // assume kilograms
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true 
    }
    console.log(iguana); // output entire object for inspection

    iguana.color = "green";
    iguana.madGenius = true;

    console.log(iguana); // note that object has the additional proprties
```

Let's do the same thing using bracket notation. Note, we are in charge in terms of which properties we want to add to the iguana object:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // assume kilograms
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true 
    }
    console.log(iguana); // output entire object for inspection

    iguana["color"] = "purple";
    iguana["unlovedAsBaby"] = true; // hence his need to compensate

    console.log(iguana); // object with additional properties
```

We've presented two different ways of accessing property values, as well as modified them or adding new properties to an object. What's the difference between these two, and when should you use one over the other? The simpliest answer is that in general it doesn't really matter.

Ok, that really isn't an answer but it is (mostly) true. But it is important for you to be aware of both ways especially when you start reading through someone elses code. For you own stuff pick whichever one makes the most sense to you but keep a couple of things in mind:

* dot notation:
    * is computationally faster than bracket notation (and we always like things fast!)
    * is cleaner to write and read than bracket notation
* bracket notation:
    * allows for special characters to be used within a property name (e.g., *name: foo[]*)
    * allows one to access object properties while looping through them (see below)
    * is also used for creating unique property names within an object when updating that object within a looping structure. OK, that is a bit difficult to process so let's look at an example. This code below creates a new object and then creates a new property name using the for loop's iterator variable, assigning a value from the array to each:
    
    ```javascript
        var myObject = {};
        var someValues = [1,3,21,42,3]
        for(var i = 0; i < someValues.length; i++) {
            myObject["id"+i] = someValues[i];
        }
        console.log(myObject);
    ```

Don't worry too much about this last example right now if it doesn't make sense. What's more important is to understand how to iterate through an object which is what we're going to cover now.

###Looping through objects

Let's say we want to iterate (or loop) through the properties within our object and access the property values. To do this, we'll use a for loop, though in a slightly different way than the one we used for iterating through an Array. Instead, we'll use a *for ... in* statement, which iterates over each property name within the Array. 

We'll take this real slow for now, so we understand what's going on. First, let simply log the object's property names (its keys) to the console:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // assume kilograms
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true 
    }
    
    for (var key in iguana) {
        console.log(key); // outputs "name", "weight", "age", "eyes", "questForWorldDomination"
    }
```

Now, we can access the values associated with each of those properties using our bracket notation:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // assume kilograms
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true 
    }
    
    for (var key in iguana) {
        console.log(iguana[key]); // outputs "Jack", 4.2, 8, "dreamy", true
    }
```

Note: since we can access the values in objects directly (via dot and bracket notation) there's often no need to loop. In this particular case this is a bit of overkill but we want to demostrate the idea.

Next let's turn to JavaScript methods.

##JavaScript methods

You might be thinking, "Oh no! Functions and objects are confusing enough. Now something else!? I really need to access my comfort iguana!!"  And that's OK, everyone needs a comfort iguana from time to time.

The good news is that **methods** are very similiar to functions (from the previous lab), so there isn't too much more to grapple with. Methods basically have the same syntax, accept arguments, and return values just like functions. 

So what's the difference between a function and method then?  While a function stands alone, a method is associated with a particular object and operates on data and functionality associated with that object. Let's return to our friendly iguana and the notion of "object-oriented programming" to first conceptually grasp what methods are before looking at some more practical examples?

Remember earlier in this lab when we discussed how objects in the real world have both properties and *do things*? So far, we've been using object properties to store only simple data types (i.e., Strings, Booleans, Numbers). But a property value can also be a more complex data type, such as a function! Whoa! What does this mean?

Let's give our iguana Jack the ability to greet us as our new overlord. After all what's the point of world domination if you can't interact with your subjects. We'll create a new property name called `greeting` and assign a function as its value. Syntactically, we attached a method call to an object using dot notation. This allows the object `iguana` some functionality, beyond merely storing static property values. 

In a very minor (and completely biologically incorrect) sense we have given our `iguana` object life!  OK, not much of a life -- it only can say one thing -- but it is arguably better than just being a static storage unit of values. Not that there's anything wrong with being a static storage unit of value, some of our best variables are precisely that.

OK, enough philosophy, back to programming. Take a look at the addition to the `iguana` object.

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, 
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true, 
        greeting: function(message) {
            console.log(message);
        }
    }
    iguana.greeting("Hello. I am your new overlord.");
```

This example demonstrates that methods are functions, which are the values of particular object properties. We can have that function return values as well. Let's say our iguana wants to calculate his BMI, after all he needs to be at his peak performance to take over the world. Similar to examples in Module 06, we can pass in two values when we invoke the method:

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // kilos
        length: 1.5, // meters
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true, 
        calculateBMI: function(w,l) {
            return w / (l*l); // now you know how to calculate BMI, BONUS!
        }
    }
    var result = iguana.calculateBMI(4.2,1.5);
    console.log(result); // output is 1.87 which is really underweight,
                         // at least for a human, not sure about an iguana
```

Note, in the example above we passed in the two values 4.2 kilos and 1.5 meters directly but we can also access the values we set in our iguana object.

```javascript
    var result = iguana.calculateBMI(iguana.weight, iguana.length);
    console.log(result); // output is still 1.87
```

However, the object *iguana* here already "knows" its own values of weight and length. We don't have to send those values in. Instead, within the object's method (the function *calculateBMI* we can access these values using a special reserved keyword in Javascript: `this`. 

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, // kilos
        length: 1.5, // meters
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true, 
        calculateBMI: function() {
            var w = this.weight;
            var l = this.length;
            return w/(l*l);
        }
    }
    
    var result = iguana.calculateBMI();
    console.log(result); // output is still 1.87
```

The `this` keyword can be conceptually challenging to grasp and use effectively. The hard part is, it means different things in different programming languages, and means something different in JavaScript depending on how functions are called. In this case, however, when a function is called as a method of an object, `this` refers to the object on which that method is called.

We could also get real savvy and store some information within an object, and pass that as an argument to the method. Let's suppose the iguana is preparing to invade some cities in Kentucky and wants to process some information about the city first. In this case the object is `lexData` and it is being passed to the method `iguana.invasionPlans` in the object `iguana`.

```javascript
    var iguana = { 
        name: "Jack", 
        weight: 4.2, 
        age: 8, 
        eyes: "dreamy",
        questForWorldDomination: true, 
        invasionPlans: function(inData) {
            // iguana can do something with data here
            console.log(inData);
        }
    }
    
    var lexData = {
       lat: 38.23,
       lon: -89.21,
       name: "Lexington",
       pop: 821325
      
    }
        
    iguana.invasionPlans(lexData);
```

What's the point of all this? After all we won't necessarily be creating iguana objects that calculate their intent to dominate us. Although that would be cool.  

BUT we will be using A LOT of methods when we begin more serious mapping using Leaflet (stay tuned). It's important to conceptually grasp what they are, as well as become familiar recognizing a method, which is attached to an object using dot notation and often passes various arguments (some of which will be JavaScript objects!) within its parentheses.

Before we wrap up, let's briefly consider a few more methods using some of JavaScript's native, built-in objects.

We've actually already by using a method all along, from the first line of JavaScript we wrote. In the `console.log()` statement, `.log()` is a method available on the `console` object. We've been passing it arguments every time we invoke it (i.e., `console.log("Hello Map")`). In fact, there a [bunch of other methods](https://developer.mozilla.org/en-US/docs/Web/API/Console) that can act upon the console as well.  

There are lots of common methods around. In Module 04 we introduced String types which have particular methods that act upon them. For example, Strings have a method named *concat* that basically operates like the plus sign operator does when placed between two Strings:

```javascript
    var cityName = "Lexington";
    console.log(cityName);
    var cityNameWithState = cityName.concat(", KY"); // concat method concatenates two Strings
    console.log(cityNameWithState); // output is "Lexington, KY"
```

This example takes the original value of `cityName`, concatenates it with the String contained within the method's parentheses, and assigns the return value to variable cityNameWithState. You can also use the `.toUpperCase` method to change a city's name. See below.

```javascript
    var cityName = "Lexington";
    var cityNameCaps = cityName.toUpperCase();
    console.log(cityNameCaps); //output is LEXINGTON
```

You can also use methods to look inside a string value, see the example below.

```javascript
    var cityName = "Lexington";
    console.log(cityName.charAt(4)); // returns the String 
                                     // character at index 4, "n"
    console.log(cityName.indexOf("x"));  // returns the index (2) of the
                                        // first character found of "x"
```

We're not going to exhaustively cover all the [useful methods in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) (though feel free to take a little time to look them up and play with the examples!). 

The key point we want you to take away from here is that when you see some JavaScript with a `.someMethod(possibleExpressionsHere)` attached to it, you recognize it as a method. Because you'll see lots of these.

Also important is to know that methods operate on particular objects or data types. So while a method named `.toUpperCase()` means something when attached to a String, it won't do anything when attached to an Array (in fact, it will throw an error). 

And lest you start feeling bad for Arrays, rest assured that JavaScript [Arrays have their own methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). Of particular utility are the `.push()` and `.pop()` methods, which pushes a new element to the end of an Array and remove the last item from an Array, respectively.

```javascript
    var cities = ["Lexington", "Bowling Green"];
    console.log(cities); // output is ["Lexington", "Bowling Green"]
    cities.push("Frankfort");
    console.log(cities); // output is ["Lexington", "Bowling Green", "Frankfort"]
    cities.pop();
    console.log(cities); // output is ["Lexington", "Bowling Green"]
```

##Glossary:

* **object**: a data structure used within JavaScript designated by curly braces and composed of comma-separated properties
* **object-oriented programming**: an approach to computer programming that treats data objects like real world objects, giving them particular characteristics and actions
* **property** (re: objects): a type of variable that is attached to an object and help define the characteristics of that object
* **property name**: a case sensative String variable used to reference an object's property
* **property value**: the value of an object's property
* **method**: a value of an object's property, when that value is a function
* **this keyword**: when used inside a method's scope, `this` refers to the object on which the method is called

