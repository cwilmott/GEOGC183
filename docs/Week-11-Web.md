# Week 11 Web Map

In-process lab addressing the basics of moving geodata and a stylized basemap onto a web server for display.  
 
 [Week 11 Worksheet: Web Map]()

## 1. Download your code

## 2. Add Markers

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
        
        // Create popup content - customize this based on your data properties
    const popupContent = `
        <div>
            <h3>${properties.name || 'Point'}</h3>
            <p>${properties.description || 'No description available'}</p>
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

