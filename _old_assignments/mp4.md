---
layout: assignment
title: "MP4: A Simple Physics Engine"
index: 10
due: "Dec 9, 2020 @ 11:59 PM"
material: ~
points: 10
rubric:
  -
    name: Forces
    points: 2
    description: Implement at least gravity and drag
  - 
    name: Collision Detection
    points: 2
    description: Implement sphere-wall collision detection and resolve the collison in a physical realistic manner.
  -
    name: Spheres
    points: 2
    description: Generate spheres of different sizes and colors.
  - 
    name: Euler integration
    points: 2
    description: Implement a physics engine the uses Euler integration to update velocity and position.
  - 
    name: Commented code 
    points: 1
    description: Each function in your code is commented in the required style.
  - 
    name: User interface
    points: 1
    description: Have an interface which allows users to generate more spheres, maybe with a button press. Also allow users to remove all the spheres with a button press.
---

![spheres](/img/mp4.png){:height="500px" width="500px"}   

Write a simple particle system using WebGL to handle the display. 
Particle systems are typically used to model fine-grained physical effects like fire, smoke, and water.
We will do something simpler and just render a system of bouncing spheres in 3D.
The specifics of how you implement the following features are up to you...write an app that you think is fun...

Your program will render a set of spheres bouncing around an invisible (or visible if you wish...) 3D box.
You could use a box with corners (-1,-1,-1) to (1,1,1) for example.
When a sphere hits one of the walls in the box, it should reflect in physically realistic manner.  

## Particles ##
You should keep an array or list of particles.

Each particle will be have a postion $$\mathbf{P}$$ and velocity $$\mathbf{V}$$...both of these quantities will be three-dimensional. Each particle will be represented by a sphere. You should have each sphere have an individual color and radius. It is acceptable for some speheres to appear identical, but your code should generate a variety of different-looking spheres. Use the Phong or Blinn-Phong reflection model and Phong shading (i.e. per-fragment shading)...have the spheres look nice.
 
You only need to generate one sphere mesh...you simply draw that mesh in multiple different spots each frame...once for each particle.
You can use some of the code on the course website that can generate and render a sphere.

## User Interface ##

Your user interface should allow you to create spheres using a mouse click or key press. Each creation event should create $$n$$ spheres, where $$n$$ is some number of your choosing.

The spheres should be genereated with a semi-random position and velocity. It doesn't have to be truly random, but there should be some variety.

You will need to bound those values to be reasonable (e.g. position inside the box).
You will also need a reset button that will remove all existing spheres from the scene.
 
## Physics ###

After rendering a frame showing the current position of the spheres, you will need to update the position and velocity of each sphere:

+ Update the position using the current velocity and Euler integration
+ Update the velocity using the acceleration and Euler integration and drag.
+ Update the acceleration using the forces of gravity.

Implement 2 forces that affect the spheres: gravity and friction. If you want to violate physics for fun and have the spheres gain velocity after hitting walls, you can implement a mode to do that as well.

## Collision Detection ##

For this MP you only need to check for sphere collision with a wall, if you use an axis aligned box this is pretty simple:
1. Compute the line segment along which the center of the sphere will move during one frame. If $$c_0$$ is the original position and $$c_1$$ is the final position then the sphere center will travel along $$c(t) = (1-t)c_0 + tc_1$$
2. Let the sphere have a radius $$r$$...if the wall you check against is the $$X=1$$ plane then you just need to check if $$c(1)_x + r >= 1$$..if it is then there was a collision.
3. If there was a collison, calculate a reflection vector. In our example, you can solve for the $$t__{collide}$$ at which the sphere hits the wall. The incident vector is then $$$$ and the normal is $$N=(-1,0,0)$$ in this case. The reflection vector is then $$$$. This becomes the new direction for the sphere and the speed of the sphere will be. 

To be principled, you should divide the timestep $$t_{total}$$ for the sphere into $$t_b$$ before the collsion and $$t_a$$ such that $$t_{total}= t_a + t_b$$ and compute the new sphere position using a timestep of $$t_b$$ from the point of collision in the direction of the new velocity. However, you could just set the sphere postion to the point of collison and update the velocity to the new velocity and then let the sphere move in that direction in the next timestep. For this app, the difference will probably not be noticeable.       

## Commenting ##

You should comment each file with an author comment and comment each function you write with a header. Use JSDoc comments with the appropriate tags and types. Details can be found in the [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html).



