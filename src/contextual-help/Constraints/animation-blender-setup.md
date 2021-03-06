The Animation blender is a tool to animate using markers to trigger animations.

In a composition, you can have several animations, one after each other.
The animation blender is a simple controller (a layer) where you add markers which will trigger these animations.
The animation blender is able to blend the animations together during transitions right after a marker, and it's also able to loop the animations after they have been triggered, if you need.

To use it, the animated properties or composition which you want to trigger with markers have to be set up.
Once they are ready, a simple tool in the Animation panel (Tools tab) of Duik can be used to easily set the markers to trigger animations.

There are two things which need to be set up: the animations, and the Blender itself.
The first part of the panel allows to quickly set the animations, while the second part is used to set the Blender up.

Blender Animations

As soon as you have animated what you want to trigger, you have to set some markers to define when these animations begin and end. Each marker must have a name (which can be whatever you want), and a duration which is exactly the duration of your animation.
With versions of After Effects more recent than 14.0 (CC2017), these markers can be set on the composition itself, but with older versions, they have to be set on a layer named exactly "Duik | Animation blender".
To help you to set these markers, you can set their name in Duik, and then click the "Set" button. This will create a marker where it should be, using the work area of the composition to set its time and duration in a single click.

Blender Setup

Setting the composition up for the Blender is easy:
1. Select the composition containing the animations you want to set up in the menu. You can use the eyedropper to quickly get the active composition.
2. Select the composition from where you want to animate using the Animation Blender. It can be the same composition as the rigged one if you wish.
3. You can choose to rig all animated properties, or only the selected ones. Setting only the selected properties up allows to have several controllers for the same composition, thus allowing to rig very complicating things...
4. Click on the "Blend!" button to set everything up.

Use

To use the blender, you just have to add markers on the controller layer. Each marker will trigger the corresponding animation.
Note: their name have to be exactly the same, and it is case sensitive.
A simple tool in the Animation panel (Tools tab) of Duik can be used to easily set these markers, but you can also do it directly inside After Effects (the the shorcuts below).

There are a few options in the effects of the controller, to loop the animation, and to control how they may blend during transitions. You can control if they have to blend, the duration of the transition (in seconds), and how it is interpolated.

To temporarily disable the Blender, you can disable the effect on the controller. This makes it easy to add new animations or modifiy the existing ones.

== Shortcuts for markers in After Effects ==

Note that some of these shortcuts were not available in all versions of After Effects, but were added in the latest versions.

- [*] adds a new marker on the selected layer, or on the composition without any selected layer.
- [Alt + *] opens the marker editor window before adding the marker, where you can set a comment.
- [Alt + Click] on a marker changes its duration.
- [Ctrl + Click] on a marker removes it.
- [Shift + 1/2/3...9] adds a marker with the corresponding number as its comment.
