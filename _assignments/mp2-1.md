---
layout: assignment
title: "MP2: Terrain Modeling Part 1"
index: 10
due: "Oct. 21, 2019 @ 11:59 PM"
material: ~
points: 9
rubric:
  -
    name: Runs and renders
    points: 1
    description: Program runs without crashing and renders visible polygons.
  -
    name: Commented
    points: 1
    description: Each function in your code is commented in the required style.
  - 
    name: Normals
    points: 1
    description: Normal vectors for the terrain are computed and handled correctly.
  -
    name: Terrain Generation
    points: 2
    description: The terrain is modeled using the random partition method.
  - 
    name: Elevation Color Map
    points: 2
    description: The shading of the terrain changes by mapping different ranges of elevation to different colors.
  - 
    name: Phong Shading
    points: 1
    description: Shading is accomplished using the Phong reflection model in the fragment shader.
  -
    name: Creativity
    points: 1
    description: The color map is visually interesting and the terrain exhibits good aesthethic quality (e.g. not totally random).
---

For your second Machine Problem, you will procedurally model a piece of terrain. For now, this can be a static scene. We will add interaction in the second part of the MP which will be assigned later.

You will need to implement the following:

### 1. Terrain Generation ###
Many basic terrain modeling algorithms employ something called *Perlin noise* to create a highly detailed natural appearance. Invented by Ken Perlin in 1982 while working on the movie *Tron*, Perlin noise uses randomness and repetition to synthesize 2D and 3D textures. In 1997, Perlin won an Academy Award for Technical Achievement from the Academy of Motion Picture Arts and Sciences for this contribution to graphics. Perlin noise and techniques based off of it are still widely used in games and movies today.

Realistic terrain generation in modern games require tools that do more than just model the basic underlying terrain...these tools support operations like creation of vegetation and roads and erosion. See [this talk by Ubisoft developer Etienne Carrier](https://www.youtube.com/watch?v=NfizT369g60) if you are interested in seeing the tools technical artists use these days. 
![](/img/perlin1.jpg)

For this MP we will write code to generate a basic 3D terrain. We won't be using Perlin's function...instead we will do something conceptually similar but less efficient...but easier to implement.

The first step is to create a flat, triangulated surface in which all the vertices have $$z$$ coordinates of $$0$$.
![](/img/rpart0-2.png)

After that we will repeatedly, randomly generate a plane that partitions the vertices. On one side of the plane we will increase the height of each vertex by $$delta$$. On the other side, we decrease the vertex heights by delta. After enough iterations, you should see something resembling a 3D terrain.
![](/img/rpart1.png)

Here it is without the triangle boundaries, shaded using the Phong reflectance model.
![](/img/rpart2-2.png)

If you wish to extend the basic algorithm to make it better in some way, you certainly can. It would be possible to start with a parabolic sheet instead of a flat plane to create a mountain, or maybe you want to write code that will cut a river through the terrain. 
Just keep in mind that it should use the random partitioing as a base and look as least good as the images shown in this section.

#### Technical Notes ####
+ The rectangle for your surface should have corners $$(x_{min},y_{min},0)$$ and $$(x_{max},y_{max},0)$$. To generate a random plane
first generate a random point $$p$$ in that rectangle. Then generate a random normal vector $$n$$ for the plane $$<x_n,y_n,0>$$, where $$x_n,y_n$$ is a point uniformly sampled on the unit circle. Given a vertex $$b$$, you can test which side of the plane that vertex falls on by using the dot product test $$ (b-p) \cdot n \gt  0 $$.
![](/img/dottest.jpg)

+ You will need to experiment with the parameters of algorithm to find ones that give good results. The image above used 100 iterations of partitioning on a $$64 \times 64$$ grid of vertices spanning a unit square with $$delta = 0.005$$.

+ Your implementation should generate an indexed mesh and render it using the WebGL function **`void gl.drawElements(mode, count, type, offset)`{: style="background-color: GainsBoro"}**. You should pay attention to the `type` parameter as the type **`gl.UNSIGNED_SHORT`{: style="background-color: GainsBoro"}** is the largest supported natively in WebGL 1.0. This will limit your mesh to having only 65536 vertices. If you want more, you will need to use the extension **[`OES_element_index_uint`{: style="background-color: GainsBoro"}](https://developer.mozilla.org/en-US/docs/Web/API/OES_element_index_uint)**.

+ In the Oct.7 live session, we will work on one possible approach to generating an indexed mesh structure. We will create a grid of vertices in the X-Y plane and triangulate them. You can use a Model transformation to rotate this flat terrain to position it however you want to make viewing easier. 

In order for the mesh to be shaded correctly **you will also need to generate per-vertex normals** for the mesh. Each normal is a vector perpendicular to the mesh at the vertex, and is computed as an average of the normals of the triangles that surround the vertex. These normals will be another attribute that you will need to send down to the vertex shader.

**Debugging Tips** 
- Start by generating a small flat terrain (for example 3 vertices by 3 vertices).  
 Use this to set up the view you want.
- Then, add in the ability to set the z coordinates of the vertices. Do something simple like random heights.
- Then, work on implementing the terrain generation algorithm.

### 2. Implement a perspective view of the scene ###

Your code should generate a view matrix and a perspective projection matrix in the javascript portion of the app and send them to the vertex shader...and use them to transform the vertices. You should use the [glMatrix library](http://glmatrix.net/) functions **`lookAt(out, eye, center, up)`{: style="background-color: GainsBoro"}** and **`perspective(out, fovy, aspect, near, far)`{: style="background-color: GainsBoro"}** to generate the matrices. It is up to you to understand how to specify the parameters to generate a good view. 

### 3. Implement the Phong reflection model with Phong shading ###
Implement the Phong reflection model with **Phong shading**. This means your shading calculations should be done per-fragment...meaning in the fragment shader. You can position your light source(s) anywhere in the scene as long as the rendered images are well-lit. You can use the [Gouraud shading version](https://illinois-cs418.github.io/Examples/PhongReflection/HelloPhong.html) as a starting point...it implements the Phong reflection model but in the vertex shader. You will need to compute the necessary vetors in the vertex and then send varying versions of them to the fragments shader. **You need to normalize these varying vectors in the fragment shader**. In addition, you will need to change how the shader handles material colors...you will need to generate a color for the terrain based on elevation as described below.

### 4. Implement an elevation-based colormap for the terrain ###

In your shading calculation, you should assign material colors (the $$k$$ values in the Phong model) to vertices based on the elevation of the vertex. If you use the z-coordinate as elevation, that means you should base your color assignment on the value of the z-coordinate. For example, you could define four different intervals of z values and assign blue to the vertices in the lowest interval, green to the second lowest, brown to the second highest, and white to the highest. **This can be done in the vertex shader or fragment shader.** Using the shader programs to generate the material colors will be mroe performant than doiing so in your JS code. A useful reference for writing the GLSL code to do this is available on [www.shaderific.com](https://www.shaderific.com/glsl).

![Example Terraing](/img/terrain.PNG)

In the image above, you can see interpolation effects as colors are blended together. One way to achieve this look would be to assign the material colors in the vertex shader and pass them as varyings to the fragment shader to complete the shading process.

Or, you could generate material colors in fragment shader...you can implement your own linear interpolation based on elevation...or you could decide not to interpolate and to have a stratified appearance or something else more sophisticated.

### 5. Comment appropriately ###

You should comment each file with an author comment and comment each function you write with a header. Use JSDoc comments with the appropriate tags and types.
Details can be found in the Google JavaScript Style Guide. 
