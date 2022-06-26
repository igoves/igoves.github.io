---
title: "100 underline/overlay animations"
date: "2021-03-30"
categories: 
  - "css"
tags: 
  - "hover"
  - "underline"
---

- [The Basic](#the-basic)
- [The Continuous](#the-continuous)
- [The Double](#the-double)
- [The Two Steps](#the-two-steps)
- [The Unexpected](#the-unexpected)
- [The Rounded](#the-rounded)
- [The Fading](#the-fading)
- [The Infinite](#the-infinite)
- [The All Sides](#the-all-sides)
- [The Thick](#the-thick)
- [The Sliding](#the-sliding)
- [The Fancy](#the-fancy)
- [The Inverted](#the-inverted)
- [The 3D](#the-3d)

* * *

### [](#the-basic)The Basic

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/oNYOpBe?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

Few notes:

- `currentColor` will use the color defined inside `color`.
- I am using CSS variables to make the code shorter. `var(--d, 0)` means that the default value is `0` then I change it on hover.
- The syntax `0 100% /var(--d, 0) 3px` means `background-position / background-size`. We adjust the `3px` to control the height/thickness of the line.

### [](#the-continuous)The Continuous

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/KKNYZoK?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-double)The Double

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/OJbGzrG?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-two-steps)The Two Steps

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/XWNQZJa?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-unexpected)The Unexpected

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/vYyMdKP?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-rounded)The Rounded

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/LYbvQLX?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-fading)The Fading

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/QWGPQxp?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-infinite)The Infinite

Keep the hover for too long here.

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/QWGPQzg?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-all-sides)The All Sides

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/ZEBZxEj?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-thick)The Thick

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/KKNYoMo?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-sliding)The Sliding

The below requires us to know the width of the element so it's more suitable for monospace fonts where we can use the `ch` unit 

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/PobgRJj?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-fancy)The Fancy

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/BaQEVqz?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

(2) and (5) use some hardcoded values that need to be adjusted based on the element width

### [](#the-inverted)The Inverted

The below doesn't work on Firefox due to a [known bug](https://bugzilla.mozilla.org/show_bug.cgi?id=1571244)

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/YzpMvbz?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>

### [](#the-3d)The 3D

**Warning:** the below uses some advanced CSS but I considered CSS variables to make it easy to control

<iframe style="width: 100%;" src="https://codepen.io/t_afif/embed/YzpMjWy?height=600&amp;default-tab=result&amp;embed-version=2" height="600" frameborder="no" scrolling="no"></iframe>
