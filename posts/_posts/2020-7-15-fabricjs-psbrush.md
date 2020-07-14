---
layout: demoV4
title: Pressure-sensitive brush
codepen: true
---

This demo shows how to load an extension library called `fabricjs-psbrush` and enable a pressure-sensitive brush on a Fabric.js canvas.
The first example simply instantiates the brush and sets it as `freeDrawingBrush`.

### Use PSBrush (pressure-sensitive brush)

After loading the main script through `script` tag, `fabric.PSBrush` can be initialized at any time. The instance can be assigned to `canvas.freeDrawingBrush` to start drawing.

**Note:** when constructing a `fabricjs.Canvas` instance, `enablePointerEvents` option needs to be `true` so that the brush has access to raw pointer events.

<div
  class="codepen-later"
  data-editable="true"
  data-height="500"
  data-default-tab="result"
  data-prefill='{
    "scripts": [
      "https://unpkg.com/fabric@4.0.0-rc.1/dist/fabric.js",
      "https://unpkg.com/@arch-inc/fabricjs-psbrush@0.0.15/dist/index.js"
    ]
  }'
>
<pre data-lang="html">
  <canvas id="c" width="400" height="300" style="border:1px solid #ccc"></canvas>
</pre>
<pre data-lang="js">
  // Create a Fabric.js canvas
  let canvas = new fabric.Canvas('c', {
    isDrawingMode: true,
    enablePointerEvents: true
  });
  
  // Initialize a brush
  let brush = new fabric.PSBrush(canvas);
  brush.width = 10;
  brush.color = "#000";
  canvas.freeDrawingBrush = brush;

  // Feel free to explore properties of this brush...
  window.brush = brush;
</pre>
</div>
