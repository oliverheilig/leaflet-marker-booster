# leaflet-marker-booster
Boosted performance and usability for the Leaflet CircleMarker

Demo (10.000 locations):
https://oliverheilig.github.io/leaflet-marker-booster

As feature here:
https://ptv-logistics.github.io/xserverjs/#poi-locator

## Purpose
The Leaflet rendering performance of client-side symbols doesn't scale well for a larger set of locations.
There are some plugins which help to avoid this problem by clustering https://github.com/Leaflet/Leaflet.markercluster,
but there are scenarios where rendering all locations at ther actual positions generates a better visualization an usability. 
leaflet-marker-booster is a snap-in extension for Leaflet, which modifies the standard L.CircleMarker.

## Rendering Boost
Typically a marker is rendered as cirlce with a filling and a stroke. The stroke is important to differentiate
overlapping markers. But performance-wise strokes are very expensive. leaflet-marker-booster provides an additional
option for the CircleMarker, wich produces the same result by rendering two filled circles:
One larger with the stoke color, and a smaller with the fill color on top. This is about 50% faster than
the standard marker.

Another elegant way to distingish markers is rendering circles with a gradient brush. This does not only look nice,
but requires only one filled circle. The performance is about 100% faster than the standard marker.

## Popup anchoring
Another issue of the standard marker is the behavior of the popup when clicking. The popup is displayed at the
click-coordinate, and not at the center of the marker. And if the map gets zoomed in and out, the popup gets
shifted away. With leaflet-marker-cluster the popup gets snapped at the upper thirds of the marker and stays there.
Note this feature is also available if no boostType is set.

## Two new marker tyes
ball...
balloon...

## Logarithmic map scaling
It's often useful to scale the markers when zooming in...

## fixes for desktop
clickTolerance...