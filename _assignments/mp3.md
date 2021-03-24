---
layout: assignment
title: "Whitted Ray Tracing and Beyond"
index: 20
due: "April 7, 2021 @ 11:59 PM"
material: ~
points: 50
rubric:
-
    name: Mirror Reflection
    points: 15
    description: Add support for perfect specular relfection on a sphere.
-
    name: Transparency
    points: 15
    description: Add support for transparent spheres
-
    name: Area Lights
    points: 15
    description: Add support for rectangular arae lights.
-
    name: Creativity
    points: 5
    description: Submitted images are scenes of your own design of similar quality to the provided images.
---

### Whitted Ray Tracing and Beyond

![whitted](https://illinois-cs419.github.io/img/whitted.jpg){:width="400px"}  

For your third programming assignment you will extend your ray tracer to include effects pioneered by Turner Whitted in his paper from 1980  [*An improved illumination model for shaded display.*](https://dl.acm.org/doi/10.1145/358876.358882)  You can read his own account of his initial implementation of recursive ray tracing in [this 2018 essay he wrote for NVIDIA](https://blogs.nvidia.com/blog/2018/08/01/ray-tracing-global-illumination-turner-whitted/). It's interesting, short, and worth reading.

The key features you will add to you ray tracer will be refraction (transparency) and mirror reflection. We will also go step beyond what Whitted did and add support for area lights.

### Implementation

You will add the following features. You can consult either or both of the books listed below for details on how to implement these features and example code. Be aware that the two books take slightly different approaches and have different coding styles, although both use `C++`.

1. **Rendering a mirror-like object.**<br/> Render a scene of about the same complexity and quality as the one at the top of this assignment.<br/> 
  _**References:**_
  + See _Ray Tracing in One Weekend_   [**Chapter 9 Metal**](https://raytracing.github.io/books/RayTracingInOneWeekend.html#metal)
  + See _Ray Tracing from the Ground Up_ **Chapter 24 Mirror Reflection**  [UIUC Library Link](https://i-share-uiu.primo.exlibrisgroup.com/permalink/01CARLI_UIU/q1ojeg/alma99947038912205899)<br/><br/>

2. **Rendering a transparent object.**<br/> Render a scene of about the same complexity and quality as the one at the top of this assignment.<br/> 
  _**References:**_<br/> 
  + See _Ray Tracing in One Weekend_   [**Chapter 10 Dielectrics**](https://raytracing.github.io/books/RayTracingInOneWeekend.html#dielectrics)
  + See _Ray Tracing from the Ground Up_ **Chapter 27 Simple Transparency** [UIUC Library Link](https://i-share-uiu.primo.exlibrisgroup.com/permalink/01CARLI_UIU/q1ojeg/alma99947038912205899)<br/><br/>

3. **Support for area lights.** <br/>
   ![whitted](https://illinois-cs419.github.io/img/light.PNG){:width="200px"} <br/>
   Render a scene of about the same complexity and quality as the one shown here.<br/> 
   You can use spheres and/or simple rectangles instead of rectangular solids.<br/>
   _**References:**_<br/> 
   + See _Ray Tracing the Next Weekend_  [**Chapter 7 Rectangles and Lights**](https://raytracing.github.io/books/RayTracingTheNextWeek.html#rectanglesandlights) 
   + See _Ray Tracing from the Ground Up_ **Chapter 18 Area Lights**  [UIUC Library Link](https://i-share-uiu.primo.exlibrisgroup.com/permalink/01CARLI_UIU/q1ojeg/alma99947038912205899)<br/><br/>
         
### Creativity

The scenes don't need to be complex, but they should be different from the ones pictured here. They should have about the same quality. You are free to use code from the sources listed here as a reference for your implementation. It is acceptable for your code to be very similar to those sources.

### Submission

**You will hand in your code and 3 images:**

+ One rendering of a scene with an area light that shows soft shadows.
+ One rendering of a transparent object like a glass sphere....include enough of a scene to show it is transparent.
+ One rendering of a mirror-like object...include enough of a scene to show that it is reflective.

**You also need to write a very brief technical report**

Write a paragraph that:
+ provides the technical specifications of the hardware you ran on
+ states which language(s) your implementation is written in
+ provides a table that shows the **time** and **number of rays** required to render each of your 3 images

**Include a README.txt file in which you list all pieces of code you did not write.**  
This includes any libraries, source code downloaded, or source code you typed in or adapted from a listing you read.  
Please use something like the following format _1. Name-Of-Piece-Of-Code URL-to-Source_ 

Hand-in will be done on Compass.
