# Viewport-relative units

- Another element used in [[css-responsive-design]]
- _Viewport-relative units_ are _relative_ to the _size of the viewport_
- Viewport unit values are _percentage values_
- Viewport is the visible area of a web page on a user's device or browser window.
- Viewport-relative units are used to create responsive layouts that adapt to different screen sizes and orientations.
- There are many viewport-relative units, _24 at the time of writing_
- There are 4 common, or base, units that are supported and the other viewport units are variations of these 4 base units
- The base units are
  - `vw` (viewport width): 1% of the viewport's width
  - `vh` (viewport height): 1% of the viewport's height
  - `vmin` (viewport minimum): 1% of the smaller dimension of the viewport
  - `vmax` (viewport maximum): 1% of the larger dimension of the viewport

## Unexpected usage of viewport units

- When using viewport units it's important to be aware of [[css-layout-trashing]]
- _layout trashing_ occurs when the size of the viewport changes dynamically
- since viewport units are relative to the size of the viewport, any cahnge to the viewport size will cause a recalculation of the layout, which can lead to performance issues
- Dynamic changes to the viewport also occur on **mobile browsers**, causing _layout trashing_
- Dynamic changes to the viewport can occur on the following events
  - user resizes the browser window (mostly on desktop)
  - user rotates their device (e.g., from portrait to landscape)
  - on-screen keyboard appears or disappears on mobile devices
  - browser UI elements (like the address bar) show or hide, which affects the viewport size on mobile devices
- These behaviors will cause layout recalculations, thus causing _layout trashing_ as a result performance issues

## Solutions to layout trashing

- To solve unexpected layout trashing when using viewport units
- CSS has derived units that are restrict to a specific context, preventing layout trashing
- These units are **small viewport units** and **large viewport units**

## Large/Small Viewport Units

- Large viewport unit refers to the viewport size when all the UX elements are hidden, and the viewport is at it's largest size
- Small viewport unit refers to the viewport size when all the UX elements are visible, and the viewport is at it's smallest size
- Small viewport unit refers to the viewport size at it's smallest
- _Large viewport units_ have the prefix `l` and _small viewport units_ have the prefix `s`
- Large Viewport Units: `lvw`, `lvh`, `lvmin`, `lvmax`
- Small Viewport Units: `svw`, `svh`, `svmin`, `svmax`

### Dynamic Viewport Units

- If the default behavior of viewport units is desired we can use _dynamic viewport unit_
- Dynamic viewport unit sets the value to the current size of the viewport at the time of evaluation, and does not change when the viewport size changes after evaluation
- Dynamic viewport units have the prefix `d`

#### Question

- Does the viewport size change after evaluation
- Does the re-calculation continue after the first evaluation, or does it stop after the first evaluation?

[@grant2024] ch. 2.4
