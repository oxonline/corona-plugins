# object:translate()

|                      | &nbsp;
| -------------------- | ---------------------------------------------------------------
| __Type__             | [Function](https://docs.coronalabs.com/api/type/Function.html)
| __Object__           | [Terrain](Readme.markdown)
| __Library__          | [terrain.*](Readme.markdown)
| __Return value__     | none
| __Keywords__         | translate, x, y, positioning
| __See also__         | [displayObject.translate()](https://docs.coronalabs.com/api/type/DisplayObject/translate.html)


## Overview

Effectively adds values to the object.x and object.y properties of all pieces of a terrain object, thus changing its screen position.

## Example

``````lua
-- Move the terrain by 200 across, and 100 down.
local dX, dY = 200, 100 
terra:translate(dX, dY)
``````
