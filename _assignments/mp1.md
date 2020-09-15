---
layout: assignment
title: "MP1: Dancing Logo"
index: 10
due: "Sept. 16, 2020 @ 11:59 PM"
material: ~
points: 10
rubric:
  -
    name: Runs and renders
    points: 1
    description: Program runs without crashing and renders multiple frames.
  -
    name: Commented
    points: 1
    description: Each function in your code is commented in the required style.
  - 
    name: Affine Transformation
    points: 1
    description: Affine transformations used in the vertex shader
  - 
    name: Logo
    points: 2
    description: Logo model looks substantially like the provided image	and is a set of triangles.
  - 
    name: Change coordinates in buffer
    points: 2
    description: Non-uniform transformation implemented by changing coordinates in buffer	
  -
    name: Second animation
    points: 2
    description: Implement your own animation, different than the logo
  -
    name: Creativity
    points: 1
    description: Is your animation significantly different than the logo and visually interesting
---

![University of Illnois Logo](/img/logo.png)

For your first Machine Problem, you will create **two** animations: 

+ a 2-D animation of the majestic and inspiring University of Illinois logo (as shown above)
+ you will also create a short 2-D animation of your choice…more details below

To complete the MP, you will need to create a digital model of the logo, write code to render it, and write code to animate it.

## Modeling
You will need to model the logo with a 2-D mesh of triangles. One approach to creating the mesh would be to get some graph paper, draw the logo and figure out a set of coordinates for the vertices and a set of edges for the triangles that works. You do not need to make the blue line around orange I curve as in the logo…just create a straight-line block I model. Once you have the coordinates and triangles, just write up a set of JavaScript arrays in your code containing those numbers.

## Rendering
You should color the logo orange and blue as shown above. For this MP, you can render using the gl.drawArrays call, with the primitives specified as gl.TRIANGLES. Note that this will draw a triangle for each group of three consecutive vertices. For example, 12 vertices create 4 separate triangles. This means that the coordinates of vertices shared by multiple triangles will be repeated in the buffer. If you wish, you can use a different implementation like fans or strips or an indexed mesh...it just has to work. But the one suggested here is probably the simplest.

## Animation
You will need to write code to change the location of vertices over time to animate your model. Your code should use two different methods for changing the vertices:

Use 2 or 3 affine transformations (such as scaling, rotation, or translation). Use the glMatrix library to implement these as matrix transformations. These transformations should be applied to the vertices in the Vertex Shader.

Implement another motion by directly changng the vertex positions in the vertex buffer. Have this motion be something non-uniform that cannot easily be implemented as an affine transformation. For example, make the logo dance like a vertical sine curve. This part of the animation could be data driven using a table of pre-defined vertex positions for the motion. The motion can also be keyframed, so the vertices are interpolated from one keyframe location to a second keyframe location. Linear interpolation is fine for this assignment. When modifying the vertex positions by changing the coordinates in the buffer, make sure you use gl.DYNAMIC_DRAW.

## Your Own Animation
Implement a second animation of your own design. It should still be simple, but it should be more than just a slightly different shape doing a similar dance. Some possibilities:

+ It could have two different logos collide...with actual collision detecion and response.
+ It could be a mosaic in which the vertex positions don’t change but the colors of the pieces do.
+ It could be a stick figure jumping or walking.

It doesn’t have to be complex, but it should be your own. Do something creative. You should use an HTML radio button on the webpage to switch between the logo animation and your animation.
