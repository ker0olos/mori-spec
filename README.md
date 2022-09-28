## Version 1 (Unfinished)

```
#### Mori is an unreleased software, still under development.
#### ¯\_(ツ)_/¯
```

This is the official specification listing all the IDs, and namespace attributes that the app looks for and apply effects on.

---

<br />

### Metadata

_Available on the main `<svg>` element that parents the model._

Attribute | Description | Default | Type
--- | --- | --- | ---
`mori:canvas-zoom` | controls how big the model is compared to the canvas | `1` | Any number
`mori:tracking` | the type of tracking that the model utilizes | `face` | `face`, `experimental`
`mori:pose-sensitivity` | how accurate must the app be to apply the detected pose to the model | `0.8` | `0` to `1`


<br />

### Rigging

To apply tracking to the model the app needs to know which elements correspond to which parts of the body.

This happens using the standard way by going and manually setting an `id` attribute to each element (or group). _Inkscape users can rename the elements from the UI_.


The following is a list of all available `id`(s), their children, and their attributes.

ID | Type | Optional Attributes
--- | --- | ---
`face` | [Group](#face) | `mori:xpivot`, `mori:ypivot`

#### Face

ID | Type | Optional Attributes
--- | --- | ---
`mouth` | Any | `mori:scale`
`left-eye` | Any | `mori:scale`, `mori:clippath`
`right-eye` | Any | `mori:scale`, `mori:clippath`
`left-eyebrow` | Any |`mori:scale`
`right-eyebrow` | Any | `mori:scale`
`left-iris` | Any | `mori:scale`
`right-iris` | Any | `mori:scale`

---

### Available Attributes

Attribute | Description | Default | Type
--- | --- | --- | ---
`mori:scale` | controls the sensitivity of the effects compered to the size of the element | `1` | Any number
`mori:clippath` | don't allow overflow | `on` | `on` or `off`
`mori:xpivot`, `mori:ypivot` | indicate that a rotation can happen to the element and allow you to offset it's center | `0.015`, `0.03` | Any number
