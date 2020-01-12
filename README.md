# SharpText

**Disclaimer**: This project is a work in progress and will most likely have bugs (but it does seem to work OK from my experiences so far). Feel free to give it a go and please raise any bugs or feature requests as an issue on this repo. I would be more than happy to look at any PRs for such improvements.

## Description

This is a GPU accelerated text renderer implemented in C#. It implements the excellent technique [discussed by Evan Wallace here](https://medium.com/@evanwallace/easy-scalable-text-rendering-on-the-gpu-c3f4d782c5ac) (thanks to Evan for explaining in detail how the technique works and providing example code :) ). It comprises of a few steps:

1. Read in a font file in any supported format (I chose the [Typography](https://github.com/LayoutFarm/Typography) library as it has .NET Standard support)
1. Convert the lines and Bezier curves into a set of triangles that can be rendered
1. Render the triangles out to a render target
1. Run another pass with the render target as input which renders the final text and performs sub-pixel anti-aliasing

It should reusable across rendering platforms as I have seperated out any platform/implementation specific code into different projects.

At the moment, the project structure looks like this:
* SharpText.Core - contains shared logic and platform independant code
* SharpText.Veldrid - implements an ITextRenderer for the Veldrid graphics backend
* SharpText.DemoApp - a simple demo app to show how to use this library (take a look at Program.cs to get started)

## Examples

The Demo App Using [Open Sans](https://fonts.google.com/specimen/Open+Sans)

![Demo App Screenshot](https://raw.githubusercontent.com/drjaydenm/SharpText/master/Images/demo_app.png)

Using [Amatic SC](https://fonts.google.com/specimen/Amatic+SC)

![Font](https://raw.githubusercontent.com/drjaydenm/SharpText/master/Images/font_1.png)

Using [LeArchitect](https://www.dafont.com/learchitect.font?l[]=10&l[]=1)

![Font](https://raw.githubusercontent.com/drjaydenm/SharpText/master/Images/font_2.png)

Using [Sacramento](https://fonts.google.com/specimen/Sacramento)

![Font](https://raw.githubusercontent.com/drjaydenm/SharpText/master/Images/font_3.png)

Using [Neon2](https://www.dafont.com/neon-lights.font?l[]=10&l[]=1)

![Font](https://raw.githubusercontent.com/drjaydenm/SharpText/master/Images/font_4.png)