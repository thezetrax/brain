### Dynamic Viewport Units

- If the default behavior of viewport units is desired we can use _dynamic viewport unit_
- Dynamic viewport unit sets the value to the current size of the viewport at the time of evaluation, and does not change when the viewport size changes after evaluation
- Dynamic viewport units have the prefix `d`, e.g. `dvw`, `dvh`, `dvmin`, `dvmax`

#### Question

- Does the viewport size change after evaluation
- Does the re-calculation continue after the first evaluation, or does it stop after the first evaluation?

[@grant2024] ch. 2.4.1
[@webdev-viewport-units]
