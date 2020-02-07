# ![faq Icon](img/duik-icons/help-icon-r.png) Frequently Asked Questions

If you don't find the answer to your question here, come and ask for help on [the official forum](https://forum.rainboxprod.coop) or on [Discord](https://discord.gg/hNuKny8)!

[TOC]

## General

### Can I use Duik on After Effects XX? (replace XX by any version name)

#### Duik Bassel

See the section entitled ["Installation"](install-duik.md).

#### Previous versions of Duik and After Effects

If you need older versions of Duik which work with earlier versions of After Effects, you can get them there: https://github.com/Rainbox-dev/DuAEF_Duik/tree/master/Release/Duik

Duik 15.52 works with CS4 and all more recent versions.

Duik 10 "oldafter" even works with After Effects 7.0!

!!! note
    Duik 15.52 can not be installed on the first After Effects v16.0 (CC2019) because of the missing `PresetEffects.xml` file. This is fixed in After Effects 16.1 and more recent versions.

### Can I keep (or safely remove) the older versions of Duik (15)?

Duik Bassel can be installed along with Duik 15 or any other older version, it will not replace them, and you can continue to use both without any issue.

However, if you don't need Duik 15 anymore, you can safely remove it: just delete all files with "duik" in their names in the `ScriptUI Panels` folder of After Effects, _except_ `Duik Bassel.jsx` which is the only one needed by Duik Bassel.

### After Effects shows an expression error saying `Unterminated string constant` when renaming layers or puppet pins.

