# object:addBody()

|                      | &nbsp;
| -------------------- | ---------------------------------------------------------------
| __Type__             | [Function](https://docs.coronalabs.com/api/type/Function.html)
| __Object__           | [Terrain](Readme.markdown)
| __Library__          | [terrain.*](Readme.markdown)
| __Return value__     | none
| __Keywords__         | bodies, physics, body, shape, outline
| __See also__         | [physics.addBody()](https://docs.coronalabs.com/api/library/physics/addBody.html)


## Overview

Allows you to add a new physics body to the terrain. If one already exists, you should remove it before attempting to add a new one. Just calling terrain:addBody will add a default physics body as if you’d called it using terrain:addBody(true). Alternatively call using a Corona physics table per the addBody documentation (params).


## Example

``````lua
local terrain = require 'plugin.terrain'

local terra = terrain.createTerrain({
    x = 480,
    y = 400,
    width = 960,
    minHeight = 100,
    maxHeight = 480,
    complexity = 5,
    smoothness = 3.5,
    fill = { type="image", filename="assets/underground.png" },
    -- fill = { type = "gradient", color1 = { 1, 1, 0.4 }, color2 = { 1, 1, 0, 0.2 }, direction = "down" },
    -- ground = { type="image", filename="assets/ground.png" },
    ground = { type = "gradient", color1 = { 0, 1, 0.4 }, color2 = { 0, 1, 0, 0.2 }, direction = "down" },
    groundHeight = 4,
    -- randomSeed = 1,
})

terra:addBody({
    bounce = 0.5,
    friction = 2,
})
``````
