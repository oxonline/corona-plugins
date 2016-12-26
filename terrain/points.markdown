# terrain.points

|                      | &nbsp;
| -------------------- | ---------------------------------------------------------------
| __Type__             | [Table](https://docs.coronalabs.com/api/type/Table.html)
| __Object__           | [Terrain](Readme.markdown)
| __Library__          | [terrain.*](Readme.markdown)
| __Keywords__         | points, coordinates
| __See also__         |


## Overview

Exposes the point data should you need to access it. You can retrieve the number of points in use by the terrain using ``````#terrain.points``````. Each point consists of a 2-value array of (x, y).

## Example

``````lua
local terrain = require 'plugin.terrain'

local terra = terrain.createTerrain({
    x = 480,
    y = 400,
    width = 960,
    minHeight = 100,
    maxHeight = 480,
    physics = true,
    complexity = 5,
    smoothness = 3.5,
    fill = { type="image", filename="assets/underground.png" },
    -- fill = { type = "gradient", color1 = { 1, 1, 0.4 }, color2 = { 1, 1, 0, 0.2 }, direction = "down" },
    -- ground = { type="image", filename="assets/ground.png" },
    ground = { type = "gradient", color1 = { 0, 1, 0.4 }, color2 = { 0, 1, 0, 0.2 }, direction = "down" },
    groundHeight = 4,
    -- randomSeed = 1,
})

local i, x, y
for i = 1, #terra.points do
	x, y = unpack(terra.points[i])
	print("x=" .. x, "y=" .. y)
end
``````