This is a known issue when using After Effects versions older than CC2017 on Mac OSX Sierra or more recent. If you rename elements using the [Rename](../Rigging-Tools/#rename) tool of Duik it should work correctly.
This has been fixed in After Effects CC2017.

### Duik's user interface does not display correctly (it's cropped), I can’t see all of it, what should I do?

This is a bug in After Effects CC and CC2014 with windows and HiDPI screens (bigger than FullHD, 1920*1080), Duik can not do anything about it.

There are three workarounds:

- Set the scaling of the display to 100% in the Microsoft Windows settings.
- Run Duik from the menu “File/Scripts/Run script...” in After Effects, instead of the “Windows” menu. But in this case, Duik won’t be dockable.
- Update After Effects

### It seems I have missing buttons and tools in Duik, compared to what I can see in tutorials, screenshots, etc. Where are they?

Duik Bassel has three user interface modes, and the default one, the _Rookie_ mode does not include the most advanced tools; it is designed to be easy-to-use but powerful enough to rig and animate any kind of characters. If you're a beginner with Duik, you should not need the most advanced tools.

To change the mode of the user interface and switch to _Normal_ or _Expert_ mode, go to the [settings](settings.md) panel.

### When using some tools, this alert is shown: `Internal Verification Failure: Unexpected match name searched for in group" ( 29::0 )`, what can I do?

This is a bug in After Effects CC2014 and CC2014.1, it is not an issue from Duik. Update After Effects to CC2014.2, or upgrade to a newer version.

### Duik worked well, but it won't start anymore. What can I do?

Sometimes, the files Duik needs to run smoothly get corrupted, especially (but not only) on Mac OS. If this is the case, Duik may not even be able to start anymore, or may be showing a script alert at start.
In this case, follow [the procedure described here](install-duik.md#fix-uninstall-duik) to re-initialize it.

## Rigging

### How can I scale a rigged character in Duik Bassel?

It is not possible to scale the rig itself yet without adjusting some expressions, **but**:

With the new "Extract Controllers" feature, you can scale a rigged character:

    1. Add the rigged comp into another comp.
    2. Select the precomposition layer and, in the controllers panel of Duik, click on "Extract controllers"  

You can then animate from outside of the precomp, with the extracted controllers, AND you can scale the precomposition layer to scale the rig (the controllers will follow).  
We think this is a good workaround, you just have to take care of the resolution as it's a precomposition (and rasterization may not work properly with the rig), scaling up will damage it a bit, but scaling it down is ok.

### How can I use the _connector_ to connect a single slave property to multiple master properties?

Use a [List](duik-list.md)!

### What can I do to make Duik work better with imported vector layers (Illustrator, SVG, Flash...) with continuous rasterization activated?

After Effects’ puppet tool (and Duik bones) is a pixel tool, but using continuous rasterization is using vector layers, so this raises some issues which are difficult to work around.

IK have to work with coordinates of the layers, and continuous rasterization may mess up those coordinates too...

However, the best you can do is converting those illustrator layers into shape layers (right click on the layer), which work better with the puppet tool and Duik.
You can just precompose those layers too, while scaling them up in the precomposition to keep the quality of vectors.

### How can I create a "Look At" effect?

What is called _Look At_ in some 3D software and older versions of Duik is basically IK controlling an single element (Duik calls this a one-layer IK).  
To add a _Look At_ on a layer with Duik, first select the target, then the layer, and click on the [Autorig & IK](autorig.md) button in the [Links & Constraints](constraints.md) panel. This will create IK on the layer, and a controller to use as a target. You can then adjust the parenting if you wish, especially parenting the target layer to the controller.

### The hominoid is facing left. I'd like it to face right.

The direction the hominoid is facing doesn't really matter, as the Auto-Rig will adjust to the locations of the Structures at the time you'll run it. Just move each Structure element to the corresponding limb of your character, one by one, and then run the Auto-Rig. Don't forget the [Edit Mode](structure-tools.md) to help you move a Structure without moving its children if you need.

### The Connector creates an additionnal layer, is there any way to prevent this?

In short: no. This additionnal layer makes things more stable and is needed by the latest versions of Duik. It can also be better for the users, as with this layer, all connector parameters are assembled on the same layer and easy to find and adjust.

!!! note
    Duik may even use the same principle for other tools, like the wiggle when applied on multiple layers. We're thinking of an option to collect all Duik effects on the same controller in this case.

## Animation

### When applying the walk cycle, the controllers of the hands seem to be deactivated, why's that?

The procedural walk cycle animates the arms with Forward Kinematics (FK) and thus deactivates the Inverse Kinematics (IK). They do not need to translate anymore as the animation is on the *angles* of the individual FK controls.

If you want to animate/adjust the arms, you can either adjust the values in the *Individual FK* controls in the effects of the controllers, or you can re-enable the IK, but this will deactivate the procedural animation on the arms.

!!! note
    You can animate the switch between IK and FK, and Duik provides a tool to ease this *[IK/FK switch](ik-fk-switch.md)* process.

### When applying the walk cycle, the character walks backwards, how to change this?

In the effect of the walk cycle controller, you can change the sign of the walk speed to change the direction the character walks. Change it to negative or positive to change the direction.

### How can I use dashed lines with the motion trail?

The trail with advanced parameters turned on uses a filled shape instead of a stroke, so it is not possible to have dashes. Turning of the advanced parameters will hide the *fill* will allow you to adjust the *stroke* and add dashes.

### When duplicating the motion trail effect on a motion trail layer, the motion trail is not duplicated. How can I duplicate a motion trail?

To duplicate a motion trail, you can't just duplicate the effect; the content of the shape layer needs to be adjusted too.

There are two ways to add multiple motion trails for the same layer:

- Duplicate the motion trail layer instead of just the effect.
- Use the *motion trail button* in Duik to re-create a new motion trail for the same layer.

## Changes between Duik Bassel, Duik 15 and older versions

### Duik 15 came with an installer, Duik Bassel is just a zip, why?

Duik Bassel is so simple to install, it does not need an installer any more. Read the [installation instructions](install-duik.md).

### The Duik 15 installer included *Dugr* too, where can I find it now?

Dugr is available on the [Rainbox website](https://rainboxprod.coop/en/tools/dugr/).

### Where is the *Rotation Morph*?

The *Rotation Morph* is replaced by the new ***Connector*** which is able to do exactly the same stuff, plus many more.

### Where is the *Orient to path* tool?

This tool has been removed as you can achieve the same thing natively in After Effects, in the "Geometry/orientation" options of the layers.

### Where is the *IK Goal*?

The *IK Goal* is replaced by the new ***Orientation Constraint*** which is able to do exactly the same stuff, plus many more.  
To create what was the *IK Goal*, simply add an empty orientation constraint to the layer. To connect its rotation to a controller like what the *IK Goal* did when you had a controller selected, modify the constraint on the layer to constrain it to the controller you want.

### Where is the hand *goal* checkbox?

This checkbox was removed, as the "Enable IK" option in the effect of the IK is already connected to the "goal" behaviour of the hand.

After a lot of tests, we came to the conclusion that the goal was needed only in IK and not needed in FK, so the easier way to (de)activate it was to link it to the IK button too.

Anyway, if you need to disable it but keep the IK active, you just have to add a Null object onto the end of the structure and link it to the forearm. Then, link the hand to this null object.
To control the rotation with the controller, you can also add an small expression in the null's rotation: `value + pickWhipToTheControllerRotation`
