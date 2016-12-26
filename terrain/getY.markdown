# object:getY()

|                      | &nbsp;
| -------------------- | ---------------------------------------------------------------
| __Type__             | [Function](https://docs.coronalabs.com/api/type/Function.html)
| __Object__           | [Terrain](Readme.markdown)
| __Library__          | [terrain.*](Readme.markdown)
| __Return value__     | [Table](https://docs.coronalabs.com/api/type/Table.html)
| __Keywords__         | position, location, coordinates
| __See also__         |


## Overview

Assists with positioning objects on a terrain, for a given value of x, which must be between 0 and width.

## Return value

Returns a table containing the following data:

##### x

The X position on the landscape (i.e. the value sent in with the call).

##### y

The Y position on the landscape at X.

##### screenX

The X position as mapped to the screen.

##### screenY

The Y position as mapped to the screen.


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
    ground = { type="image", filename="assets/ground.png" },
})

local i, x, pos
for i = 1, 100 do
    x = math.random(0, terra.opts.width)
    pos = terra:getY(x)
    if pos then -- i.e. if within bounds
        local circle = display.newCircle(pos.screenX, pos.screenY, 2)
        circle.fill = {1, 0, 0}
    end
end
``````
