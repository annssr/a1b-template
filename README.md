# Assignment 1:  Different Architectures

This is a three part assignment where you will implement a simple VR experience in three different programming environments: Babylon.js, Playcanvas, and A-Frame.

The goal of the assignment is to have you gain experience with three very different architectures, and to reflect on these differences.  [Babylon.js](https://babylonjs.org) is an object-hierarchy architecture, similar to other systems like three.js and numerous non-web graphics libraries.  [Playcanvas](https://playcanvas.com) uses an Entity-Component architecture, similar to Unity, Unreal, and other game engines.  [A-Frame](https://aframe.io) is a mix of the two, and is implement using custom DOM elements so that the scene graph sits in the HTML page.

This repository is for the second of the three parts of the assignment, where you will use Playcanvas.

# Assignment 1(b):  Playcanvas VR Experience 

For this assignment, you will implement a very similar application as assignment 1(a), but this time using Playcanvas. (Each of you should have an account on playcanvas.com by this time.)

To get started with the assignment, create a new *private* project on Playcanvas using the "VR Starter Kit", give it a name that starts with "a1b " and includes your GT user name (e.g., I might name mine "a1b blair@gatech"). You will be sharing this project with the instructor and TAs, and they will need to easily identify which is which from their project names.

## Due: Friday October 2nd, 11:59am (noon)

## Name and GT user-id

Name: 
User ID:
Playcanvas Username: 

## Rubric

Graded out of 5.

Each of the parts to be added can be figured out from the examples and tutorials in the [Playcanvas documentation](https://developer.playcanvas.com/en/).  In particular, you should go through some of the [tutorials]https://developer.playcanvas.com/en/tutorials/) to see how different features work.  If you have experience with Unity, some of the Playcanvas interface and approach will feel familiar.

The assignment and rubric are very similar to A1(a). 

0. Your exported project runs locally using `npm run start`. (1)
2. Add a 2D GUI panel attached to the left controller that has a color panel and two buttons ("cube" and "sphere"). (1)
3. When you click, create a cube or sphere as described below, with the correct color. (2)
4. Pressing the grip button on the controller with the menu erases all the objects created. (1)

Up to 2 additional bonus points will be given for some of the following (1 bonus each). (note: **You cannot do the same bonus part for 1(a) and 1(b)**):
- add a slider to the GUI to control the size of the object created.
- add a second GUI panel, perpendicular to the first (the "second side of a cube") and move the two buttons there.  Add at least 2 more objects that can be created and include buttons for them in the panel.
- allow cubes to be created when you click on a sphere.  The cube needs to be oriented and positioned so the center of one face is just touching the point on the sphere where you clicked.
- suggest something else you'd like to do of similar complexity.

## Overview 

The goal of the assignment is to use Playcanvas to create the same immersive WebXR application you just created in Babylon.js.

You should take the WebXR starter code, remove the cubes from the space, and build the program described in the rubric.  

You should attach a simple GUI to one of the controllers (your choice).  It should be sized so that it's not in the way, and that you can use the other controller to interact with it.  Since Playcanvas does not have something like Babylon's Color Picker, you can pick 9 different colors, and lay them out in a 3x3 grid in the GUI. One of them should be visibly selected at all times.

When you click the trigger on either controller, you should create a sphere or cube (whichever is selected) of about 0.2 meters in size. There are two cases to consider.  If the ray hits something (the ground or another object), the object should be positioned such that it is touching the collision point.  For the sphere, you should position it such that a point on the sphere hits the collision point. For the cube, the center of one of the faces should touch the collision point.

To keep things simple, you do NOT have to create cubes when the object hit with the ray is a sphere.  Keep your cubes axis aligned, and only create them against the ground or other cubes.

The object created should be the current color in the color selection grid in the GUI.

Finally, when the user presses both "grips" at the same time, all the objects you created should be removed, so they can start over.

# Collaboration

You are free to discuss technical questions and issues in the Teams channels, but the code you submit should be your own.  So, please do not post large chunks of code, but providing pointers to examples or documentation pages or components and methods, along with discussion of how to use them, is fine.

# Submission

You will submit your assignment two ways:
- You should add "blair, ryanm14, tedthemeap, nfereydooni" as collaborators on your playcanvas project.
- You should publish your project as a downloadable .zip, and extract all the files into the "dist" directory in this repository, and check it in.  

By sharing the project, the TAs and I can inspect your project if need be.  By downloading the published project, the TAs will be able to more easily run and grade it. 

**Make sure you put your published project in the dist directory and submit it**, without adding any additional files.  The TAs need to be able to test your program as follows:

1. cd into the directory and run ```npm run start```
2. the local web server (via python's web server) will serve up your dist directory as `localhost:8080`, which the TAs can test on their VR devices using the techniques discussed in class.

Please test that your submission meets these requirements, and works when run via the npm script.  For example, after you check in your final version of the assignment to github, check it out again to a new directory and make sure everything runs correctly.
 
# Development Environment

You should do all your work in the editor on playcanvas.com

## Running 

When you are editing a scene in the Playcanvas editor, it will have a URL like `https://playcanvas.com/editor/scene/989742`.  When you run that scene with the "play" button in the editor, it will open another tab with a URL like `https://launch.playcanvas.com/989742?debug=true`.  If you are using a Quest, enter (and bookmark) that URL in the browser, so that you can run your application there (and debug it using the same approach you have used in 1(a)).

## License

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">Material for 3D User Interfaces Fall 2020</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.blairmacintyre.me/3dui-class-f20" property="cc:attributionName" rel="cc:attributionURL">Blair MacIntyre</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.

The intent of choosing (CC BY-NC-SA 4.0) is to allow individuals and instructors at non-profit entities to use this content.  This includes not-for-profit schools (K-12 and post-secondary). For-profit entities (or people creating courses for those sites) may not use this content without permission (this includes, but is not limited to, for-profit schools and universities and commercial education sites such as Corsera, Udacity, LinkedIn Learning, and other similar sites).   