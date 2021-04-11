---
layout: assignment
title: "Final Project"
index: 20
due: "May 14, 2021 @ 11:59 PM"
material: ~
points: 50
rubric:
-
    name: Required Features
    points: 40
    description: Implement features with weight equal to the number of people on the team
-
    name: Report
    points: 10
    description: Submit report website or PDF describing the project
---

# Final Projects

![scene](https://illinois-cs419.github.io/img/scene.jpg){:width="900px"}

For your final project, you will choose a set of features to implement and demonstrate those features by producing rendered scenes in which they are apparent. Typically these new features can just be added to your existing ray-tracing code but you can create standalone demonstrations as well. For example, it may be easier to implement a simple fluid simulation outside of your existing code-base.

We have provided references that explain how these features can be implemented, but you can use other resources you discover on your own as well or instead our suggested sources.  

The suggested projects below have weights associated with them. **The total point value of all the weights of the features you choose to implement should equal the number of people on your team.**  

## Deliverables

Each team will submit a report as a PDF document that uses the [IEEE Visualization journal format](https://tc.computer.org/vgtc/publications/journal/).

**Alternatively** you can create a webpage that follows the same format as the PDF would have. If you create an animation, this is a better option since you can embed a link to YouTube or similar site. [GitHub Pages](https://pages.github.com/) is a free and easy to use option for creating and hosting the webpage. 


Each team member should have their **name** and **netid** listed at the top of the report.

The report can be from 1 to 5 pages and should include the following sections:

1.  Abstract...3 or so sentences stating which features you implemented
2. Resources...briefly describe which references/resources you used for each feature you implemented (e.g. Shirley's books, etc.) 
3. Implementation...1 paragraph describing the hardware and OS of the system used to render your images and the programming language used to implement the renderer
4. One section for each feature implemented. At least one paragraph should describe how the feature was implemented and should refer the reader to an image and describe how the feature is shown in the image. You should also refer to Performance Results Table and describe how performant (or not) the renderer is for that feature. 
   1. At least 1 image for each feature implemented, demonstrating that feature.
   2. A table listing the render time and number of rays per pixel used to generate each image.
5. Conclusion...short paragraph stating anything interesting you learned or how you would  extend the code if you had time. 
   **Include a link to a repo containing the project code.**

## Topics

1. **Photon Mapping**
This a a technique that has been used to produce high quality renderings of scenes that involve (1) caustics, (2) participating media and (3) transmission. If you choose to implement this, your scene should demonstrate at least one of those 3 features. You get an additional weight point for each additional feature you demonstrate.<br/>
**_References:_**<br/>
[A Practical Guide to Global Illumination using Photon Maps](http://171.67.77.70/courses/cs348b-01/course8.pdf)<br/>
**_Weight:_ 2 to 5**<br/>
 
2. **Volumetric Rendering**
Participating media can also be rendered using more traditional volumetric techniques. Again each type of volumetric object implemented beyond the first is worth an additional point.<br/>
**_References:_**<br/>
[Production Volume Rendering SIGGRAPH 2017 Course Notes](https://graphics.pixar.com/library/ProductionVolumeRendering/paper.pdf)<br/>
_Production Volume Rendering_ by  Magnus Wrenninge [UIUC library link to book](https://i-share-uiu.primo.exlibrisgroup.com/discovery/fulldisplay?docid=alma99954765801405899&context=L&vid=01CARLI_UIU:CARLI_UIU&tab=LibraryCatalog&lang=en)<br/>
**_Weight:_ 2 to 5**<br/>

3. **Glossy Specular Reflection**
Implement the BRDF from _Ray Tracing from the Ground Up_ that allows you to render shiny objects that have some scattering.<br/>
**_References:_**<br/>
[Ray Tracing from the Ground Up: Chapter 25](https://i-share-uiu.primo.exlibrisgroup.com/discovery/fulldisplay?docid=alma99947038912205899&context=L&vid=01CARLI_UIU:CARLI_UIU&tab=LibraryCatalog&lang=en)<br/> 
**_Weight:_ 2**<br/>

4. **Fluid Modeling**
There are a number of ways to model fluids (meshes versus particles, etc.). You will need to choose one and then implement some simulation of fluid behavior, and you will need to animate (render multiple frames). You may find it easier to implement this in WebGL depending on the approach you take.<br/> 
**_References:_**<br/>
[Fluid Simulation for Animation](https://www.cs.ubc.ca/~rbridson/fluidsimulation/)<br/> 
_Fluid Simulation for Computer Graphics_ by Robert Bridson [UIUC Library link to book](https://i-share-uiu.primo.exlibrisgroup.com/discovery/fulldisplay?docid=alma99954765903705899&context=L&vid=01CARLI_UIU:CARLI_UIU&tab=LibraryCatalog&lang=en_)<br/>
**_Weight:_ 3**<br/>

5. **Ambient Occlusion**
Simple and non-physical but effective technique for adding indirect shading and soft shadow-like features<br/>
**_References:_**<br/>
[Ray Tracing from the Ground Up: Chapter 17](https://i-share-uiu.primo.exlibrisgroup.com/discovery/fulldisplay?docid=alma99947038912205899&context=L&vid=01CARLI_UIU:CARLI_UIU&tab=LibraryCatalog&lang=en) *by Kevin Suffern*<br/>
**_Weight:_ 1**<br/>
   
6. **Animation**
Render multiple frames that you make into a movie using Adobe Premiere or DaVinci Resolve or something similar. You will need to implement some sort of kinematics system so that the objects move from frame to frame...the number of points for this project can be increased if you implement a more complicated physics and/or collision detection system.<br/>
**_References:_**<br/>
_Computer Animation_ by Rick Parent [UIUC Library link to book](https://i-share-uiu.primo.exlibrisgroup.com/discovery/fulldisplay?docid=alma99953422012205899&context=L&vid=01CARLI_UIU:CARLI_UIU&tab=LibraryCatalog&lang=en)<br/>
_Game Physics_ by Ian Millington [UIUC Library link to book](https://i-share-uiu.primo.exlibrisgroup.com/permalink/01CARLI_UIU/gpjosq/alma99661882112205899)<br/>
_Real-Time Collision Detection_ by Christer Ericson [UIUC Library link to book](https://i-share-uiu.primo.exlibrisgroup.com/permalink/01CARLI_UIU/gpjosq/alma99704757712205899)
<br/>
**_Weight:_ 2**<br/>

7. **Image-based Texture Mapping**
Add support for texture mapping images onto a surface in your ray-tracer. 
**_References:_**<br/>
[Ray Tracing from the Ground Up: Chapter 29](https://i-share-uiu.primo.exlibrisgroup.com/discovery/fulldisplay?docid=alma99947038912205899&context=L&vid=01CARLI_UIU:CARLI_UIU&tab=LibraryCatalog&lang=en)<br/>
**_Weight:_ 1**<br/>

8. **Procedural Texture Mapping**
Add support for procedural texture mapping of surfaces and/or solids.<br/>
**_References:_**<br/>
[Ray Tracing from the Ground Up: Chapter 30](https://i-share-uiu.primo.exlibrisgroup.com/discovery/fulldisplay?docid=alma99947038912205899&context=L&vid=01CARLI_UIU:CARLI_UIU&tab=LibraryCatalog&lang=en) *by Kevin Suffern*<br/>
**_Weight:_ 1**<br/>

9. **Constructive Solid Geometry**
Add support for modeling objects using CSG...creating interesting surfaces using solids and boolean operations. At a minimum you should support spheres and boxes and the operators union, intersection, and difference.<br/>
**_References:_**<br/>
[Wikipedia CSG Article](https://en.wikipedia.org/wiki/Constructive_solid_geometry)<br/>
**_Weight:_ 2**<br/>

10. **Bezier Surfaces**
A Bezier surface is composed of joined polynomial patches...the Utah teapot was originally modeled using Bezier patches. Add support for a simple Bezier patch model representation of a surface. This one is easier than it may sound...you can convert the Bezier representation to triangles for intersection testing and use the patch polynomials to generate the normal at a hit point.<br/>
**_References:_**<br/>
[Scratchapixel Bezier Article](https://www.scratchapixel.com/lessons/advanced-rendering/bezier-curve-rendering-utah-teapot/bezier-surface)<br/>
_The Essentials of CAGD_ by Farin and Hansford [UIUC Library link to book](https://i-share-uiu.primo.exlibrisgroup.com/permalink/01CARLI_UIU/gpjosq/alma99888760512205899)
<br/>
**_Weight:_ 2**<br/>

11. **Advanced Material Modeling**
You can model a different material by creating an appropriate BRDF for it, liked brushed metal for example.<br/>
**_References:_**<br/>
_Digital Modeling of Material Apearance_ by Julie Dorsey [UIUC Library link to book](https://www-sciencedirect-com.proxy2.library.illinois.edu/book/9780122211812/digital-modeling-of-material-appearance)<br/>
_Real-Time Rendering_ Chapter 9 Physically Based Shading [Website](http://www.realtimerendering.com/#brdf)<br/>
**_Weight:_  1 for each BRDF implemented** <br/>
    
12. **Motion Blur**
Add support for motion blur. Motion blur for a physical camera happens because the "shutter" is open for a certain amount of time. Therefore, what you are rendering is actually the average of what the camera sees while the shutter is open. That means if an object is moving, we want to sample it at random positions along its trajectory during that time.
<br/>
**References:**<br/>
[Ray Tracing The Next Week: Chapter 2 ](https://raytracing.github.io/books/RayTracingTheNextWeek.html#motionblur)<br/>
**Weight: 1**<br/> 

## Alternative Projects

If you wish to propose an alternative project (e.g. implement a simple ray-tracer in CUDA), you can. Just contact the instructor on CampusWire and ask if your idea is appropriate.

CUDA Ray Tracer resource [NVIDIA Blog Post](https://developer.nvidia.com/blog/accelerated-ray-tracing-cuda/)

## 4 Credit Students 

If you are taking the course for 4 credits, you should implement an additional feature of weight $$1$$. If you would prefer to implemeent a feature not on the list or would prefer to read and present a research paper instead, just contact the course staff and we can finalize those details.


