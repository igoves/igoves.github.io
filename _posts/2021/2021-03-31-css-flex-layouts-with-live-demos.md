---
title: "CSS Flex Layouts With Live Demos"
date: "2021-03-31"
categories: 
  - "css"
tags: 
  - "flex"
  - "layout"
---

## Table of Contents

_Click to jump to each example._

[Flex cards on a touch device](#flex-cards-on-a-touch-device)

[Flex cards with equal height](#flex-cards-with-equal-height)

[Flex Cards with content-based height](#flex-cards-with-content-based-height)

[A flex card with content-controlled width](#a-flex-card-with-content-controlled-width)

[Centered flex cards](#centered-flex-cards)

[Plans and prices flex cards](#plans-and-prices-flex-cards)

[Three-column flex layout with two sidebars](#three-column-flex-layout-with-two-sidebars)

[Webpage flex layout with a Header, Content, and Footer](#webpage-flex-layout-with-a-header-content-and-footer)

[Webpage flex layout with a Header, Footer, and Sidebar](#webpage-flex-layout-with-a-header-footer-and-sidebar)

Display flex or flexbox is still the preferred way for building web grids and layouts in 2021 and is about to stay on top for quite some time. For that reason don’t feel doubtful about the evergreen demos and code samples below as they still serve very well when it comes to alignment and templating.

## Basic HTML structure

All examples share a similar HTML structure—one parent element (`.parent`) and several children (`.child`).

```html
<div class="parent">
  <div class="child">...</div>
  <div class="child">...</div>
  <div class="child">...</div>
  ...
</div>
```

_The HTML markup is also present for each flex demo for convenience._

## Flex Cards on a Touch Device

<iframe style="width: 100%;" title="Drop Last Item Full Width" src="https://codepen.io/moubi/embed/YzpZpVM?height=485&amp;theme-id=dark&amp;default-tab=result" height="485" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/YzpZpVM">Drop Last Item Full Width</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
  flex-wrap: wrap;}

.child {
  flex-grow: 1;
}

.child:last-child {
  width: 100%;}
```

HTML structure (_click to open_)

```html
<div class="parent">
  <div class="child">1</div>
  <div class="child">2</div>
  <div class="child">3</div>
</div>
```

This use case is derived from a common flex layout where three items are displayed on a single row. Then the last card can drop on the second one full-width (responsive) when using a mobile device or narrow screens. The central point in the code is around `flex-wrap: wrap` set to the parent and `width: 100%` set on the last child.

## Flex Cards with Equal Height

<iframe style="width: 100%;" title="Same Height, Same Width" src="https://codepen.io/moubi/embed/dyOvWgE?height=435&amp;theme-id=dark&amp;default-tab=result" height="435" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/dyOvWgE">Same Height, Same Width</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
  justify-content: space-between;
}

.child {
  flex-grow: 1;
  flex-basis: 0;
}
```

HTML structure (_click to open_)

```html
<div class="parent">
  <div class="child">
    It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.
  </div>
  <div class="child">Contrary to popular belief, Lorem Ipsum is not simply random text.</div>
  <div class="child">
    Lorem Ipsum is simply dummy text of the printing and typesetting industry.
  </div>
</div>
```

Similar to the previous flex demo you often need to display several cards on a single row with the same width and stretching their height to the tallest one. Just adding `display: flex` to the parent is enough to bring the stretch functionality in by default. For the flex items’ equal width you will need `flex-grow` and `flex-basis` too.

## Flex Cards with Content-based Height

<iframe style="width: 100%;" title="Flexbox Children with Auto Height" src="https://codepen.io/moubi/embed/poNPKpE?height=435&amp;theme-id=dark&amp;default-tab=result" height="435" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/poNPKpE">Flexbox Children with Auto Height</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
  align-items: flex-start;}

.child {
  flex-grow: 1;
  flex-basis: 0;
}
```

HTML structure (_click to open_)

```html
<div class="parent">
  <div class="child">
    It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.
  </div>
  <div class="child">Contrary to popular belief, Lorem Ipsum is not simply random text.</div>
  <div class="child">Lorem Ipsum is simply dummy text.</div>
</div>
```

The cards are forced to have their height automatically adjusted based on their content. Explicitly specifying `align-items: flex-start` ensures that. The equal width is achieved the same way as with the previous demo.

## A Flex Card with Content-controlled Width

<iframe style="width: 100%;" title="Flexbox Child with No Shrink" src="https://codepen.io/moubi/embed/OJbpgpg?height=295&amp;theme-id=dark&amp;default-tab=result" height="295" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/OJbpgpg">Flexbox Child with No Shrink</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
}

.child:last-child {
  flex-shrink: 0;}
```

HTML structure (_click to open_)

```html
<div class="parent">
  <div class="child">1</div>
  <div class="child">Lorem Ipsum is simply dummy print text.</div>
</div>
```

Often you need a flex card to have a fluid width but also another one aside with size that respects its content. Go to [this CSS flex demo example](https://codepen.io/moubi/pen/OJbpgpg) on CodePen and try to update the text and resize the screen. You will notice how the flex item on the right grows together with the text inside and doesn’t shrink even when the parent container goes too narrow. To apply the effect give `flex-shrink: 0` to that child—it is like saying _“Don’t shrink no matter what”_. By default, its value is `1`.

## Centered Flex Cards

<iframe style="width: 100%;" title="Flexbox Centered Items" src="https://codepen.io/moubi/embed/bGBvZmj?height=500&amp;theme-id=dark&amp;default-tab=result" height="500" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/bGBvZmj">Flexbox Centered Items</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
```

HTML structure (_click to open_)

```html
<div class="parent">
  <div class="child">1</div>
  <div class="child">2</div>
</div>
```

Having a centered image and text within a container both vertically and horizontally can be done by just applying some rules to the `.parent` alone. For this particular case, two cards are displayed in a column visually positioned in the middle of its wrapper. Don’t set `flex-direction: column` and you will have the same result with a row instead.

## Plans and Prices Flex Cards

<iframe style="width: 100%;" title="Flexbox Item Full Height" src="https://codepen.io/moubi/embed/yLVvXPm?height=500&amp;theme-id=dark&amp;default-tab=result" height="500" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/yLVvXPm">Flexbox Item Full Height</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
  align-items: center;
  height: 300px;  /* or whatever make sense */
}

.child {
  flex-grow: 1;
}

.child:nth-child(2) {
  align-self: stretch;}
```

HTML structure (_click to open_)

```html
<div class="parent">
  <div class="child">1</div>
  <div class="child">2</div>
  <div class="child">3</div>
</div>
```

A trivial flex grid for plans and prices section where the middle card is somehow bold. In the demo, all cards are vertically centered within their parent container and the middle one **expands to 100% height**. **Three steps to note for this flex example:** the parent needs a height set directly or indirectly together with vertically aligned items; `flex-grow: 1` for the `.child` elements so that they fill the horizontal space; and `align-self: stretch` for the middle card to fill the remaining vertical space.

## Three-column Flex Layout with Two Sidebars

<iframe style="width: 100%;" title="Flexbox Middle Item Stretch" src="https://codepen.io/moubi/embed/dyOmaow?height=400&amp;theme-id=dark&amp;default-tab=result" height="400" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/dyOmaow">Flexbox Middle Item Stretch</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
}

.child:nth-child(2) {
  flex-grow: 1;
}
```

HTML structure (_click to open_)

```html
<div class="parent">
  <div class="child">1</div>
  <div class="child">2</div>
  <div class="child">3</div>
</div>
```

CSS flex comes in very handy for webpage layouts. The current pen represents a grid with a content area and two sidebars on each side. The middle item (the content) should be wider so you can set `flex-grow: 1`. **In the production code, you may need to set an explicit width for the sidebars**.

## Webpage Flex Layout with a Header, Content, and Footer

<iframe style="width: 100%;" title="Flexbox Header, Body, Footer" src="https://codepen.io/moubi/embed/oNYEGGv?height=600&amp;theme-id=dark&amp;default-tab=result" height="600" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/oNYEGGv">Flexbox Header, Body, Footer</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
  flex-direction: column;
  height: 100vh;  /* or whatever make sense */
}

.child:nth-child(2) {
  flex-grow: 1;
}
```

HTML structure (_click to open_)

```html
<div class="parent">
  <div class="child">Header</div>
  <div class="child">Content</div>
  <div class="child">Footer</div>
</div>
```

A page layout with header, content, and footer sections is evergreen. You may look at it as the previous sidebars demo but on the flip side. The difference? Columns are now rows and the direction is changed to `flex-direction: column`. **Explicitly adding heights to the flex header and footer is OK**.

## Webpage Flex Layout with a Header, Footer, and Sidebar

<iframe style="width: 100%;" title="Flexbox Header, Sidebar, Content, Footer" src="https://codepen.io/moubi/embed/OJbQxGx?height=600&amp;theme-id=dark&amp;default-tab=result" height="600" frameborder="no" scrolling="no" allowfullscreen="allowfullscreen"><br /> See the Pen <a href="https://codepen.io/moubi/pen/OJbQxGx">Flexbox Header, Sidebar, Content, Footer</a> by Miroslav Nikolov<br /> (<a href="https://codepen.io/moubi">@moubi</a>) on <a href="https://codepen.io">CodePen</a>.<br /></iframe>

CSS Code

```css
.parent {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.main {
  display: flex;
  flex-grow: 1;
}

.content {
  flex-grow: 1;
}
```

HTML structure

```html
<div class="parent">
  <div class="child">Header</div>
  <div class="main">
    <div class="child">Sidebar</div>
    <div class="child content">Content</div>
  </div>
  <div class="child">Footer</div>
</div>
```

This page layout is a bit more complex and requires nested flexbox items. It can be built on top of the previous flex demo. The middle section (`.main`) is split into sidebar and content columns and represents a separate “parent” with `display: flex`. The `.content` area takes most of the space thanks to `flex-grow: 1`. **Setting an explicit width and height to those elements in the real use case is up to you**.
