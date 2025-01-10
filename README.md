## Overview
This application displays a service area map that the user can search to verify if their address is within the service area.

## Mechanics
A non-interactive map is rendered using the MapLibre GL JS mapping library and the MapTiler vector tiles API. 

The map displays a polygon representing the company's service area, which is defined by a string of geojson hard-coded into the script.

The input field in the top left corner allows the user to submit their address to see if it is covered by the company's service area. Autocomplete and geocoding (address to Lon/Lat) is powered by the MapTiler Geocoding Control library and API. 

Checking whether the queried location is inside the service area is accomplished using the Turf.js library's turf.booleanPointInPolygon function. 

## Extensibility and Modification
Further expansion is possible by using turf.js's turf.distance function to calculate the distance from the company's headquarters and using a simple equation to approximate a service time. 

If the company's service area changes it will need to be redefined as a geojson formatted polygon and inserted into the script. 
