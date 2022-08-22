# Resets
Here's [Eric Meyer's reset](https://meyerweb.com/eric/tools/css/reset/).
# Selectors
There are three main selector types:

**Type selectors**
```css
div
p
span
```
**Class selectors**
```css
.myclass
```
**And id selectors**
```css
#myid
```
Aditionally, there are **combined selectors**
```css
section cls1 p.cls2 span#id1
```
And **universal selectors**
```css
*
```
In the above case, the only elements being affected would be `<span>`s with an id of `id1` that are within a `<p>` with a class of `cls2` that are within any element with the `cls1` class that are in any `<section>`. E.g.
```html
<section>
    <div class="cls1">
        <p class="cls2"> Some<span id="id1">thing</span></p>
    </div>
</section>
```
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
{
    font-size: 10px;
}
```
**Relative** lengths can be represented in a few different ways:

**Percentage**
```css
{
    width: 50%;
}
```
**Em**, which is a unit equivalent to the element's font size
```css
{
    font-size : 14px;
    width     : 5em;
}
```
In the above case, `5em` would be equavlent to `70px`.

# Box Model
**Sides**
1. `top`
2. `right`
3. `bottom`
4. `left`

**Corners**
1. `top-right`
2. `bottom-right`
3. `bottom-left`
4. `top-left`

**Border styles**
1. `solid`
2. `dotted`
3. `dashed`
4. `outset`
5. `inset`
6. `groove`
7. `double`
8. `ridge`

*detailed information on borders can be found [here](https://www.quackit.com/html/codes/html_borders.cfm)*

**Width & Height**
```css
{
    width  : <len>;
    height : <len>;
}
```
**Margins & Padding**

*`margin` can simply be replaced with `padding` in any of the below examples; they have the same value syntax. Additionally, `auto` can be used in place of any length, in which case the browser will decide a suitable margin to use.*
```css
{
    margin        : <top_right_bottom_left_len>;
    margin        : <top_bottom_len> <left_right_len>;
    margin        : <top_len> <right_len> <bottom_len> <left_len>;
    margin-<side> : <len>;
}
```
**Borders**
```css
{
    border                 : <len> <style> <color>;
    border-<side>          : <len> <style> <color>;
    
    border-style           : <style>
    border-style           : <top_bottom_style> <left_right_style>;
    border-style           : <top_style> <right_style> <bottom_style> <left_style>;
    border-<side>-style    : <style>
    
    border-color           : <color>
    border-color           : <top_bottom_color> <left_right_color>;
    border-style           : <top_color> <right_color> <bottom_color> <left_color>;
    border-<side>-color    : <color>

    border-width           : <len>;
    border-width           : <top_bottom_len> <left_right_len>;
    border-width           : <top_len> <right_len> <bottom_len> <left_len>;
    border-<side>-width    : <width>

    border-radius          : <radius>
    border-radius          : <topleft_bottomright_len> <topright_bottomleft_len>;
    border-radius          : <topleft_len> <topright_len> <bottomright_len> <bottomleft_len>;
    border-<corner>-radius : <len>
}
```
**Box sizing**
```css
{
    -webkit-box-sizing: <content-box|padding-box|border-box> /* Chrome and Safari */
       -moz-box-sizing: <content-box|padding-box|border-box> /* Firefox */
        -ms-box-sizing: <content-box|padding-box|border-box> /* Internet Explorer */
            box-sizing: <content-box|padding-box|border-box>
}
```
- `content-box`
    The default box sizing.
- `padding-box`
    Includes padding within the width/height. Should not be used.
- `border-box`
    Includes the border and padding within the width/height. Generally the best option, as it makes calculations a bit easier (if we want our element to be 400 pixels wide, it will remain 400 pixels wide no matter our border or padding sizes).
# Pseudo Elements & Classes
A pseudo-element is a keyword added to a selector that lets you style specific parts of the elements. A list of all pseudo-elements and what they do can be found [here](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements). For example, the below would only apply styling to the first letter of every paragraph tag.
```css
p::first-letter
```
It's also important to note that only one pseudo-element may be used in a selector. For example, the below would not work:
```css
div::after::first-letter
```
A pseudo-class is a keyword added to a selector that lets you style depending on a specific state of the element. For example, only to hyperlinks that have already been visited by the user:
```css
a:visited
```
More information on pseudo-classes can be found [here](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes).
