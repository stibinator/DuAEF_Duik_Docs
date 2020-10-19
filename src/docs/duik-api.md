# Duik API

Almost all Duik features are now very easy to include and use in your own scripts, thanks to the Duik Application Programming Interface (API).

The idea is just to include the API at the beginning of your script: `#include 'Duik16_api.jsxinc` to get an easy access to all Duik features, as very simple functions.  

Here's a very simple example showing how to create a Structure for a hominoid, rigging it, and applying the walk cycle, in the current composition:

    //encapsulate everything to avoid global variables !important!
    (function(thisObj) {
        //include the API
        #include 'Duik16_api.jsxinc'
        //Now the Duik API is available in the Duik object, and DuAEF is also available.

        //We need to initialize DuAEF before using it. You must provide a script name and version.
        DuAEF.init("Your Awesome Script Name", "1.0.2");

        //Now you can create your UI if any, and initialize what you need.
        //DuAEF can be of great help, it has a lot of methods for creating the UI, handle After Effects, and more.
        //Read the reference at duaef-reference.rainboxlab.org

        //When everything is ready and before using the Duik API,
        //We need to tell DuAEF we're entering run state so it can finish to prepare its stuff.
        DuAEF.enterRunTime();
        
        // Create a hominoid structure
        // The whole API is contained in the Duik object
        Duik.structures.mammal();
        // Select all Structures
        Duik.structures.select();
        // Run the Autorig
        Duik.constraints.autorig();
        // Select all controllers
        Duik.controllers.select();
        // Make the character walk!
        Duik.automation.walk();
        //Have Fun!
    })(this);


You can [download the latest version of the API on Github](https://github.com/Rainbox-dev/DuAEF_Duik/releases).

This API has a [comprehensive documentation available here](http://duik-api.rainboxlab.org).

The Duik API only has high-level methods, most of them working without needing any parameter, which makes it very easy to use. All methods adjust their behaviour according to the After Effects context and work with the active composition, the selected layers, the selected properties... If you need a lower-level access to what can be achieved with Duik (for example to rig specific layers, build an advanced autorig, add IK on specific layers, etc.), you can use the [Duduf After Effects Framework (DuAEF)](duaef.md) which Duik is based on, and which includes much more tools.