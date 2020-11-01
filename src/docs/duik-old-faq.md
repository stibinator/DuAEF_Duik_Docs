# ![faq Icon](img/duik-icons/help-icon-r.png) Frequently Asked Questions

These questions all concern old versions of _Duik_ or _After Effects_ and they're all fixed by just updating your software!

[TOC]

## General

### Can I use Duik on After Effects XX? (replace XX by any version name)

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

### When using some tools, this alert is shown: `Internal Verification Failure: Unexpected match name searched for in group" ( 29::0 )`, what can I do?

This is a bug in After Effects CC2014 and CC2014.1, it is not an issue from Duik. Update After Effects to CC2014.2, or upgrade to a newer version.

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
