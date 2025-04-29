This is a sample page for a cartography tutorial. It is written in [Markdown](https://www.markdownguide.org/) (.md)

I recommend setting up a development environment on your computer using Visual Studio Code (it's free), because this will help you with the formatting for the .md docs.

To make a new page, just add a new .md doc in the /docs folder

The reason we use this is because the code snippets are so so much easier to use for students.

Like this:
``` html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Mapbox GL JS map</title>
<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no">
<link href="https://api.mapbox.com/mapbox-gl-js/v3.11.0/mapbox-gl.css" rel="stylesheet">
<script src="https://api.mapbox.com/mapbox-gl-js/v3.11.0/mapbox-gl.js"></script>
<style>
body { margin: 0; padding: 0; }
#map { position: absolute; top: 0; bottom: 0; width: 100%; }
</style>
</head>
<body>
<div id="map"></div>
<script>
	mapboxgl.accessToken = 'pk.eyJ1IjoiY3dpbG1vdHQiLCJhIjoiY2s2bWRjb2tiMG1xMjNqcDZkbGNjcjVraiJ9.2nNOYL23A1cfZSE4hdC9ew';
    const map = new mapboxgl.Map({
        container: 'map', // container ID
        center: [-74.5, 40], // starting position [lng, lat]. Note that lat must be set between -90 and 90
        zoom: 9 // starting zoom
    });
</script>

</body>
</html>
```