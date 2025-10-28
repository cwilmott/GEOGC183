# Week 11 Web Map

This week we will be completing your web map by adding data from Week 9 onto the custom base map we created in Week 10. 

## 1. Set up your Development Environment

First, we need to get our code back from our Github Repository onto our laptops for editing. This is called setting up a Development Environment. Ours will not be complicated - we are simply going to download the files, and reupload them once we are done, and use a browser to test the ```index.html``` file.

!!! tip "For Tech-Hares!"
      If you're a wizz at git and interested in the experimental pathways, feel free to set up the site as a git using either Github Desktop or pull straight from the         repostitory 

### Download your code

First, we need to download our code back onto our laptops/computers in visual studio code. 

To do this, go to your repository and select **Code**, then **Download Zip**.

Move the ```c183-webmap.zip``` file somewhere you'll be able to find it, and then unzip (double click for MacOSX).

### Bring it into Visual Studio Code
Now we need to open our files. 

Go to Visual Studio Code (or download it here <https://code.visualstudio.com/Download> if you're using your laptop and it's not already downloaded).

Select Open Folder, and then select the folder you have just downloaded (called BAHA-Map or similar)
! [Image Title] (https://code.visualstudio.com/assets/docs/getstarted/getting-started/open-folder.png)

All three of your files - ```index.html```, ```style.css``` and ```script.js``` should be there, alongside your ```/data``` folder.

!!! tip "For Tech-Tortoises :material-tortoise:"
     Your ```index.html``` file will look different to the one on Code Pen - this is because when you downloaded your code pen files, it automatically linked your             ```style.css``` and ```script.js``` files into your index.html as it packaged them. It needs to do this so you html knows where to find your style and your javascript!

### Check it still works!
On your desktop, locate your index.html file and drag it into a browser - you should see your map (as long as you're on the internet!). <br>

DO NOT CLOSE THIS BROWSER WINDOW - we will be using this to test the updates to your map when we add your markers and such.

## Create an "On Load" function

Before we add our markers and pop-ups, we need to make sure our markers don't load before our map. So, we are going to create an on('load') for our map. This will be a wrapper for all of our markers (and pop-ups) which will go inside the function. 

It's made up of several parts. 

``` js
map.on('load', function() {
});
```
Take a careful look: what is happening here is that when the map object (i.e. ```map```) has an event (```on```) where it has loaded (```load```) then, run these pieces of code ```function() {}```

You can see there are lots of syntax also nested in there - you have to be careful - make sure every bracket and parenthesis has a pair, and pay attention to the semi-colons going forward!

Now, copy and paste the function into your ```script.js``` file under your ```const map```.

Your code should look something like this:

```js
mapboxgl.accessToken = 'pk.eyJ1IjoiY3dpbG1vdHQiLCJhIjoiY2s2bWRjb2tiMG1xMjNqcDZkbGNjcjVraiJ9.2nNOYL23A1cfZSE4hdC9ew';
const map = new mapboxgl.Map({
        container: 'map', // container ID
        style: 'mapbox://styles/cwilmott/cmg5px11u00ef01sm3fr65ro0',
        center: [-122.27, 37.8], // starting position [lng, lat]. Note that lat must be set between -90 and 90
        zoom: 9 // starting zoom
    });

map.on('load', function() {

});
```
## 2. Add Markers

Now, we are going to add our markers *inside* our **load function**. To do this, we have to do two things:
1.  Make a link to our geojson data
2.  Add it as a marker (or symbol) layer to our webmap

### a. Add Source Data

Adding source data is relatively easy. But first, we need to locate our source data! 

There are two ways of creating links using code: one is what is called a **relative path**, in which the link structured according to its position to your code. In this cse, the relative path to your data source would be: data/yourdata.geojson (i.e. it's in the data folder, with your geojson). *In most cases for web development, this is what is recommended because it contains all the links in the same structure of the program and makes it easy to move*. 

But today, I want to make sure it works, so I'm going to recommend we do an **absolute path** to the location of your raw data on the internet - in a large part because I've seen your repositories and they're all over the shop with naming and structure.

So, :material-numeric-1-circle: I want you to go to your **Github repository**, select your **183data.geojson** file, and select **raw**. The link in the address bar is what you will need.

Now, :material-numeric-2-circle:, I want you to look at this piece of code:

``` js

map.addSource('points-data', {
        type: 'geojson',
        data: 'thefullwebaddressofyourdata.geojson'
    });

```
Can you see what is happening here? If what you think is happening is that we are adding a source (```addSource```) to the map (```map```), called **'points-data'**, which has the type 'geojson', and a link to the data - you are correct. :fire: :fire: :fire: :fire:

Now, see if you can paste the code **inside the Load Function** and then replace the address of the data with the address of YOUR data. (and don't worry, you won't see anything change, because we haven't added our markers).

If it looks something like this, you're doing great! AND PAY ATTENTION TO THAT SYNTAX!

``` js

map.on('load', function() {
    map.addSource('points-data', {
        type: 'geojson',
        data: 'https://raw.githubusercontent.com/cwilmott/c183-webmap/refs/heads/main/data/183-data.geojson'
    });
});
```
Nice! :t_rex:

!!! warning
      You'll notice on the Mapbox documentation that a lot of the examples have the geoJSON code in the html, or directly in the javascript. This is one way to do it, but it takes far far longer to render for large datasets and is not as dynamic. 

### b. Add Your Markers / Symbol Layer

Okay, now we have added our source (addSource), we need to create a marker layer (addLayer) which puts a marker at each point in your data.

Mapbox has some handy configurations available which means we don't need to do the work of creating our own markers (right now at least!). I've coded up a basic **circle** marker like this:

``` js
map.addLayer({
        id: 'points-layer',
        type: 'circle',
        source: 'points-data',
        paint: {
            'circle-color': '#4264FB',
            'circle-radius': 6,
            'circle-stroke-width': 2,
            'circle-stroke-color': '#ffffff'
        }
    });
```
We chatted in lecture about the different elements of the marker - note the source data! That's important.

Copy and paste the above code into your **Load Function** *under* your addSource function. Order matters! If the data hasn't loaded, how will the markers know where to go!

Your code should now look something like this:

``` js

mapboxgl.accessToken = 'pk.eyJ1IjoiY3dpbG1vdHQiLCJhIjoiY2s2bWRjb2tiMG1xMjNqcDZkbGNjcjVraiJ9.2nNOYL23A1cfZSE4hdC9ew';
const map = new mapboxgl.Map({
        container: 'map', // container ID
        style: 'mapbox://styles/cwilmott/cmg5px11u00ef01sm3fr65ro0',
        center: [-122.27, 37.8], // starting position [lng, lat]. Note that lat must be set between -90 and 90
        zoom: 9 // starting zoom
    });

map.on('load', function() {
    map.addSource('points-data', {
        type: 'geojson',
        data: 'https://raw.githubusercontent.com/cwilmott/c183-webmap/refs/heads/main/data/183-data.geojson'
    });

    map.addLayer({
        id: 'points-layer',
        type: 'circle',
        source: 'points-data',
        paint: {
            'circle-color': '#4264FB',
            'circle-radius': 6,
            'circle-stroke-width': 2,
            'circle-stroke-color': '#ffffff'
        }
    });
});
```
Check it has worked by refreshing your ```index.html``` page in the browser. If it does, proceed! :champagne_glass:

!!! tip "For Tech-Hares"
      See if you can change the color, radius, stroke width and stroke color - have some fun, but don't lose that syntax!



## 3. Add Pop-Ups to Markers

Pop-Ups are the trickiest thing we'll do and there are a lot of moving parts. You need to be careful, take note of the syntax, debug or go back a few steps - and pay attention to the little alerts that pop up in VS Code.

Error is not a failure in coding - it's a part of the process. I'm not going to even tell you how many error warnings I got learning to code. 

### a. Style Your Pop-Up
In CSS

### b. Add it to your map

In js

``` js
mapboxgl.accessToken = 'pk.eyJ1IjoiY3dpbG1vdHQiLCJhIjoiY2s2bWRjb2tiMG1xMjNqcDZkbGNjcjVraiJ9.2nNOYL23A1cfZSE4hdC9ew';
const map = new mapboxgl.Map({
        container: 'map', // container ID
        style: 'mapbox://styles/cwilmott/cmg5px11u00ef01sm3fr65ro0',
        center: [-122.27, 37.8], // starting position [lng, lat]. Note that lat must be set between -90 and 90
        zoom: 9 // starting zoom
    });

map.on('load', function() {
    map.addSource('points-data', {
        type: 'geojson',
        data: 'https://raw.githubusercontent.com/cwilmott/c183-webmap/refs/heads/main/data/183-data.geojson'
    });

    map.addLayer({
        id: 'points-layer',
        type: 'circle',
        source: 'points-data',
        paint: {
            'circle-color': '#4264FB',
            'circle-radius': 6,
            'circle-stroke-width': 2,
            'circle-stroke-color': '#ffffff'
        }
    });

    // Add click event for popups
    map.on('click', 'points-layer', (e) => {
        // Copy coordinates array
        const coordinates = e.features[0].geometry.coordinates.slice();
        const properties = e.features[0].properties;
        
        // Create popup content using the actual data properties
        const popupContent = `
            <div>
                <h3>${properties.Landmark}</h3>
                <p><strong>Address:</strong> ${properties.Address}</p>
                <p><strong>Architect & Date:</strong> ${properties.Architect_Date}</p>
                <p><strong>Designated:</strong> ${properties.Designated}</p>
                ${properties.Link ? `<p><a href="${properties.Link}" target="_blank">More Information</a></p>` : ''}
                ${properties.Notes ? `<p><strong>Notes:</strong> ${properties.Notes}</p>` : ''}
            </div>
        `;

        new mapboxgl.Popup()
            .setLngLat(coordinates)
            .setHTML(popupContent)
            .addTo(map);
    });

    // Change cursor to pointer when hovering over points
    map.on('mouseenter', 'points-layer', () => {
        map.getCanvas().style.cursor = 'pointer';
    });

    // Change cursor back when leaving points
    map.on('mouseleave', 'points-layer', () => {
        map.getCanvas().style.cursor = '';
    });

        
});
```
=== "index.html"

    ``` html
 <!DOCTYPE html>
  <html lang="en">

  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mapbox GL JS map</title>
    <link rel='stylesheet' href='https://api.mapbox.com/mapbox-gl-js/v3.15.0/mapbox-gl.css'><link rel="stylesheet" href="./style.css">
    

  </head>
    
  <body>
  <h1> Heritage Map of Berkeley</h1>
  <div id="map"></div>
    <script src='https://api.mapbox.com/mapbox-gl-js/v3.15.0/mapbox-gl.js'></script><script  src="./script.js"></script>

  </body>
  
</html>

    ```

=== "style.css"

    ``` css
   body { margin: 0; padding: 0; }
#map { position: absolute; top: 0; bottom: 0; width: 100%; }

h1 {
    position: absolute;
    top: 20px;
    left: 20px;
    z-index: 1000;
    background: rgba(255, 255, 255, 0.9);
    padding: 15px 20px;
    margin: 0;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    font-family: 'Helvetica Neue', Arial, Helvetica, sans-serif;
    font-size: 24px;
    color: #333;
}

.mapboxgl-popup {
        max-width: 400px;
        font:
            12px/20px 'Helvetica Neue',
            Arial,
            Helvetica,
            sans-serif;
    }
    ```
=== "script.js"

```
mapboxgl.accessToken = 'pk.eyJ1IjoiY3dpbG1vdHQiLCJhIjoiY2s2bWRjb2tiMG1xMjNqcDZkbGNjcjVraiJ9.2nNOYL23A1cfZSE4hdC9ew';
const map = new mapboxgl.Map({
        container: 'map', // container ID
        style: 'mapbox://styles/cwilmott/cmg5px11u00ef01sm3fr65ro0',
        center: [-122.27, 37.8], // starting position [lng, lat]. Note that lat must be set between -90 and 90
        zoom: 9 // starting zoom
    });

map.on('load', function() {
    map.addSource('points-data', {
        type: 'geojson',
        data: 'https://raw.githubusercontent.com/cwilmott/c183-webmap/refs/heads/main/data/183-data.geojson'
    });

    map.addLayer({
        id: 'points-layer',
        type: 'circle',
        source: 'points-data',
        paint: {
            'circle-color': '#4264FB',
            'circle-radius': 6,
            'circle-stroke-width': 2,
            'circle-stroke-color': '#ffffff'
        }
    });

    // Add click event for popups
    map.on('click', 'points-layer', (e) => {
        // Copy coordinates array
        const coordinates = e.features[0].geometry.coordinates.slice();
        const properties = e.features[0].properties;
        
        // Create popup content using the actual data properties
        const popupContent = `
            <div>
                <h3>${properties.Landmark}</h3>
                <p><strong>Address:</strong> ${properties.Address}</p>
                <p><strong>Architect & Date:</strong> ${properties.Architect_Date}</p>
                <p><strong>Designated:</strong> ${properties.Designated}</p>
                ${properties.Link ? `<p><a href="${properties.Link}" target="_blank">More Information</a></p>` : ''}
                ${properties.Notes ? `<p><strong>Notes:</strong> ${properties.Notes}</p>` : ''}
            </div>
        `;

        new mapboxgl.Popup()
            .setLngLat(coordinates)
            .setHTML(popupContent)
            .addTo(map);
    });

    // Change cursor to pointer when hovering over points
    map.on('mouseenter', 'points-layer', () => {
        map.getCanvas().style.cursor = 'pointer';
    });

    // Change cursor back when leaving points
    map.on('mouseleave', 'points-layer', () => {
        map.getCanvas().style.cursor = '';
    });

        
});
```








