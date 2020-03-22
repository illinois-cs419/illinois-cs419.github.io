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

2. What image format should I output?
You can write out your image to any common image file format. You can use the PPM format from the book, although not many programms read that format (PhotoShop does but most Microsoft viewers don't). You can find tools online to view and convert PPM files. You could use any other format you wish....PNG, or JPEG, etc. **You can use a library (e.g. libpng) to output the image if you wish)**. As a final alternative, you could write the ray tacer in JavaScript and render in a browser rather than outputting a file. See details on this option below.

3. What should the resolution of the image be?
Use at least 500x500. You can make it begger if you wish or use a different aspect ration (e.g. 4:3).

4. Can I use a math library for vector types and functions (e.g. cross product)?
Yes! For example, if you chose to use JavaScript you could use the glmatrix library.

5. Do I need to implement all the features in both books?
No! Just implement the ones in the rubric...unless you want to implement...you could even read and implement the third book from Shirley's website.

6. How many spheres?
Your scene should include over 20 spheres...that's really a modest number so feel free to do more.

7. Can I do something different like using the GPU to parallel ray trace and/or implementing ray marching within WebGL?
Yes, although I won't be able to help with those as much (I haven't implemented them myself), but if you have the skills and ambition you should take up whatever challenge you wish. E-mail me first though, and let em exactly what you wish to do.

8. Can I render something other than spheres?
Yes! See the section on creativity below.

## Implementation Suggestion ##

If you want to write in JavaScript, you can. Instead of using WebGL, you will write pixel values directly onto an HTML5 Canvas using the [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API). In particular the section on [pixel manipulation](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Pixel_manipulation_with_canvas) will be helpful. Rendering will slow, but that's alright provided it's not too slow for you to comfortable work with it and debug.

## Debugging ##

The Shirley books include a lot of good advice on debugging, but I'll mention the most important one here. **Debug using small image sizes like 1x1 and 2x2 images to begin with**.

## A Word About Creativity ##

For the point for creativity, in addition to your scene not being the same as someone else's scene, you should implement some other feature. Texturing (like the procedural checkerboard in the book) is one option...or image texturing or area lights or rendering meshes. Do something that looks good.

## Submission ###

Please submit a **zipped** folder containing:
+ A README.md file explaining how to build and run your code and what format you used to write out the image.
+ All your code
+ An image file showing your rendered scene







