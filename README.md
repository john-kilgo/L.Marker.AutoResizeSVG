# L.Marker.AutoResizeSVG

Leaflet plugin that resizes marker icons based on zoom level: SVG edition.

The difference between the maximum and minimum zoom level allowed on your map is broken up into three relatively equal parts: The top third of the zoom level ("zoomed in"), a mid-range, and an outer range ("zoomed out").

## How to use

[View a demo](http://john-kilgo.github.io/L.Marker.AutoResizeSVG)


Include after Leaflet:
```
<script src="../marker-resize-svg.js"></script>
```

Create an icon:

All regular L.Icon options are allowed, just be sure to append 'Array' to the name of the parameter and include three objects in the array.

```
var myIcon = L.icon({
	iconUrl: 'myicon.svg',
	iconSizeArray: 
	[
		[32, 32], [96, 96], [256, 256]
	],
	iconAnchorArray: 
	[
		[16, 32], [48, 96], [128, 256]
	]
})
```

Create a marker using this icon:
```
L.autoResizeMarkerSVG([42.486, -71.236], {icon: myIcon}).addTo(mymap);
```
In this example, the smallest size is shown when zoomed out, the mid-range size is shown when in the mid-range of the zoom, and the largest size is shown when zoomed in to the map. Reversing the order would have the smallest icon size shown when the map is zoomed in and the large icon size shown when zoomed out, in this example.


