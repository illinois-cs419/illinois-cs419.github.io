---
layout: assignment
title: "Bare Bones Ray Tracing"
index: 10
due: "Feb. 16, 2021 @ 11:59 PM"
material: ~
points: 10
rubric:
  -
    name: Runs and renders
    points: 1
    description: Program runs without crashing and renders multiple frames.
  -
    name: Commented code
    points: 1
    description: 
  - 
    name: Ray-Plane Intersection
    points: 1
    description: Be able to render a plane.
  - 
    name: Ray-Sphere Intersection
    points: 2
    description: Be able to render a sphere
  -
    name: Ray-Triangle Intersection
    points: 1
    description: Be able to render a triangle
  - 
    name: Movable Camera
    points: 2
    description: Be able to generate a render from an arbitrary viewpoint and direction	
  -
    name: Orthographic and Perspective Projection
    points: 2
    description: Be able to render using either type of projection
  -
    name: Multi-Jittered Sampling
    points: 1
    description: Be able to render an image using multi-jittered sampling for anti-aliasing
  -
    name: Simple Diffuse Shading
    points: 1
    description: Use the diffue shading term from the Phong reflection model 
---

For your first programming assignment you will implement a bare bones ray-tracer with the following capabilities:

1. Ray-object intersection support for:
   1. Planes
   2. Spheres
   3. Triangles
 
2. Orthographic projection
 
3. Perspective projection with a movable camera
 
4. Multi-jittered sampling for the primary rays
 
5. Simple shading using the Blinn-Phong or Phong reflectance model. Just do diffuse (Lambertain) shading without any specular component. Use a directional light with no position

6. Output images in one of PPM or PNG format.

### Hand-in

You will hand in your code and 5 images:

+ One orthographic rendering of a scene with spheres and triangles

+ One perspective rendering of the same scene

+ An additional perspective rendering of the same scene from a different viewpoint

+ Two images illustrating the effects of using jittering. The first image should use a single ray for each pixel, while the second should use multi-jittering. Try to set up a scene so that the difference is apparent.

The images should be at least 500 x 500 pixels. 

Hand-in will be done on Compass 


### Technical Details

+ You can use any programming /platform you wish

+ You can use any math library/package you wish to support the vector/matrix operations you need to perform

+ The documentation standard is simple each function or scoped block of code should have a comment describing the following:
+++ The purpose of the function
+++ The inputs to the function
+++ The return value(s) if any

+ **If you use code from other sources, you must document the use of that code**
