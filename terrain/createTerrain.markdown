# terrain.createTerrain()

|                      | &nbsp;
| -------------------- | ---------------------------------------------------------------
| __Type__             | [Function](http://docs.coronalabs.com/api/type/Function.html)
| __Library__          | [terrain.*](Readme.markdown)
| __Return value__     | [table](http://docs.coronalabs.com/api/type/Table.html)
| __Keywords__         | terrain, landscape, ground, procedural
| __See also__         | [terrain:addBody()](addBody.markdown), [terrain:getY()](getY.markdown), [terrain:removeSelf()](removeSelf.markdown), [terrain:translate()](translate.markdown)


## Overview

This function acts as a constructor for the terrain object. It creates a new terrain based on the attributes passed in, and returns as reference to it.


## Syntax

	local terra = terrain.createTerrain({
        ...
    })

##### x <small>(required)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ Defines the centre X position for the terrain object - i.e. width / 2.

##### y <small>(required)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ Defines the centre Y position for the terrain object - this will be maxHeight / 2.

##### width <small>(required)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ The width of the terrain object.

##### fill <small>(required)</small>
_[Paint](https://docs.coronalabs.com/api/type/Paint/index.html)._ Defines the fill you want to use for the terrain. You should be fine using pretty much any Corona shape fill definition – solid fills, gradients or images.

##### ground <small>(optional)</small>
_[Paint](https://docs.coronalabs.com/api/type/Paint/index.html)._ You can also specify a ground fill to overlay the top of the terrain. This may also be any Corona shape fill definition – solid fills, gradients or images.

##### groundHeight <small>(optional)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ If using a fill where the ground height cannot be determined – i.e. a non-image: solid or gradient fill – you can set the required height using this setting. If required but not set, it defaults to 2.

##### minHeight <small>(optional)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ The minimum height any point in the terrain can be – must be greater than 0. Defaults to 50.

##### maxHeight <small>(optional)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ The maximum height any point in the terrain can be – must be greater than minHeight. Defaults to 300.

##### leftHeight <small>(optional)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ The height you want the left-most point to be. The terrain will start at this height. If not set, the left-most height can be anything between minHeight and maxHeight.

##### rightHeight <small>(optional)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ The height you want the right-most point to be. The terrain will end at this height. If not set, the right-most height can be anything between minHeight and maxHeight.

##### physics <small>(optional)</small>
_[Boolean](https://docs.coronalabs.com/api/type/Boolean.html)/[Table](https://docs.coronalabs.com/api/type/Table.html)._ The type of physics to apply to the object (or none if not set). Set to true to enable default physics, or use a valid table of values per the Corona physics [addBody -> params documentation](https://docs.coronalabs.com/api/library/physics/addBody.html). When using physics, ensure you have initialised the physics engine first by calling physics.start().

##### complexity <small>(optional)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ Defines the complexity of the landscape generated. Defaults to 6 and must be a whole number. The number of points will be determined using this number as follows: 2(complexity + 1) + 1. For example, a complexity of 6 will result in 129 points.

##### smoothness <small>(optional)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ Determines how smooth the resulting landscape is by restricting the variance between points based on this value. Defaults to 5 can can be a floating point value. The lower the number, the more jagged (mountainous) the terrain will be, the higher the number, the smoother it will be.

##### parent <small>(optional)</small>
_[GroupObject](https://docs.coronalabs.com/api/type/GroupObject/index.html)._ The parent group to insert the terrain group into. Defaults to the current stage.

##### randomSeed <small>(optional)</small>
_[Number](https://docs.coronalabs.com/api/type/Number.html)._ If you want to consistently regenerate the exact same terrain, specify a random seed to use. This works cross-device as it uses a pure Lua implementation of the Mersenne Twister rather than any built-in random number generator which is usually device-specific.


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
``````
