# Terrain examples

##### [Terrain documentation](terrain/Readme.markdown)

## Some of the examples below use the following images. You may use these images without permission for testing purposes only.

![ground.png](ground.png)
![underground.png](underground.png)

## Basic terrain using textures

``````
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

timer.performWithDelay(1000, function()
    local r = math.random(3, 10)
    local circle = display.newCircle(math.random(0, 300), 0, r)
    circle.fill = {1, 1, 1}
    physics.addBody(circle, {shape="circle", radius=r, bounce=0.5})
end, 0)
``````

![example1.png](example1.png)

## Basic terrain using gradients

``````
local terra = terrain.createTerrain({
    x = 480,
    y = 400,
    width = 960,
    minHeight = 100,
    maxHeight = 480,
    physics = true,
    complexity = 5,
    smoothness = 3.5,
    fill = { type = "gradient", color1 = { 1, 0.5, 0 }, color2 = { 1, 1, 0, 0.2 }, direction = "down" },
    ground = { type = "gradient", color1 = { 0, 1, 0.4 }, color2 = { 0, 1, 0, 0.2 }, direction = "down" },
    groundHeight = 8,
})

timer.performWithDelay(1000, function()
    local r = math.random(3, 10)
    local circle = display.newCircle(math.random(0, 300), 0, r)
    circle.fill = {1, 1, 1}
    physics.addBody(circle, {shape="circle", radius=r, bounce=0.5})
end, 0)
``````

![example2.png](example2.png)

## A smoother terrain

``````
local terra = terrain.createTerrain({
    x = 480,
    y = 400,
    width = 960,
    minHeight = 100,
    maxHeight = 480,
    physics = true,
    complexity = 5,
    smoothness = 10,
    fill = { type="image", filename="assets/underground.png" },
    ground = { type="image", filename="assets/ground.png" },
})

timer.performWithDelay(1000, function()
    local r = math.random(3, 10)
    local circle = display.newCircle(math.random(0, 300), 0, r)
    circle.fill = {1, 1, 1}
    physics.addBody(circle, {shape="circle", radius=r, bounce=0.5})
end, 0)
``````

![example3.png](example3.png)

## A more mountainous terrain

``````
local terra = terrain.createTerrain({
    x = 480,
    y = 400,
    width = 960,
    minHeight = 100,
    maxHeight = 480,
    physics = true,
    complexity = 5,
    smoothness = 1,
    fill = { type="image", filename="assets/underground.png" },
    ground = { type="image", filename="assets/ground.png" },
})

timer.performWithDelay(1000, function()
    local r = math.random(3, 10)
    local circle = display.newCircle(math.random(0, 300), 0, r)
    circle.fill = {1, 1, 1}
    physics.addBody(circle, {shape="circle", radius=r, bounce=0.5})
end, 0)
``````

![example4.png](example4.png)

## Plotting points along the terrain

``````
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

![example5.png](example5.png)
