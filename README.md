# LAB-SVGp5

LAB-SVGp5 is a Processing library intended to optimize Processing's rendering of SVG elements as PShapes.

Since Processing typically turns an SVG into a PShape, it is conventionally drawn with a shape() call. However, when drawing many instances of the SVG, this can slow down render times, as is documented in Processing's reference. 

The solution here is to add multiple instances of the SVG to a PShape group, which can then be rendered with a single call to shape() and reduce the expensive I/O to the GPU. 

The challenge is that SVGs themselves contain multiple shapes as well as colors, fills, etc. The goal of this library is to combine multiple PShapes into a group, and thereby significantly reduce the render time when an SVG is being redrawn many times.