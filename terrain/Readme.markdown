# terrain: Plugin API Docs

|                      | &nbsp;
| -------------------- | ---------------------------------------------------------------
| __Type__             | [TYPE](http://docs.coronalabs.com/api/type/Library.html)
| __Corona Store__     | [terrain](http://store.coronalabs.com/plugin/terrain)
| __Keywords__         | terrain, landscape, ground, procedural
| __See also__         |

## Overview

The terrain plugin can be used in your [Corona](https://coronalabs.com/products/corona-sdk/) project. It allows you to generate random terrains for use in your games. It uses a variation of the 2d midpoint algorithm for terrain generation, mixed with a Mersenne Twister random number generator to ensure consistent generation of terrains cross-platform.


## Syntax

	local terrain = require "plugin.terrain"

    local terra = terrain.createTerrain({
        x = 250,
        y = 150,
        width = 400,
        minHeight = 100,
        maxHeight = 200,
        physics = true,
        complexity = 2,
        smoothness = 3.5,
        fill = { type="image", filename="assets/underground.png" },
        ground = { type="image", filename="assets/ground.png" }
    })


### Constructor

##### [terrain.createTerrain()](createTerrain.markdown)


### Methods

##### [object:addBody()](addBody.markdown)

##### [object:getY()](getY.markdown)

##### [object:removeSelf()](removeSelf.markdown)

##### [object:translate()](translate.markdown)


### Properties

##### [object.points](points.markdown)

##### [object.poly](poly.markdown)


## Project Configuration

### Corona Store Activation

In order to use this plugin, you must activate the plugin at the [Corona Store](http://store.coronalabs.com/plugin/terrain).


### SDK

When you build using the Corona Simulator, the server automatically takes care of integrating the plugin into your project.

All you need to do is add an entry into a `plugins` table of your `build.settings`. The following is an example of a minimal `build.settings` file:

``````
settings =
{
	plugins =
	{
		-- key is the name passed to Lua's 'require()'
		["plugin.terrain"] =
		{
			-- required
			publisherId = "net.oxonline",
		},
	},
}
``````

### Enterprise

If you have activated this plugin, you can download this plugin from the corresponding plugin page in the [Corona Store](http://store.coronalabs.com/plugin/terrain).


## Platform-specific Notes

None


## Resources

### Sample Code

You can access sample code [here](SAMPLE_CODE_URL).

### Support

More support is available from the Oxonline Games team:

* [E-mail](mailto://plugins@oxonline.net)
* [Plugin Publisher](http://oxonline.net)


## Compatibility

| Platform                     | Supported
| ---------------------------- | ----------------------------
| iOS                          | Yes
| Android                      | Yes
| Android (GameStick)          | Yes
| Android (Kindle)             | Yes
| Android (NooK)               | Yes
| Android (Ouya)               | Yes
| Mac App                      | Yes
| Win32 App                    | Yes
| Windows Phone 8              | Yes
| Corona Simulator (Mac)       | Yes
| Corona Simulator (Win)       | Yes
