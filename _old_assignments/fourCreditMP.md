---
layout: assignment
title: "4 Credit MP: Ray Tracing"
index: 10
due: "May 6, 2020 @ 11:59 PM"
material: ~
points: 10
rubric:
  -
    name: Positionable camera
    points: 1
    description: Implement a camera you can position in the scene...choose an interesting view in for your scene
  - 
    name: Spheres
    points: 1
    description: Be able to render spheres of different sizes
  -
    name: Diffuse material
    points: 1
    description: Some spheres should be rendered as diffuse surafces
  - 
    name: Metal material
    points: 1
    description: Some spheres should be rendered as metallic surfaces (mirrors are nice)
  - 
    name: Dielectrics
    points: 1
    description: Some spheres should be glass....
  - 
    name: Instances
    points: 1
    description: Render a non-trivial number of spheres by using instancing
  -
    name: Bounding Volume Hierarchy
    points: 1
    description: You should implement a BVH to make your tracer more performant
  - 
    name: Plane
    points: 1
    description: Render a geometric plane as a floor for your scene
  - 
    name: Shadows
    points: 1
    description: Support shadows...can be hard shadows using a point light
  - 
    name: Creativity
    points: 1
    description: Do something interesting and visually unique in your scene...maybe texturing
    
---

![Tracing](/img/ray-tracing.png){:height="500px" width="500px"}   

For your 4-credit project you will write a simple ray-tracer and render a scene. To prepare to write the ray-tracer, you should read the following the very short books from [Peter Shirley's books on ray tracing](https://raytracing.github.io/):

+ [Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html)
+ [Ray Tracing the Next Week](https://raytracing.github.io/books/RayTracingTheNextWeek.html)

Your ray tracer will not be interactive...it need not render the scene in real-time. In fact, it is expected that it may take up to several minutes for your scene to render depending on your choice of programming language. The output of the program should be an image written to a file.

## Implementing the Ray Tracer  ##

The ultimate goal is to be able to render a scene including the components shown in the image on this page. **However, your scene should be unique...use your creativity and make it look different from the one presented here**. The functional elements your ray tracer needs to support are included in the rubric. Information about each of these is easily found in the books linked above.

Your program should write out an image file containing the scene you rendered

Here are some answers to questions I imagine you have:

1. What programming language should I use?

  You can use any language you wish. You may consult the C++ code the Shirley provides, but write the code yourself. Your code should be demonstrably different than his. To achieve this, it may be easier to write in another language...maybe one you want to learn. The scene will be pretty minimal, so even languages not known as performant (e.g. Python or JavaScript) can be a good choice.

2. What image format and should I output?

You can write out your image to any common image file format. You can use the PPM format from the book, although not many programms read that format (PhotoShop does but most Microsoft viewers don't). You can find tools online to view and convert PPM files. You could use any other format you wish....PNG, or JPEG, etc. **You can use a library (e.g. libpng) to output the image if you wish)**. As a final alternative, you could write the ray tacer in JavaScript and render in a browser rather than outputting a file. See details on this option below.

3. Can I use a math library for the vector operations


## Implementation Suggestion ##

## A Word About Creativity ##


## User Interface ##


## Submission ###

After rendering a frame showing the current position of the spheres, you will need to update the position and velocity of each sphere:

+ Update the position using the current velocity and Euler integration
+ Update the velocity using the acceleration and Euler integration and drag.
+ Update the acceleration using the forces of gravity.

Implement 2 forces that affect the spheres: gravity and friction. If you want to violate physics for fun and have the spheres gain velocity after hitting walls, you can implement a mode to do that as well.





