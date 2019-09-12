# ![spring Icon](img\duik-icons\automation\spring-icon-r.png) Spring

![Spring panel](img\duik-screenshots\S-Rigging\S-Rigging-Automations\Spring.PNG)

The ***Spring*** will add *follow through* / *overlap* /*overshot* to your animations and it is able to animate automatic bounces.

## Setup

The *Spring* is not restricted to the position of a layer, but can work on any property.

1. Select the properties
2. Click on the *Spring* button

The *Spring* is computed depending on the velocity of the layer, whenever it stops. This means it will work better if the last keyframe interpolation is set to linear and not Bézier, so the *Spring* can compute the motion according to the last velocity. If the property slows down before stopping (with a Bézier ease), there can not be any swinging.

It can be adjusted in the effects of the corresponding layer.

## Effect

![Spring pannel](img\duik-screenshots\S-Rigging\S-Rigging-Automations\Spring-effects.PNG)
![Spring example](img\duik-screenshots\S-Rigging\S-Rigging-Automations\automation-illustration\spring-example.png)

- The elasticity controls both the amplitude and the frequency of the motion. A Higher elasticity will result in a higher frequency but lower amplitude.

- The damping controls how long it takes for the property to stop to move. This value is arbitrary and represent a strength. The actual duration of the spring depends of the incoming velocity of the property.

- If the spring is set on a spatial property, there are two ways to compute it:  

    - **Basic**: the computation is made with the keyframes of the property itself.  
    - **Simulation**: the computation is made with the actual motion of the layer. This is heavier to compute, but it does not need any keyframe on the layer, it is its actual translation which is used, even if its from a parent layer.

- If the spring is set on a simple value (with only one dimension), you can set it to "bounce". This means that instead of swinging around the stopping value, it will bounce against it. This can be useful for bouncing stuff like balls.  
If you need this "bounce" option on a position, separate the dimensions in After Effects firts, then add the spring to the axis which needs to bounce.

![Spring example gif](img\examples\cart.gif)
