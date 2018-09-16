# \<b7-parallax\>

A visually correct parallax implementation that models the perspective and distance of the layers.

## Minimal usage
```html
<html>
  <head>
    <link rel="stylesheet" href="b7-parallax.css" module/>
    <style>
      .scroll-container {
        --b7-parallax-camera-distance: 3; /* The distance of the virtual camera from the screen plane in centimeters. */
      }

      .background-layer {
        --b7-parallax-layer-distance: -1; /* The distance of the layer from the screen plane in centimeters */
      }

      .screen-layer {
        --b7-parallax-layer-distance: 0; /* The distance of the layer from the screen plane in centimeters */
      }

      .foreground-layer {
        --b7-parallax-layer-distance: 1; /* The distance of the layer from the screen plane in centimeters */
      }

      /*
        background-layer    screen-layer    foreground-layer            (camera)
              -1cm              0cm             1cm                       3cm
              .                 .                 .                        .
              |                 .                 .                        .
              |                 |                 .                        .
              |-----------------|-----------------|-----------------------(*)
              |                 |
              |
      */
    </style>
  </head>
  <body>
    <div class="scroll-container b7-parallax-scroll-container">
      <div class="b7-parallax">
        <div class="background-layer">Background</div>
        <div class="screen-layer">Screen</div>
        <div class="foreground-layer">Foreground</div>
        <div></div>
      </div>
    </div>
  </body>
</html>
```