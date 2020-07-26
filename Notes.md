# This is my notes for HTML CSS

## 4. Intermediate HTML 5 & Intermediate CSS 3

1. ### The Box Model

   Each element in CSS is represented as a rectangular box, and is described using the standard box model. The arrangement is from inside out as listed down below.

   The standard box model consists of four main parts:

   1. content
   1. padding
   1. border
   1. margin

   In order for an element to be represented as a box it has to be a block level element.

   1. <h4 id="margin">Margin</h4>
      Margin has four sides:

      1. top
      1. right
      1. bottom
      1. left

   They can be accessed using `margin: 10px 20px 30px 40px`. Take note that these values each refer to one of the sides and the arrangement is as listed above.</br>
   Another way to access these values is when top and bottom, right and left (opposite sides) have the same values. You can access them like this : `margin: 10px 20px`. In this example Top and Bottom will have value of 10px and Right and Left will have value of 20px.

   Take note that these value manipulations also carry over to _**padding**_ as well but not ~~border~~.

   They can also be called directly for manipulation using their names :

   1. `margin-top:`
   1. `margin-right:`
   1. `margin-bottom:`
   1. `margin-left:`

   Take note that these naming conventions are also carried over to _**padding and border**_ as well.

   1. #### Padding

      Padding is the same as margin explained above.

   1. #### Border

      Border has four sides:
   1. top
   1. right
   1. bottom
   1. left

   They can also be called directly for manipulation using their names :

   1. `border-top:`
   1. `border-right:`
   1. `border-bottom:`
   1. `border-left:`

   Border is defined like this : </br> `border: <size> <border-style> <color>`

   - size: size's value is like anything else in CSS and can be either of these :
     - px
     - em
     - rem
     - %
   - border-style: there are many border styles just to name a few :

     1. dotted
     1. dashed
     1. solid
     1. double
     1. groove
     1. ridge
     1. inset
     1. outset
     1. none(no border)
     1. hidden(just as the name implies it is hidden)
     1. dotted dashed solid double

   The last one makes the border's of each side different like the size of <a href="#margin">margin</a> for different sides.

   - color: set's borders color.

   1. #### Content

      Content is what the box or block level element contains(text or other elements).

2. ### Border Radius

   Border radius determines the roundness of the four corners. They can be called with : `border-radius: <value>` and the value can be either of :

   - px
   - em
   - rem
   - % (When % is selected it will be the % of the width of the border e.g. if the width of the border is 100 then 10% border-radius will be 10px)

   Also you can set different border-radius for each corner similar to the <a href="margin">margin</a> part where the first value determines the top left corner and then it moves clockwise so the last one will be the bottom left corner.</br>
   The same goes for calling 2 values in which the first value is the top left corner and the corner across the diameter which is bottom right corner and the second value is the other two corners which is top right corner and bottom left corner.

   The border will by default set the same value for horizontal and vertical values but you can decide them yourself with declaring values like this : </br>
   `border-radius : <horizontal-value>/<vertical-value>`</br>
   `border-radius : 15px/40px`

3. ### Box Shadow

   Adds shadow effects around an element's frame and it is defined by it's horizontal and vertical axis. It can receive inputs values of :

   - px
   - em
   - rem
   - ~~%~~(no % for box shadow)

   The configuration is : `box-shadow: <optional-option> <horizontal-value> <vertical-value> <shade-value> <spread-value> <color>`

   It needs at minimum 2 values and the first 2 values can also be negative :
   `box-shadow: 20px 20px` or `box-shadow: -20px -20px` and the `<spread-value>` can be negative as well but the not the ~~`<shade-value>`~~.</br>
   But by default it's color is the same as the content so we must specify a color value as well if the color of our content is the same as the background color :</br>
   `box-shadow: 20px 20px black`</br>
   You can use rgba for colors and give it opacity. So you can use the shade-value and rgba at the same time.

   If you want to make the shadow go inward in tho the box you can use :</br> `box-shadow: inset <the-rest-is-the-same-as-above>`</br>
   Take note that in this case the shadow will always be behind the content of the box.

   You can also have more than one shadow for a box : </br>
   `box-shadow: <optional-option> <horizontal-value> <vertical-value> <shade-value> <spread-value> <color>, <optional-option> <horizontal-value> <vertical-value> <shade-value> <spread-value> <color>` </br>
   For example : `box-shadow: 20px 20px 5px 10px black, inset -20px -20px 5px 10px red;`

4. ### Advanced selectors

   There are 2 main advanced selectors : </br>

   - pseudo-elements : style a specific part of the selected element(s).
   - pseudo-classes : specifies a special state of the selected element(s).

5. ### !important

   It means that "this is important" and the setting marked by it will not change.</br>
   example : `element { color: blue !important}`
   If 2 !important are called at the same time from different places and they conflict each other the most specific one will take effect. For example if I set the color red for all the texts in `* {color: red !important}` then I set all the paragraphs to black `p {color: black !important}` then the paragraphs will turn black because the p modifier is more specific than \* modifier.</br>
   It can also directly change the `<html>` element like `background-color`.

6. ### pseudo-classes

   - :root
   - :hover
   - :focus
   - :enabled/disabled
   - :checked
   - :first-child
   - :nth-chil
   - :last-child

   #### Root

   This pseudo-class is like a container which targets the highest level "parent" element in the DOM, or the document tree. So basically it targets `<html>` element and it can also hold variables for general purposes like making a color and then reusing it everywhere and if you decided to change it you just have to change that variables value. It also has **_higher specificity_**. Pseudo-class selectors (but not pseudo-elements) have a specificity equal to that of a class, which is higher than a basic element selector.</br>It can be used like this: `root: {--success-color: #2aaa50}` then it can be called elsewhere in the CSS file in color sections using: `<color-attribute>: color: var(--success-color)`.

   #### Hover

   This pseudo-class happens when a user hovers over a function but doesn't necessarily activate it. You can give hover class to anything in CSS. It is not standalone and has to accompany another element or attribute.</br>
   It can be accessed like this: `<element-or-attribute>:hover{<options>}`

   #### Focus

   As the name suggests this pseudo-class makes the browser focus on something. It's a generated figure user clicks or tabs or selects using the keyboards tab key. It is not standalone and has to accompany another element or attribute.</br>
   It can be accessed like this: `<element-or-attribute>:focus{<options>}`

   #### Enabled and Disabled

   It is any element that can be selected or disabled or focused on. Disabled is the opposite of enabled so It is any element that can be selected or enabled or focused on.

   #### Checked

   It represents any radio button or checked box or select list with options which can be checked or unchecked.