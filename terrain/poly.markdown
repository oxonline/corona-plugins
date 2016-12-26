# terrain.poly

|                      | &nbsp;
| -------------------- | ---------------------------------------------------------------
| __Type__             | [ShapeObject](https://docs.coronalabs.com/api/type/ShapeObject/index.html)
| __Object__           | [Terrain](Readme.markdown)
| __Library__          | [terrain.*](Readme.markdown)
| __Keywords__         | shape, polygon
| __See also__         | [display.newPolygon()](https://docs.coronalabs.com/api/library/display/newPolygon.html)


## Overview

The underlying polygon object created for the terrain. As a Corona shape object, you can amend it or its underlying physics object as you see fit.

Note that you should only move it using the translate method provided to ensure the whole terrain is moved correctly.

## Example

``````lua
local polygon = terra.poly
``````
