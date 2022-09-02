## Version 1 (Unfinished)

This is the official specification listing all the IDs, and namespace attributes that the app looks for and/or apply effects to

---

<br />

### Metadata

_available only on the main `<svg>` element that parents the model's elements_

Attribute | Description | Default | Type
--- | --- | --- | ---
`mori:canvas-zoom` | controls big the model is compared to the canvas | `1` | Any number
`mori:tracking` | the type of tracking that the model utilizes | `face` | `face`, `experimental`
`mori:pose-sensitivity` | how accurate must Mori be to apply the detected pose to the model | `0.8` | `0` to `1`


<br />

### Rigging

to apply tracking to the model the app needs to know which elements correspond to which parts of the body.

This happens using the standard way by going and manually setting an `id` attribute to each element (or group). _Inkscape users can just rename the elements from the UI_


The following is a list of all available `id`(s), their children, and their attributes

ID | Type | Attributes
--- | --- | ---
`face` | Group | `mori:xpivot`, `mori:ypivot`
`left-arm` | Group | `mori:xpivot`, `mori:ypivot`
`right-arm` | Group | `mori:xpivot`, `mori:ypivot`


#### Face

ID | Type | Attributes
--- | --- | ---
`mouth` | Any | `mori:scale`, `mori:xerr`, `mori:yerr`
`left-eye` | Any | `mori:scale`, `mori:clippath`, `mori:xerr`, `mori:yerr`
`right-eye` | Any | `mori:scale`, `mori:clippath`, `mori:xerr`, `mori:yerr`
`left-eyebrow` | Any |`mori:scale`
`right-eyebrow` | Any | `mori:scale`
`left-iris` | Any | `mori:scale`
`right-iris` | Any | `mori:scale`

---

### Available Attributes

Attribute | Description | Default | Type
--- | --- | --- | ---
`mori:scale` | controls either the sensitivity of the effect or the scale of the object it self (depends on the element) | `1` | Any number
`mori:clippath` | don't allow overflow | `on` | `on` or `off`
`mori:xpivot`, `mori:ypivot` | indicate that a rotation can happen to the element and allow you to offset it's center | `0.015`, `0.03` | Any number
`mori:xerr`, `mori:yerr` | the allowed error level for point manipulation in 2d-axis | `0` | Any number
