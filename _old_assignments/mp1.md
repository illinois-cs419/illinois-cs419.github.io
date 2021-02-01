---
layout: assignment
title: "Bare Bones Ray Tracing"
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
    name: COmmented and well-engineered code
    points: 1
    description: Each function in your code is commented
  - 
    name: Ray-Plane Intersection
    points: 1
    description: 
  - 
    name: Ray-Sphere Intersection
    points: 2
    description: Logo model looks substantially like the provided image	and is a set of triangles.
  -
    name: Ray-Triangle Intersection
    points: 1
    description: Is your animation significantly different than the logo and visually interesting
  - 
    name: Movable Camera
    points: 2
    description: Non-uniform transformation implemented by changing coordinates in buffer	
  -
    name: Orthographic and Perspective Projection
    points: 2
    description: Implement your own animation, different than the logo
  -
    name: Multi-Jittered Sampling
    points: 1
    description: Is your animation significantly different than the logo and visually interesting
  -
    name: Simple Diffuse Shading
    points: 1
    description: Is your animation significantly different than the logo and visually interesting
---

---
title: MP1
permalink: "/mp1/"
layout: page
---

### <span style="color:blue"> Bare Bones Ray Tracing </span>
**Due: September 20, 11:55pm**

For your first programming assignment you will implement a bare bones ray-tracer with the following capabilities:

1. Ray-object intersection support for:
   1. Planes
   2. Spheres
   3. Triangles
 
2. Orthographic projection
 
3. Perspective projection with a movable camera
 
4. Multi-jittered sampling for the primary rays
 
5. Simple shading using the Blinn-Phong or Phong reflectance model. Just do diffuse (Lambertain) shading without any specular component. Use a directional light with no position

### Hand-in

You will hand in your code and 5 images:

+ One orthographic rendering of a scene with spheres and triangles

+ One perspective rendering of the same scene

+ An additional perspective rendering of the same scene from a different viewpoint

+ Two images illustrating the effects of using jittering. The first image should use a single ray for each pixel, while the second should use multi-jittering. Try to set up a scene so that the difference is apparent. 

Hand-in will be done on Compass and detailed instructions will be forthcoming 



### Technical Details

+ You can use any programming /platform you wish

+ You can use any math library/package you wish to support the vector/matrix operations you need to perform

+ If you wish to use the framework code from Ray-Tracing from the Ground Up, you may.

**Keep in mind that if you use code from other sources, you must document the use of that code**
