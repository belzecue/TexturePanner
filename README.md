# TexturePanner [![License](https://img.shields.io/badge/License-MIT-lightgrey.svg?style=flat)](http://adultlink.mit-license.org) [![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/adultlink/5usd)
![IntroImage](Screenshots/Misc.gif)

This shader is a glorified texture panner, with a few extra features oriented towards adding variety. By getting creative with mesh geometry and textures, we can achieve a wide range of results.

It can be modified through [Amplify Shader Editor](http://amplify.pt/unity/amplify-shader-editor) and contributions to the project are always welcome!

Project developed using **Unity 2017.4.8f1**. Please use this version if you are planning on contributing.

# Table of contents
1. [Setup](#setup)
   - 1.1 [Getting started](#getting-started)
   - 1.2 [Using your own meshes](#using-your-own-meshes)
2. [Usage & parameters](#usage-parameters)
   - 2.1 [General settings](#general-settings)
   - 2.2 [Scrolling & rotation](#scrollingrotation)
   - 2.3 [Scanlines](#scanlines)
   - 2.4 [Stretching](#stretching)
   - 2.5 [Displacement](#displacement)
3. [Examples](#examples)
4. [License](#license)

# Setup
## Getting started
The setup for this shader is minimal, all you need to do is create a new material and assign a base texture, which will be scrolled over the UVs. Assign this new material to a quad and there we go, we now have a scrolling texture:

![BasicExample](Screenshots/BasicExample.gif)

When using textures that allow transparency (.png for instance), this information is taken into consideration:

![BasicExample2](Screenshots/BasicExample2.gif)

## Using your own meshes

A series of meshes ready to use are included within this repository, but depending on your project, you will most likely have the need to use meshes other than these. In this case, we need to be mindful of the UVs.

If we use the default cube mesh in Unity as our mesh, the texture we chose will scroll over every face:

![BasicExample3](Screenshots/BasicExample3.gif)

Furthermore, we can see both side faces are going against each other, thus breaking the scrolling effect. We need to lay out the UVs of our mesh in a way that allows for easy scrolling. For instance, if our goal is to make the arrows loop through the side faces of the cube, we need to get rid of the top and bottom faces, and orient all the side faces in the same direction.

It is recommended to layout all the faces inside the UV square for cleaner results. This means our texture will stretch across all the faces, which me may not want, but we can always tile it in the inspector:

![BlenderCubeUVs](Screenshots/BlenderCubeUVs.gif)
![BlenderCubeExample](Screenshots/BlenderCubeExample.gif)

# Usage, parameters

**WIP**

This shader is comprised of a few "modules", that work independently and can be activated/deactivated without affecting each other.

![Parameters](Screenshots/Parameters.png)

## General settings

Texture tiling, offset and color mixing fall under this category. Color mixing offers a few options:
- Original: The original color of the texture is respected, no action is taken.
- Hueshift: The hue of the texture is shifted by the hue value of the selected color.
- Multiply: Direct multiplication of both colors.
- Replace: Gives a new color to the whole texture.

## Scrolling/Rotation
## Scanlines
## Stretching
## Displacement

# Examples

3D space loading rings are a great application for scrolling textures, since you can easily create unique-looking pieces.

![LoadingRings](Screenshots/LoadingRings.gif)

Conveyor belts are the prime example for texture scrolling, since they illustrate the concept perfectly.

A slightly different version of the shader (TexturePanner_opaque) is used for these ones, which can cast and receive shadows.

![ConveyorBelts](Screenshots/ConveyorBelts.gif)

Texture panning is a simple concept that we can take advantage of to create a huge variety of effects.

We are just simply scrolling said texture over a mesh, but the results we can achieve are really diverse.

By stretching the mesh and scrolling the texture at high speeds, we get a twitchy behaviour, resembling the appearance of spaceship thrusters.

![ThrustersExample](Screenshots/Thrusters.gif)

Given the appropriate mesh and UV setup, this shader can be used to achieve that futuristic cyberpunk neon ad look, including scanlines.

Also, _A E S T H E T I C_.

![Buildings](Screenshots/Buildings.gif)

Imagination is the limit!

Experiment with new geometries and effect combinations. Sometimes the most fun outcomes are the result of just toying around!

# License
MIT License

Copyright (c) 2018 Guillermo Angel

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
