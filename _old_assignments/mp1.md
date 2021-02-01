---
layout: assignment
title: "Bare Bones Ray Tracing"
index: 10
due: "Feb. 18, 2021 @ 11:59 PM"
material: ~
points: 50
rubric:  
  -
    name: Commented code
    points: 5
    description: 
  - 
    name: Ray-Plane Intersection
    points: 5
    description: Be able to render a plane.
  - 
    name: Ray-Sphere Intersection
    points: 5
    description: Be able to render a sphere
  -
    name: Ray-Triangle Intersection
    points: 5
    description: Be able to render a triangle
  - 
    name: Movable Camera
    points: 5
    description: Be able to generate a render from an arbitrary viewpoint and direction	
  -
    name: Orthographic and Perspective Projection
    points: 5
    description: Be able to render using either type of projection
  -
    name: Multi-Jittered Sampling
    points: 10
    description: Be able to render an image using multi-jittered sampling for anti-aliasing
  -
    name: Simple Diffuse Shading
    points: 5
    description: Use the diffuse shading term from the Phong reflection model 
-
    name: Hard Shadows
    points: 5
    description: Be able to produce hard-edged sahodws as shown in the image on this page.
    
---

![Tracing](/img/MP1.jpg){:width="500px"}   
For your first programming assignment you will implement a bare bones ray-tracer with the following capabilities:

1. Ray-object intersection support for:
   1. Planes <br/> Reference: [Basic Ray Tracing Jan 28.](https://illinois-cs419.github.io/schedule)

   2. Spheres <br/> Reference: [Ray-Sphere Intesection Feb.2](https://illinois-cs419.github.io/schedule) <br/>  [Reference: RTiOW Section 5](https://raytracing.github.io/books/RayTracingInOneWeekend.html#addingasphere)
   
   3. Triangles <br/> [Reference: Ray-Triangle Intersection Feb. 9](https://illinois-cs419.github.io/schedule)
 
2. Orthographic projection and perspective projection <br/> [Reference: Basic Ray Tracing Jan. 28](https://illinois-cs419.github.io/schedule)
 
3. A movable camera <br/> [Reference: Cameras Feb. 9](https://illinois-cs419.github.io/schedule)
 
4. Multi-jittered sampling for the primary rays <br/> [Reference: Sampling Feb. 4](https://illinois-cs419.github.io/schedule) 
 
5. Simple shading using the Blinn-Phong or Phong reflectance model. <br/>
Just do diffuse (Lambertain) shading without any specular component. <br/>
Use a point light and do not recurse...just shade the hit using a surface normal and the direction to the light. <br/>
[Reference: Diffuse Shaddng Feb. 9](https://illinois-cs419.github.io/schedule)

6. Hard shadows <br/> [Reference: Hard Shadows Feb. 11](https://illinois-cs419.github.io/schedule)   

6. Output images in one of PPM or PNG format. <br/> [Reference: RTiOW Section 2](https://raytracing.github.io/books/RayTracingInOneWeekend.html#outputanimage)

### Technical Details

+ You can use any programming /platform you wish

+ You can use any math library/package you wish to support the vector/matrix operations you need to perform

+ The documentation standard is simple each function or scoped block of code should have a comment describing the following:
  +The purpose of the function
  + The inputs to the function
  + The return value(s) if any

+ **If you use code from other sources, you must document the use of that code in a text file named README.md in your handin**

### FAQ
Q. Should my images look like the one on this page?<br/>
A. Not exactly! You can ignore the cylinder and the box...you won't render those.<br/>
   And you can be a little creative and any scene you want as long as it denomstrates the elements shown here.<br/> 
   Also, you should be aware the scene on this page is in perspective, which is why there is a horizon from the plane. 
   
Q. Can use code X that I found on the web?<br/>
A. Probably! In general, code to do basic numerical work (e.g. cross-product or even barycentric coordinates for a point) can be from a library.
   You can ask on CampusWire about specific pieces of code. <br/>
   Whether your use a library or copy source code from some approved source, you must cite the source in a text file named README.md in your handin.

Q. In what order should I implement these features?<br/>
A.  I would implement things in the following order 
    1. Image output, orthographic and persepctive projection, ray-plane intresection (with flat shading)
    2. Spheres, diffuse shading, movable camera
    3. Triangles, multi-jittered sampling, shadows
    Test as you go...save your test cases for re-use if possible.

### Hand-in

You will hand in your code and 5 images:

+ One orthographic rendering of a scene with sphere, a plane, and triangles at a resolution of at least 500x500. 

+ One perspective rendering of the same scene at a resolution of at least 500x500. 

+ An additional perspective rendering of the same scene from a different viewpoint at a resolution of at least 500x500. 

+ Two images illustrating the effects of using jittering. <br/>
  The first image should use a single ray for each pixel, while the second should use multi-jittering. 
  Try to set up a scene so that the difference is apparent, you can reduce the resolution to something small. 

Hand-in will be done on Compass 


