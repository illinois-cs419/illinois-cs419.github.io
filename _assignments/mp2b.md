---
layout: assignment
title: "MP2: Terrain Modeling Part 2"
index: 10
due: "Oct. 21, 2019 @ 11:59 PM"
material: ~
points: 9
rubric:
  -
    name: Documentation
    points: 1
    description: Documented user interface on the webpage.
  -
    name: Forward motion
    points: 1
    description: The position of the viewer moves forward in accordance with the magnitude of the current velocity.
  - 
    name: Roll
    points: 1
    description: The view orientation can be rotated around the forward direction.
  -
    name: Pitch
    points: 1
    description: The view orientation can be rotated around the horizontal axis that is perpendicular to the view direction.
  - 
    name: Change speed
    points: 1
    description: The user can increase or decrease the speed of forward movement.
  - 
    name: Fog
    points: 1
    description: A fog effect, implemented in the shader, can be turned on or off using a control on the webpage.
---


![terrain](/img/terrain.PNG)  

To complete the second Machine Problem, you will implement a simple flight simulator. Your "plane" will fly over the terrain you generate.  You will also add the capability of applying fog to your terrain.

The airplane should automatically move forward at a fixed speed. The user will control the bank and tilt of the airplane through the arrow keys.

+ Pressing the left (right) arrow key will make the plane roll to its left (right).
+ Pressing the up (down) arrow key will cause the airplane to pitch up (down).
+ Pressing the + (-) key will increase (decrease) the airplane's speed

You will need to implement the following: 

#### A quaternion based viewing system ####
The glMatrix library provides support for using [quaternions](http://glmatrix.net/docs/module-quat.html). We would suggest using that library instead of creating your own quaternion class. **Note** if you are using the example code from this course, that code uses an older version of the glMatrix library. The library downloaded from the course website may not include all of the functions documented in the current API. It is suggested that you donwload the current glMatrix library from the web and work with that version.

#### A working and documented user interface #### 
You should implement a user interface that minimally implements the arrow-key and +/- key controls described above. You can add additional controls to affect yaw if you wish.
Your webpage should include text instructions describing how the user interface works...you can simply include text in the HTML file that will be displyed on the webpage, that explains how to control the view and speed. 

#### A cloud of fog, placed over and around your terrain ####
The fog computation should be done per-pixel, which means implemented in the fragment shader. Implement a control on the webpage (e.g. a checkbox) which allows the user to turn the fog on and off in the scene. More details about how to simulate fog will be provided in lecture.
