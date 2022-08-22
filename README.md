# Resets
Here's [Eric Meyer's reset](https://meyerweb.com/eric/tools/css/reset/).
# Selectors
There are three main selector types:

**Type selectors**
```css
div {}
p {}
span {}
```
**Class selectors**
```css
.myclass {}
```
**And id selectors**
```css
#myid {}
```
Aditionally, there are **combined selectors**
```css
section cls1 p.cls2 span#id1 {}
```
In the above case, the only elements being affected would be `<span>`s with an id of `id1` that are within a `<p>` with a class of `cls2` that are within any element with the `cls1` class that are in any `<section>`.

Id selectors take precendence over class selectors during styling conflicts, and similarly, class selectors take precendence over type selectors. Combined selectors other selectors depending on their specificity weight (`idsI`-`classesI`-`typesI`). In the above combined example, it would have a specificity weight of `1-2-3` (1 id, 2 classes, 3 types).

# Colors
There are a few types of color values that can be used:
1. keyword : `black`, `orange`, `maroon`, more can be found within the [CSS specification](https://www.w3.org/TR/css-color-3/)
2. hex     : `#f84e0a`
3. RGB     : `rgb(rI0:255, gI0:255, bI0:255)`
4. RGBa    : `rgba(rI0:255, gI0:255, bI0:255, aF0:1)`
5. HSL     : `hsl(hN0:360, sP, lP)`
6. HSLa    : `hsla(hN0:360, sP, lP, aF0:1)`

# Lengths
There are two main ways to represent length: **absolute** and **relative**.

**Absolute** lengths are measured in pixels (1/96th of an inch)
```css
{ font-size: 10px; }
```
**Relative** lengths can be represented in a few different ways:

**Percentage**
```css
{ width: 50%; }
```
**Em**, which is a unit equivalent to the element's font size
```css
{ font-size: 14px; width: 5em;}
```
In the above case, `5em` would be equavlent to `70px`.
