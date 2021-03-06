<img src="http://www.brenwill.com/docs/cocos3d/Logos/cocos3d-Banner-150h.png">

Copyright (c) 2010-2014 [The Brenwill Workshop Ltd.](http://www.brenwill.com) All rights reserved.

Cocos3D
=======

Table of Contents
-----------------

- About Cocos3D
- Installation
- Creating Your First Cocos3D Project
- Demo Applications
    - CC3DemoMashUp - demos all important Cocos3D features
    - CC3Demo3DTiles - demos adding running many concurrent layers and scenes
    - CC3Performance - demos performance capabilities and testing
    - CC3DemoMultiScene - demos using Cocos3D with Xcode Storyboards
- Cocos3D and Cocos2D Static Libraries
- Cocos2D Version Compatibility
- Compiling for Android
- Documentation
- Creating POD 3D Model Files
- Demo Models


About Cocos3D
-------------

Cocos3D is a sophisticated, yet intuitive. and easy-to-use, 3D application development
framework for the iOS, Android, and Mac OSX platforms. With Cocos3D, you can build
sophisticated, dynamic 3D games and applications using Objective-C.

- Build 3D apps for iOS devices, Android devices, or Mac computers running OSX. The same 3D
  content and game logic will run unchanged under iOS, Android, or Mac OSX.
- Use OpenGL programmable pipelines for sophisticated GLSL shader rendering, or use OpenGL 
  fixed pipelines for simpler configurable rendering.
- Supports OpenGL ES 2.0 or OpenGL ES 1.1 on iOS and Android devices, and OpenGL on Mac OSX.
- Seamless integration with Cocos2D. Rendering of all 3D model objects occurs within a special 
  Cocos2D layer, which fits seamlessly into the Cocos2D node hierarchy, allowing 2D nodes such 
  as controls, labels, and health bars to be drawn under, over, or beside 3D model objects. 
  With this design, 2D objects, 3D objects, and sound can interact with each other to create 
  a rich, synchronized audio-visual experience.
- Seamless integration with the iOS UIViewController framework.
- Pluggable loading framework for 3D models exported from familiar 3D editors such as Blender, 
  3ds Max or Cheetah3D, or through industry standard 3D object files such as Collada or PowerVR POD,
  or even from your own customized object file formats.
- Loading 3D models, textures and GLSL shaders can be performed on a background thread while the
  scene is being displayed, and automatically added to the scene when loading is complete.
- 3D models can be selected and positioned by touch events and gestures, allowing intuitive user
  interaction with the objects in the 3D world.
- 3D models can include animation sequences, with full or fractional animation, in multiple tracks. 
  Animation tracks can be blended together, and cross-fading actions can be used to smoothly 
  transition between tracks.
- 3D model objects can be arranged in sophisticated structural assemblies, allowing child objects
  to be moved and oriented relative to their parent structure.
- 3D models and assemblies can be easily duplicated. Each duplicated model can be independently
  controlled, animated, colored, or textured. But fear not, underlying mesh data is shared between
  models. You can quickly and easily create swarming hoards to populate your 3D world, without
  worrying about device memory limitations.
- 3D models, cameras, and lighting can be manipulated and animated using familiar Cocos2D Actions,
  allowing you to quickly and easily control the dynamics of your 3D world, in a familiar, and
  easy-to-use programming paradigm.
- 3D objects can be covered with dynamic materials and textures to create rich, realistic imagery.
- Multi-texturing and bump-mapped textures are available, allowing you to create sophisticated surface effects.
- Vertex skinning, also often referred to as bone rigging, allowing soft-body meshes to be 
  realistically deformed based on the movement of an underlying skeleton constructed of bones and joints.
- Automatic shadowing of models using shadow volumes.
- Collision detection between nodes.
- Ray-casting for nodes intersected by a ray, and the local location of intersection on a node
  or mesh, right down to the exact mesh intersection location and face.
- The 3D camera supports both perspective and orthographic projection options.
- Objects can dynamically track other objects as they move around the world. The 3D camera 
  can dynamically point towards an object as it moves, and other objects can dynamically point
  towards the camera as it moves.
- Lighting effects include multiple lights, attenuation with distance, spotlights, and fog effects.
- Mesh data can be shared between 3D objects, thereby saving precious device memory.
- Mesh data can freely, and automatically, use OpenGL vertex buffer objects to improve performance
  and memory management.
- Culling of 3D objects outside of the camera frustum is automatic, based on pluggable, 
  customizable object bounding volumes.
- Automatic ordering and grouping of 3D objects minimizes OpenGL state changes and improves
  rendering performance. Pluggable sorters allow easy customization of object sorting, ordering,
  and grouping for optimal application performance.
- Rendering to texture for dynamic textures within a scene, or to create sophisticated post-processing effects.
- Automatic rendering of the scene to an environment map texture, to create automatic environment
  reflections and refractions.
- Integrated particle systems:
	- 3D point particles provide efficient but sophisticated particle effects.
	- 3D mesh particles allow particles to be created from any 3D mesh template (eg- spheres,
	  cones, boxes, POD models, etc).
- Automatic OpenGL state machine shadowing means that the OpenGL functions are invoked only when a
  state really has changed, thereby reducing OpenGL engine calls, and increasing OpenGL throughput.
- Sophisticated performance metrics API and tools collect real-time application drawing and updating
  performance statistics, for logging or real-time display.
- Sophisticated math library eliminates the need to use OpenGL ES function calls for matrix mathematics.
- Fully documented API written entirely in familiar Objective-C. No need to switch to C or C++ to work with 3D artifacts.
- Extensive logging framework to trace program execution, including all OpenGL ES function calls.
- Includes demo applications and Xcode templates to get you up and running quickly.


Installation
------------

1. The Cocos3D framework works with [Cocos2D](http://www.cocos2d-iphone.org). Before installing
   Cocos3D, you must [download](http://www.cocos2d-iphone.org/download) and install Cocos2D.<br/><br/>

	The same Cocos3D distribution can be used with `Cocos2D 3.0`, `Cocos2D 2.1` or `Cocos2D 1.1`.
	Link to `Cocos2D 3.0` or `Cocos2D 2.1` to make use of the more advanced shader-based 
	programmable-pipeline available with OpenGL ES 2.0 (iOS) or OpenGL (OSX). Or link to 
	`Cocos2D 1.1` to use the simpler configurable fixed-pipeline of OpenGL ES 1.1 (iOS), 
	and avoid the need to write GLSL shaders.

2. Download the latest [stable Cocos3D release](http://cocos3d.org), or clone the
   [Cocos3D GitHub repository](http://github.com/cocos3d/cocos3d).

3. Unzip the Cocos3D distribution file.

4. Open a Terminal session, navigate to the unzipped Cocos3D distribution directory, and run 
   the `install-cocos3d` script using one of the following formats:

		./install-cocos3d.sh
		./install-cocos3d.sh -2 cocos2d-version

	A Cocos2D distribution must be installed. In the first format, the Cocos3D demo apps 
	will be linked to the latest major version of Cocos2D that is installed.</br></br>
	
	By using the -2 option, you can specify the version of Cocos2D to which the Cocos3D demo
	apps should be linked. The ***cocos2d-verison*** argument can be either an installed 
	Cocos2D version number (`v3`, `v2`, or `v1`), or a path to a specific Cocos2D distribution 
	retrieved from GitHub.

	An example of each format is as follows:

		./install-cocos3d.sh -2 v3
		./install-cocos3d.sh -2 "../cocos2d-iphone-release-3.0-RC4"

	The first format will link the Cocos3D demo apps to the `Cocos2D 3.0` template libraries 
	that you have most recently installed. When using this format, you must have previously 
	installed the corresponding version of Cocos2D. This installation format is suitable for 
	most Cocos3D development activities.</br></br>

	The second format will link the Cocos3D demo apps to the specific Cocos2D distribution 
	that was downloaded into the specified directory. This format can be useful when testing 
	against specific Cocos2D versions downloaded from GitHub. You may use either a relative 
	path (as above), or an absolute path. If for some reason the relative path cannot be 
	correctly resolved on your system, or the resulting links to the Cocos2D library are 
	not accurate, try again using the full absolute path.

	If you encounter errors during installation, it's typically because you are trying
	to run the installer without first navigating to the Cocos3D distribution directory.
	Be sure to run the installer from the Cocos3D distribution directory.

5. That's it!

Keep in mind that Cocos3D does not "patch" your Cocos2D installation. Instead, you install
Cocos3D alongside Cocos2D, and link to it using the installation script.


Creating Your First Cocos3D Project
-----------------------------------

The `install-cocos3d.sh` script also installs several convenient Xcode project templates.

To get started with your first Cocos3D project, open Xcode, click on the File->New->NewProject...
menu selection, and select one of the templates in the `Cocos3D` group under either the
`iOS` or `OS X` sections.

The same Cocos3D distribution can be used with `Cocos2D 3.0`, `Cocos2D 2.1` or `Cocos2D 1.1`.
Choose the Cocos3D template that corresponds to the version of Cocos2D that you want to
work with, and which you previously downloaded and installed.

The template project starts with a working 3D variation on the familiar *hello, world*
application, which you can use as a starting point for your own application.

When you ran the `install-cocos3d` script (see the Installation section above), it checked
which versions of Cocos2D you have installed, and only installs those Cocos3D templates that 
work with the major Cocos2D versions that you have installed. If you install a different major
version of Cocos2D (3.0, 2.1 or 1.1), you can run the `install-cocos3d` script again to 
automatically add the Cocos3D templates that are designed for that major version of Cocos2D.


Demo Applications
-----------------

The best way to understand what Cocos3D can do is to look at the examples and code in the demo
applications that are included in the Cocos3D distribution. These demos, particularly the
`CC3DemoMashUp` app, will help you understand how to use Cocos3D, and demonstrate many of the
key features and capabilities of Cocos3D.

For convenience, to access all of the demos together, open either the `cocos3d-iOS.xcworkspace`
or `cocos3d-OSX.xcworkspace` Xcode workspace. You can also open each demo project individually
in the Projects folder.

At the time of this release, the current version of Cocos2D is `3.0`, and by default, the demo
apps within the Cocos3D distribution are pre-configured to use that version. To build and run
the demo apps with a different version of Cocos2D, follow the steps described below in the 
section titled *Cocos2D Version Compatibility*.

The following demo apps are included in the Cocos3D distribution:


###CC3DemoMashUp

Please read the class notes of the `CC3DemoMashUpScene` class for a full description of how to
run and interact with this demo, and what features it covers.

Your camera hovers over a scene that includes animated robots, bouncing beach-balls,
spinning globes, and a selection of animated teapots. This is a sophisticated demo that
showcases many interesting features of Cocos3D, including:

- loading mesh models, cameras and lights from 3D model files stored in the PowerVR POD format
- creating mesh models from static header file data
- sharing mesh data across several nodes with different materials
- loading 3D models from a POD file converted from a Collada file created in a 3D editor (Blender)
- assembling nodes into a hierarchical parent-child structual assembly.
- programatic creation of spherical, box and plane meshes using parametric definitions.
- texturing a 3D mesh from a CCTexture image
- transparency and alpha-blending
- translucent and transparent textures
- coloring a mesh with a per-vertex color blend
- multi-texturing an object using texture units by combining several individual textures into overlays
- DOT3 bump-map texturing of an object to provide high-resolution surface detail on a model
  with few actual vertices
- Vertex skinning with a soft-body mesh bending and flexing based on the movement of skeleton bone nodes.
- Copying soft-body nodes to create a completely separate character, with its own skeleton, that can be
  manipulated independently of the skeleton of the original.
- animating 3D models using a variety of standard Cocos2D CCActionIntervals
- overlaying the 3D scene with 2D Cocos2D controls such as joysticks and buttons
- embedding 2D Cocos2D text labels into the 3D scene
- incorporating 2D Cocos2D CCParticleEmitters into the 3D scene (as a sun and explosion fire)
- emitting 3D point particles from a moving nozzle, with realistic distance attenuation
- emitting two different types of 3D mesh particles, with distinct textures, from a moving nozzle,
  with each particle moving, rotating, and fading independently
- creating a tightly focused spotlight whose intensity attenuates with distance
- directing the 3D camera to track a particular target object
- directing an object to track the camera, always facing (looking at) the camera (aka halo objects)
- directing an object to track another object, always facing (looking at) that object
- selecting a 3D object by touching the object on the screen with a finger
- placing a 3D object on another at a point that was touched with a finger
- adding a small CC3Layer/CC3Scene pair as a child window to a larger CC3Layer/CC3Scene pair.
- moving, scaling and fading a CC3Layer and its CC3Scene
- creating parametric boxes and texturing all six sides of the box with a single texture.
- adding an object as a child of another, but keeping the original orientation of the child
  (addAndLocalizeChild:)
- handling touch-move events to create swipe gestures to spin a 3D object using rotation
  around an arbitrary axis
- toggling between opacity and translucency using the isOpaque property
- choosing to cull or display backfaces (shouldCullBackFaces)
- creating and deploying many independent copies of a node, while sharing the underlying mesh data
- drawing a descriptive text label on a node using CC3Node shouldDrawDescriptor property.
- drawing a wireframe bounding box around a node using CC3Node shouldDrawWireframeBox property.
- automatically zooming the camera out to view all objects in the scene
- constructing and drawing a highly tessellated rectangular plane mesh using CC3PlaneNode
- caching mesh data into GL vertex buffer objects and releasing vertex data from application memory
- retaining vertex location data in application memory (retainVertexLocations) for subsequent calculations
- moving the pivot location (origin) of a mesh to the center of geometry of the mesh.
- attaching application-specific userData to any node
- applying a texture to all six sides of a parametric box
- displaying direction marker lines on a node to clarify its orientation during development.
- displaying a repeating texture pattern across a mesh
- creating and displaying shadow volumes to render shadows for selected nodes
- detecting the local location of where a node was touched using ray tracing
- collision detection between nodes
- texturing a node with only a small section of single texture
- using the CC3Scene onOpen method to initiate activity when a scene opens
- using pinch and pan gestures to control the movement of the 3D camera
- using tap gestures to select 3D objects, and pan gestures to spin 3D objects
- bitmapped font text labels
- moving individual vertex location programmatically
- using OpenGL ES 2.0 shaders.
- loading PowerVR PFX effects files and applying them to materials
- environmental reflections using a cube mapped texture.
- render-to-texture the scene for display within the scene.
- render-to-texture to create additional visual effects using post-rendering image processing.
- render depth-to-texture to visualize the contents of the depth buffer.
- read pixels from a rendered framebuffer
- replace framebuffer and texture pixels with programmatic content
- create CGImageRef from a rendered framebuffer
- dynamically generate an environmental cube-map for creating a real-time dynamic reflective surfaces.
- apply multiple animation tracks to a model, blend them together, and smoothly transition between
  animation tracks using a cross-fade action.

In addition, there are a number of interesting options for you to play with by uncommenting
certain lines of code in the methods of this class that build objects in the 3D scene,
including experimenting with:

- simple particle generator with multi-colored, light-interactive, particles
- simple particle generator with meshes updated less frequently to conserve performance 
- different options for ordering nodes when drawing, including ordering by mesh or texture
- configuring the camera for parallel/isometric/orthographic projection instead of the default
  perpective projection
- mounting the camera on a moving object, in this case a bouncing ball
- mounting the camera on a moving object, in this case a bouncing ball, and having the
  camera stay focused on the rainbow teapot as both beach ball and teapot move and rotate
- directing an object to track another object, always facing that object, but only
  rotating in one direction (eg- side-to-side, but not up and down).
- displaying 2D labels (eg- health-bars) overlayed on top of the 3D scene at locations 
  projected from the position of 3D objects
- disabling animation for a particular node, in this case the camera and light
- invading with an army of teapots instead of robots
- ignore lighting conditions when drawing a node to draw in pure colors and textures
- displaying descriptive text and wireframe bounding boxes on every node
- displaying a dynamic bounding box on a 3D particle emitter.
- making use of a fixed bounding volume for the 3D particle emitter to improve performance.
- permitting a node to cast a shadow even when the node itself is invisible by using the 
  shouldCastShadowsWhenInvisible property
- Skybox using a cube mapped texture.
- Cocos2D CCSprite displaying the television screen rendered texture


###CC3Demo3DTiles

A simple demo that lays out multiple small Cocos3D scenes as layers in a larger controllable
Cocos2D layer. The effect is a grid of tiles, with each tile displaying a separate 3D scene,
each containing its own camera and lighting. The main node in each 3D tile can be rotated
under touch control.

This demonstrates the ability to simply include 3D objects in an otherwise 2D game, and 
techniques for optimizing under those conditions. It also demonstrates touch control when
many 3D scene are visible concurrently.


###CC3Performance

This is a simple demo of the performance characteristics of Cocos3D. It demonstrates how to
collect detailed statistics about your application's performance. In doing so, it presents
a number of models, and, through the user interface, allows you to control the type of model
loaded, and how many copies to render.

You can dynamically experiment with how different model types, sizes and quantities affect
the performance of Cocos3D. You can also use this performance demo app to compare performance
across different devices.


###CC3DemoMultiScene

This demo app is a sophisticated combination of the three demo apps listed above. It 
demonstrates how to include Cocos3D in a UIView using Xcode Storyboards. Using standard
UIKit controls, you can load any of the Cocos3D demos listed above, then shut down the 
running demo, and load a different Cocos3D demo.


Cocos3D and Cocos2D Static Libraries
------------------------------------

The Cocos3D distribution includes `Xcode` projects to build static libraries for Cocos3D and Cocos2D.
These are available in the `cocos3d-iOS.xcworkspace` and `cocos3d-OSX.xcworkspace` Xcode workspaces,
and the Xcode projects are also individually available in the `cocos3d-library` and `cocos2d-library`
folders under the `Projects` folder in the Cocos3D distribution.

You can add these static library projects as sub-projects of your `Xcode` app project. Instructions
for adding a static library to your app project are available through Apple's documentation, or
can be found by searching the web. You can also reference how these static libraries have been
added to the demo apps, also available in the `Projects` folder in the Cocos3D distribution.

When adding Cocos3D files to your project, either as a static library, or as individual files, be 
aware that, to ensure the highest performance, the Cocos3D libraries do not use Automatic Reference
Counting (ARC). However, you can seamlessly use the Cocos3D library within an ARC-enabled application.
The Cocos3D static library project provided with the Cocos3D distribution is already configured to 
bypass ARC, and you can simply include this static library project as subproject to your application
project, regardless of whether your application uses ARC or Manual Reference Counting (MRC).

Like any static library, the compiled Cocos3D static library includes only executable code, and does
not include the standard Cocos3D GLSL shader files. If you use the Cocos3D static library in your
application project, and want to use the standard Cocos3D GLSL shader files, you should also drag
the `cocos3d-GLSL` folder in the Cocos3D distribution to the `Xcode` *Project Navigator* panel of your
application project. One further step is required because, by default, `Xcode` treats these GLSL files
as source code files, rather than resource files. After dragging the GLSL files to your application
project in Xcode, select your project in the `Xcode` *Project Navigator*, select the *Build Phases* tab,
and move all of the `.vsh` and `.fsh` files from the *Compile Sources* list to the *Copy Bundle Resources* list.

Finally, the Cocos3D and Cocos2D static libraries require linking to certain other support libraries.
To direct `Xcode` to link with these support libraries, in your application target build settings,
make sure the **Other Linker Flags** (aka `OTHER_LDFLAGS`) entry includes the following entries:
	-ObjC -lz -lstdc++

At the time of this release, the current version of Cocos2D is `3.0`, and by default, the 
static library projects within the Cocos3D distribution are pre-configured to use that version.
To build and run the static libraries with a different version of Cocos2D, follow the steps
described below in the section titled *Cocos2D Version Compatibility*.


Cocos2D Version Compatibility
-----------------------------

Cocos3D under iOS and Android is compatible with `Cocos2D` `3.0` and `Cocos2D` `2.1`, for 
using programmable-pipeline OpenGL ES 2.0, and is compatible with `Cocos2D` `1.1`, for 
using fixed-pipeline OpenGL ES 1.1.

Cocos3D under OSX is compatible with `Cocos2D` `3.0` and `Cocos2D` `2.1`, for using
programmable-pipeline OpenGL. Cocos3D is not compatible with `Cocos2D` `1.1` under OSX.

At the time of this release, the current version of Cocos2D is `3.0`, and by default, the 
demo apps and static libraries within the Cocos3D distribution are pre-configured to use 
that version. To build and run the demo apps or static libraries with a different version 
of Cocos2D, follow the steps described here:

1. Delete the reference to the *cocos2d* and *cocos2d-chipmunk* groups in the `Xcode` *Project Navigator*
   panel. These groups can be found in the `cocos2d-library-iOS` or `cocos2d-library-OSX` project.
2. Run the `install-cocos3d.sh` script again and identify the new version of `Cocos2D` to be linked.
   Keep in mind that you must link `Cocos2D` `3.0` or `Cocos2D 2.1` if you want to use 
   OpenGL ES 2.0 (iOS) or OpenGL (OSX) with a programmable rendering pipeline, and you must link
   `Cocos2D 1.1` if you want to use OpenGL ES 1.1 (iOS & Android) with a fixed rendering pipeline.
3. Add the newly linked Cocos2D files to the project by dragging the `cocos2d` folder from the 
   Cocos3D distribution folder into the `cocos2d-library-iOS` or `cocos2d-library-OSX` 
   project in the `Xcode` *Project Navigator* panel. When prompted for the target to add the source
   code to, select the `cocos2d` target.
4. Add the newly linked Cocos2D Chipmunk files to the project by dragging the `cocos2d-chipmunk`
   folder from the Cocos3D distribution folder into the `cocos2d-library-iOS` or `cocos2d-library-OSX` 
   project in the `Xcode` *Project Navigator* panel. When prompted for the target to add the source
   code to, select the `cocos2d-chipmunk` target.
6. `Cocos2D` `3.0` uses Automatic Reference Counting (ARC). `Cocos2D` `2.1` and `Cocos2D` `1.1`
   do not. You must set the appropriate compiler build setting to ensure the compiler will use
   the correct technique.
	1. In the `cocos2d-library-iOS` or `cocos2d-library-OSX` project, select the `cocos2d` 
	   target in your project settings.
	2. Select the *Build Settings* tab.
	3. Locate the **Objective-C Automatic Reference Counting** (aka `CLANG_ENABLE_OBJC_ARC`)
	   setting for the `cocos2d` target. If you are now linking to `Cocos2D` `3.0`, set this
	   property to `YES`. If you are now linking to `Cocos2D` `2.1` or `Cocos2D` `1.1`, set 
	   this property to NO. Make sure you change only the setting for the `cocos2d` target 
	   within your project. Do not change the setting for the `cocos2d-library-iOS` or 
	   `cocos2d-library-OSX` project itself.
	4. The `cocos2d-chipmunk` part of the `Cocos2D` `3.0` library does *not* use ARC. Ensure
	   the **Objective-C Automatic Reference Counting** (aka `CLANG_ENABLE_OBJC_ARC`) setting
	   of the `cocos2d-chipmunk` target is always set to NO.
7. `Cocos2D` `3.0` supports compiling to the ARM64 architecture. `Cocos2D` `2.1` and
   `Cocos2D` `1.1` do *not* support compiling to the ARM64 architecture. Because of this,
   by default, the **Valid Architectures** (aka `VALID_ARCHS`) build setting for all demo 
   Xcode Projects in the Cocos3D distribution is set to `$(ARCHS_STANDARD_32_BIT)` (which 
   resolves to **armv7 armv7s**), so that the demo projects will compile with all versions
   of `Cocos2D`. If you are now linking to `Cocos2D` `3.0`, you can set this property to
   `$(ARCHS_STANDARD)` (or simply remove this setting from the Project), in all demo Projects,
   to allow compilation to include the ARM64 architecture.
8. As a development optimization, if you are now linking to `Cocos2D` `3.0`, you can set the 
   value of the **Build Active Architecture Only** (aka `ONLY_ACTIVE_ARCH`) build setting in 
   the *Debug* configuration in all demo projects to `YES`. You should not do this if you are
   linking to `Cocos2D` `2.1` or `Cocos2D` `1.1`, as this will prohibit you from building
   the demo apps on devices that use the ARM64 processor.
9. If you have already built the demo app using the old version of `Cocos2D`, delete the 
   contents of your `~/Library/Developer/Xcode/DerivedData` folder, and restart Xcode.


Compiling for Android
---------------------

Cocos3D (along with Cocos2D) is written in Objective-C. Cocos3D has partnered with 
[Apportable] ( http://www.apportable.com) to bring your 3D apps and games to the Android
platform. The Apportable SDK is a free SDK for porting Objective-C applications to Android.

To build and install your app or game project for the Android platform:

1. Download and install the Apportable SDK.
2. Open a `Terminal` window and navigate to the `Xcode` project folder of your Cocos3D app.
3. Run the command: `apportable install` to build and install your Cocos3D app on an
   Android device connected to your computer.
	
Please refer to the Apportable SDK documentation for more information about building,
installing, and debugging your app on Android. If you are building an OpenGL ES 1.1 app, 
you will need to modify the `configuration.json` file in your `Xcode` project, as indicated
in that file.


Documentation
-------------

To learn more about Cocos3D, please refer to the [Cocos3D Programming Guide](http://brenwill.com/2011/cocos3d-programming-guide/)
and the latest [API documentation] (http://brenwill.com/docs/cocos3d/2.0.0/api/).

You can create a local copy of the API documentation using `Doxygen` to extract the documentation
from the source files. There is a `Doxygen` configuration file to output the API documents in the
same format as appears online in the folder Docs/API within the Cocos3D distribution.


Creating POD 3D Model Files
---------------------------

Cocos3D reads 3D model content from POD files.

If you are using *Blender*, *Maya*, or *3DS Max* as your 3D editor, you can install the *PVRGeoPOD*
plugin from Imagination Technologies to export directly from your editor to the POD file format.

For other editors, you can export your 3D model to a file in `COLLADA 1.4` format, and then use
the standalone *PVRGeoPOD* app to convert the COLLADA file to the POD format.

Both the standalone and plugin versions of *PVRGeoPOD* are available free of charge from
Imagination Technologies, the supplier of the GPU's used in iOS devices.

Read the [full instructions](http://brenwill.com/2011/cocos3d-importing-converting-collada-to-pod/)
for more info on where to get the *PVRGeoPOD* converter, and how to use it to generate POD files.

If you are using *Blender* as your 3D editor, and have many `.blend` files to export to POD format,
you can use the command-line batch tool available in the `Tools/Blender-POD Batch Converter`
folder in the Cocos3D distribution. See the `README!.md` file in that folder for instructions.
The *Blender-POD Batch Converter* tool was created by Cocos3D user Nikita Medvedev.


Demo Models
-----------

Some of the POD models that appear in the demo and template apps were designed in Blender and
exported to POD files using the PowerVR *PVRGeoPOD* converter.

As a reference for the creation of your own 3D models for use in Cocos3D, you can find the original
Blender files and DAE files for these POD models in the `Models` folder in the Cocos3D distribution.

