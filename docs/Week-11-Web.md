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

!!! tip "For Tech-Tortoises"
        Your ```index.html``` file will look different to the one on Code Pen - this is because when you downloaded your code pen files, it automatically linked your         ```style.css``` and ```script.js``` files into your index.html as it packaged them. It needs to do this so you html knows where to find your style and your javascript!

### Check it still works!
On your desktop, locate your index.html file and drag it into a browser - you should see your map (as long as you're on the internet!). 
DO NOT CLOSE THIS BROWSER WINDOW - we will be using this to test the updates to your map when we add your markers and such.

## 2. Add Markers

Now, we are going to add our markers. To do this, we have to do two things:
1)    Make a link to our geojson data
2)    Add it as a marker (or symbol) layer to our webmap

### create ```map.on('load')``` function
- Map onLoad function.

### a. Add Source Data
- add Geojson raw source

### b. Add Your Markers / Symbol Layer
- Add Markers constant

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

## 3. Add Pop-Ups to Markers

Now overlay pop-ups ontol markers 

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





