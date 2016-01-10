![PlayCanvas](http://static.playcanvas.com/images/logo/Playcanvas_LOGOSET_SMALL-06.png)

# PlayCanvas WebGL Game Engine

PlayCanvas is an open-source game engine. It uses HTML5 and WebGL to run games and other interactive 3D content in all modern browsers without the need for a plugin.

## Project Showcase

Many games and apps have been published using the PlayCanvas engine. Here is a small selection:

[![TANX](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/4373/45093/ESR5DQ-image-25.jpg)](http://playcanv.as/p/aP0oxhUr) [![Car](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/23510/347824/7ULQ3Y-image-25.jpg)](http://car.playcanvas.com/) [![Swooop](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/12/4763/TKYXB8-image-25.jpg)](http://playcanv.as/p/JtL2iqIH)
<br>
[![Afterglow](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/8/341194/MEMET7-image-25.jpg)](http://afterglowskigame.dareville.com/) [![Star-Lord](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/4373/333626/BGQN9H-image-25.jpg)](http://playcanv.as/p/SA7hVBLt) [![Orange Room](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/23510/345310/BKST60-image-25.jpg)](http://playcanv.as/p/1ha5glKf)
<br>
[![Steampunk Slots](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/23510/344862/VH0NOH-image-25.jpg)](http://playcanv.as/p/nL1dYbMv) [![Casino](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/14928/349824/U88HJQ-image-25.jpg)](http://casino.playcanvas.com/) [![Seemore](https://s3-eu-west-1.amazonaws.com/images.playcanvas.com/projects/14705/319531/O4J4VU-image-25.jpg)](http://seemore.playcanvas.com/)

You can see more games on the [PlayCanvas website](https://playcanvas.com/explore).

## Features

The PlayCanvas Engine is a fully featured 3D game engine.

* **Graphics**
    * WebGL-based 3D renderer
    * Physically based rendering (PBR)
    * Directional, point and spot lights (all of which can cast shadows)
    * Static and skinned meshes
    * GPU Particle engine with editor
    * PostFX library: bloom, edge detect, FXAA, vignette, etc
    * Seamless default material support from Maya, 3DS Max, Blender, etc.
    * Full model export pipeline from Maya, 3DS Max, Blender, etc via [PlayCanvas Tools](https://playcanvas.com)
* **Collision & Physics**
    * Full integration with 3D rigid-body physics engine [ammo.js](https://github.com/kripken/ammo.js)
* **Audio**
    * 3D Positional audio via Web Audio API
* **Resource Loading**
    * Simple and powerful resource loading
* **Entity / Component System**
    * Built-in components: audiosource, animation, camera, collision, light, rigidbody, script
* **Scripting system**
    * Write game behaviours by attaching JavaScript to game entities.
* **Input**
    * Mouse, Keyboard, Touch, Gamepad support

## Usage

Here's a super-simple Hello World example - a spinning cube!

```html
<script>
    // Create a PlayCanvas application
    var canvas = document.getElementById("application-canvas");
    var app = new pc.Application(canvas, {});
    app.start();

    // Fill the available space at full resolution
    app.setCanvasFillMode(pc.FILLMODE_FILL_WINDOW);
    app.setCanvasResolution(pc.RESOLUTION_AUTO);

    // Create box entity
    var cube = new pc.Entity();
    cube.addComponent("model", {
        type: "box"
    });

    // Create camera entity
    var camera = new pc.Entity();
    camera.addComponent("camera", {
        clearColor: new pc.Color(0.1, 0.1, 0.1)
    });

    // Create directional light entity
    var light = new pc.Entity();
    light.addComponent("light");

    // Add to hierarchy
    app.root.addChild(cube);
    app.root.addChild(camera);
    app.root.addChild(light);

    // Set up initial positions and orientations
    camera.setPosition(0, 0, 3);
    light.setEulerAngles(45, 0, 0);

    // Register an update event
    app.on("update", function (deltaTime) {
    	cube.rotate(10 * deltaTime, 20 * deltaTime, 30 * deltaTime);
    });
</script>
```

Want to play with the code yourself? Edit it on [CodePen](http://codepen.io/playcanvas/pen/NPbxMj).

## Examples

See all the [examples](http://playcanvas.github.io) here or browse them locally in the examples directory

## How to build

* Ensure you have Python installed (supported version is 2.7)
* Ensure you have [Java](https://java.com/en/download/) installed.

Then, to execute a build of the engine to the build/output folder, do:

    cd build
    python build.py

## Documentation

Full documentation available on the [PlayCanvas Developer](http://developer.playcanvas.com) site including [API reference](http://developer.playcanvas.com/en/api/)

## Releases

A full list of Releases and Release Notes is available [here](https://github.com/playcanvas/engine/releases).

## How to get models?

To convert any models created using a 3D modelling package see [this page](http://developer.playcanvas.com/en/engine/) in the developer documentation.

## Getting Help

[**Answers**](http://answers.playcanvas.com) - Use PlayCanvas Answers to ask specific questions about how to achieve something with the engine

[**Forums**](http://forum.playcanvas.com) - Use the forum to have more general conversions about PlayCanvas and the Engine

## Contributing

What to help us make the best damn 3D engine on the web? Great!

### Github Issues

Please use Github issues to report bugs or request features.

### Reporting bugs

Please follow these steps to report a bug

1. **Search for related issues** - search the existing issues so that you don't create duplicates

2. **Create a testcase** - Please create the smallest isolated testcase that you can that reproduces your bug

3. **Share as much information as possible** - everything little helps, OS, browser version, all that stuff.

## PlayCanvas Platform

The PlayCanvas Engine is an open source game engine which you can use to create games or render 3D in the browser. In addition to the engine we also make the [PlayCanvas development platform](https://playcanvas.com/) which features a level design tool, asset management and a hosting and publishing service.

## License

The PlayCanvas Engine is released under the [MIT](http://opensource.org/licenses/MIT) license. See LICENSE file.
