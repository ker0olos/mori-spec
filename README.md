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
`left-eye` | Any | `mori:scale`
`right-eye` | Any | `mori:scale`
`left-eyebrow` | Any |`mori:scale`
`right-eyebrow` | Any | `mori:scale`
`left-iris` | Any | `mori:scale`
`right-iris` | Any | `mori:scale`

---

### Available Attributes

Attribute | Description | Default | Type
--- | --- | --- | ---
`mori:scale` | controls the sensitivity of the effects compered to the size of the element | `1` | Any number
`mori:xpivot`, `mori:ypivot` | indicate that a rotation can happen to the element and allow you to offset it's center | `0.015`, `0.03` | Any number

---

### Keyframes

Keyframes are how mori does rotations.

Mori transitions from one keyframe (degree) to the other. If a degree is missing. The value is calclauted based on the missing degree and the next available degree.

Keyframes are currently only being used for head rotations. Adding custom keyframes to `#face` will override or help guide the rotation in the right direction.

Attribute | Description | Type
--- | --- | --- | ---
`mori:keyframe-href` | the id of the element that the keyframe is being attached to | `#face`
`mori:keyframe-deg` | the degree of the keyframe | `0` -> `360`


