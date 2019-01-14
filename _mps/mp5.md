---
title: MP5
permalink: "/mp5/"
layout: page
---

### <span style="color:blue"> Path Tracing and Irradiance Caching  </span>
**Due: December 12, 11:55pm**
**For 4 Credit Students Only**

![Cornell Box](/assets/img/box.jpg){:height="200px" width="200px"}

For your 4 credit programming assignment you will:

1. **Create a scene matching the Cornell Box.** You can find data for the geometry [here](http://www.graphics.cornell.edu/online/box/data.html). You needn't match the surface reflectances exactly, but your model should look **very** close to the image above. The surfaces can all be diffuse materials, with just the one overhead area light.  

2. **Implement a path tracer.** See _Ray Tracing from the Ground Up_ Chapter 26 Global Illumination. To speed up convergence, you can compute direct lighting and indirect lighting separately, as the book does. You might also want to try _Russian Roulette_ but that is not required. 
 
3. **Implement irradiance caching.** See [_Practical Global Illumination with Irradiance Caching_ by Krivaenk and Gautron](https://vufind.carli.illinois.edu/vf-uiu/Record/uiu_6588105). You only need to implement the basic algorithm, although if you have time you might wish wish to implement irradiance gradients. I would strongly suggest implementing a two-pass algorithm. Your render will likely not be perfect and that is fine. It should be good. You will likely need to experiment with parameters (the error term and weights), so give yourself time to work on this and use small image sizes for experiments and larger for your final render.
         
### Hand-in

**You will hand in your code and 3 sets of images:**

+ One set of three images of the Cornell Box showing progressively more sample paths per pixel. The book uses 100, 1000, and 10,000 but you may need to use more or less.
Your final image should be fully converged (or almost fully converged).
+ One image, fully converged or close, of the Cornell Box using path tracing and irradiance sampling. Your image does not have to be artifact free, but it should be a reasonable attempt. 
+ The same irradiance scene as above, but the render the location of the irradiance samples as red dots. You should be able to loop over the sample locations, compute a ray from the eye to a sample and then figure out which pixel that ray crosses and color that pixel red.

**You also need to write a brief technical report**

Write a report that:
+ provides the technical specifications of the hardware you ran on
+ states which language(s) your implementaion is written in
+ provides a table that shows the **time** and **number of rays** required to render each of your 3 path-traced images
+ provides a statement of time required to render the scence with irradiance caching. Measure the time to generate the irradiance samples and the time render separately as well. This is easy if you employ two-pass rendering.
+ include a paragraph or two describing how you implemented path tracing.
+ include a paragraph or describing your implementation of irradiance caching.
**Include a README.txt file in which you list all pieces of code you did not write.**  
This includes any libraries, source code downloaded, or source code you typed in or adapted from a listing you read. Please use something like the following format _1. Name-Of-Piece-Of-Code URL-to-Source_ 

Hand-in will be done on Compass.


### Rubric

|:----------------+------------|
| **Feature**           | **Points** |
|:--------------------------|-------:|
| Model the Box      | 5      |
| Path Tracer  | 5      |
| Irradiance Caching | 5      |
| Technical Report    | 5      |
| **TOTAL**	                 |20        |
|===
| 
