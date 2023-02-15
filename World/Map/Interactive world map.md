---
share: false
---

```leaflet
id: nrmap
image: 
    - [[Flat (Political unlabeled).png|Political]]
    - [[Terrain (Blank).png|Blank]]
    - [[Terrain (Biomes).png|Biomes]]
imageOverlay: 
    - [ [[_Grid overlay.png|Grid]] ]
    - [ [[_Degrees overlay.png|Degrees grid (bad)]] ]
    - [ [[_Political labels 1.png|Countries]] ]
    - [ [[_Political labels 2.png|States]] ]
    - [ [[_Political labels 3.png|Cities]] ]
bounds: 
    - [0, 0]
    - [3306.930693069307, 7928.783382789318]
# math is [image dimension / (pixels / kilometers) = bounds]
# one cell width is 337px, one cell height is 404px
# latitude for full 4810 height instead of 4000: 3976.584158415842
height: 800px
lat: 1653.465346534654
long: 3964.391691394659
minZoom: -3.5
maxZoom: 1
defaultZoom: -3.5
zoomDelta: 0.5
unit: kilometers
scale: 1
markerFolder:
    - Nova-Regna/World/Map
filterTag:
    - maplocation
```

Due to the fact that this map is very old and little things like "planning" or "standards" weren’t considered at the time, the aspect ratio of the original map grid is not 1:1, as you can see on the [[Earth]] page, and the grid only accounts for ±75° of latitude rather than the full ±90°. The result is that this interactive map is slightly squished so that each square on the grid is actually a square instead of a tall rectangle. It looks a little funny. Pay it no mind.

This map is only viewable from within Obsidian, and if you can’t see it, you need to install the [Leaflet plugin](obsidian://show-plugin?id=obsidian-leaflet-plugin). Because of the way this plugin works, it’s easy to measure distance accurately between two points, but the coordinates - which you can copy to your clipboard by shift-clicking anywhere on the map - are nonsensical, so they must still be calculated manually. The [[_Degrees grid.png|degrees grid]] and [[_Minutes grid.png|minutes grid]] are there for use in an image editor - zoom in and scale the degrees grid into a square of the full grid, and the minutes grid into a square of the degrees grid - if you want that.

You can also convert the nonsense Y and X coordinates that the map gives you into sensible decimal coordinates like this:

```
lat = Y * (75 - -75) / 3306.9306 + -75
lon = X * (180 - -180) / 7928.7833 + -180
```

You can then take the decimal coordinates and convert them to the preferred DMS coordinates elsewhere, and you can drop the seconds if you want, or at least drop any decimal precision from them.

However, coordinates are no longer entirely necessary either. The original point in using coordinates was to pinpoint locations that are unlabeled on the map, since it’s a static PNG that won’t get new labels added to it, but this interactive map solves that problem with the ability to place pins anywhere that link to the appropriate page. Coordinates are still cool though.