Neux Complete Guide
=============================

This markup page will notify important aspects of neux.css

#### Self intro:

##### Neumorphism is not a new deliverance in this project

The abstract of Neumorphism has been around for quite a time and UI designers have released many designing concepts on
multiple platforms like dribbble.com. Neux is inspired by patents and predecessors in frontend libraries and frameworks.

Colors, backgrounds and shadows
-------------------------------

The \_variables.scss file contains of 32 rgba color variables which includes 19 common Material colors and 13 Neu colors. The defined colors have their own respective text, background, shadow and border classes
excluding the `neu-tranparent`. The `neu-transparent`
can be seen used in minor events like `:disabled`.

Below you can see these colors as text shades and background colors.

![texts](imgs/texts.jpg)

![backgrounds](imgs/bgs.jpg)

![shadows](imgs/shadow1.jpg)

##### Note: Each background comes with a pre-written placeholder color.

Utilizing and adjusters Classes
-------------------------------

Many front-end frameworks and libraries include classes to utilize. Neux.css intends to let designers skip the curve of
creating responsive and adjustments. To achieve this goal, \_adjusters.scss and \_adjusters include:

1. Common display attributes like `.flex` and `.grid`
2. Couple of classes are written to contain the elements inside;
   `.container` and `.row`.

   `.row-firm` keeps the flexing direction at row on every device. However, in `.row-firm` the items' alignment is set to `stretch` while in `row` and `container` the items align in center. 

3. Two sets of column grid classes have been coded which work with containers and rows.

4. In addition to above, margin and padding adjusters are also available.

5. Also, up to 8 columns are written from `grid-template-columns` css attribute for `display: grid/ inline-grid`; e.g. `.grid-columns-3`.

### Margin classes:

##### Top margin:

`.mt0` `.mthalf` `.mt1` `.mt2` `.mt3` `.mt4` `.mt5`.

##### Right margin:

`.mr0` `.mrhalf` `.mr1` `.mr2` `.mr3` `.mr4` `.mr5`.

##### Bottom margin:

`.mb0` `.mbhalf` `.mb1` `.mb2` `.mb3` `.mb4` `.mb5`.

##### Left margin:

`.ml0` `.mlhalf` `.ml1` `.ml2` `.ml3` `.ml4` `.ml5`.

##### Horizontal margin:

`.mh0` `.mhhalf` `.mh1` `.mh2` `.mh3` `.mh4` `.mh5`.

##### Vertical margin:

`.mv0` `.mvhalf` `.mv1` `.mv2` `.mv3` `.mv4` `.mv5`.

##### All sides:

`.m0` `.mhalf` `.m1` `.m2` `.m3` `.m4` `.m5`.

### Padding classes:

same pattern as margin classes.

##### Top padding:

`.mt0` `.mthalf` `.mt1` `.mt2` `.mt3` `.mt4` `.mt5`
etc...

### Display and positioning

Common positioning values are turned into classes. `.fixed` `.relative` `.absolute` `.sticky`.

Common display values: `.block` `.flex` `.grid` `.inline-block` `.inline-flex` `.inline-grid`.

Top, bottom, left and right set as `0` have their classes respectively `.top` `.bottom` `.left` `.right`.

#### Class .row associated with class .col-n (n defers from 1 to 11)

If you want to take the whole width of the row with one column, use `.col-12`.

UPDATE:

3 sets of `.col-` classes have been added for specific viewport width ranges. To overwrite default `.col-` classes' behavior, a prefix is added to the class for each specific range.

1. Portrait tablets and large phones, etc.
```css
@media only screen and (min-width: 600px) and (max-width: 768px) {}
```

Use `.s-col-1`, `.s-col-2` to `.s-col-12`.  

2. Landscape tablets, etc.
```css
@media only screen and (min-width: 768px) and (max-width: 992px) {}
```

Use `.m-col-1`, `.m-col-2` to `.m-col-12`.

3. Laptops, desktops, etc.
```css
@media only screen and (min-width: 992px) and (max-width: 1200px) {}
```

Use `.l-col-1`, `.l-col-2` to `.l-col-12`.


```html
<div class="row-firm">
    <div class="col-3 small test-div bg-red">col-3</div>
    <div class="col-5 small test-div bg-blue-gray">col-3</div>
    <div class="col-2 small test-div bg-green">col-3</div>
</div>
```

![.row](imgs/row.jpg)

#### Class .grid associated with class grid-columns-n (n defers from 2 to 8)

Perfect combination for carousals. Provides a set of same-width-set columns with `1fr` gap. The columns created will break in lines on smaller screens.

![.grid](imgs/grid.jpg)

In addition to classes above, Rational number `p/q` based classes are available. 

1. `1/2` fraction. `.half`
   
2. `1/3` fraction. `.one-third` `.two-third`

3. `1/4` fraction. `.one-forth` `.three-fourth`

4. `1/5` fraction. `.one-fifth` `.two-fifth` `.three-fifth` `.four-fifth`

5. `1/6` fraction. `.one-sixth` `.five-sixth`

6. `1/7` fraction. `.one-seventh` `.two-seventh` `.three-seventh` `.four-seventh` `.five-seventh` `.six-seventh`

7. `1/8` fraction. `.one-eighth` `.three-eighth` `.five-eighth` `.seven-eighth`



Page Design; A New Approach...
------------------------------

### Panel

In Neumorphism, everything should sit on its parent rather than float over it. Like a controlling pad, you can see
buttons and items have the same background and coloring set. You are also able to see a prominence effect.

To achieve this visual, Neux has `panel`; a special class to contain your items inside and create the visual effect with
shadows. You can either choose a single background element and have panels inside or to have different panels with
different backgrounds which might be less popular in Neumorphism. Background classes have their own `.panel` class
individually. Also `.panel` is also co-written with every background class.

```html
<div class="container">
    <div class="bg-gray panel text-white">
        // your content
    </div>
</div>
```

or

```html
<div class="container bg-gray text-white">
    <div class="panel">
        // your content
    </div>
</div>
```

##### Note: Panel class does not provide side margins.

### The Convex and the Concave Effects

Neux has two visual effects in addition to default background and shadow effect. Same as `.panel`, each background class
has its own effects of concave and convex.

```html
<button class="concave" type="submit">SEND MESSAGE</button>
```

```html
<div class="panel bg-blue concave">
    // your content
</div>
```

```html
<div class="bg-neu-light container">
    <div class="panel convex">
        // your content
    </div>
</div>
```

##### image with class panel 

`.panel` is re-written for html `img` tag. If set, paddings will be removed, the border and the box-shadow will be set to `inherit`.

### Cards

The `.card` class represents a simple bordered element which its width is set as `auto`. This class comes with a simple
horizontal margin setup for `button` and `input` elements. and same as panel is co-written with backgrounds classes.

```html
<div class="container">
    // content
    <div class="bg-gray card">
        // card content
    </div>
</div>
```

or

```html
<div class="container bg-gray text-white">
    //content
    <div class="card">
        // card content
    </div>
</div>
```

The `.card-body` is for containing the text and input elements and provides a firm height and hides the overflow.

```html
<div class="card" style="">
    <img src="URL" alt="" class="">
    <div class="card-body">
        <h4 class="">Dan Diablo</h4>
        <p class="">CEO and Founder</p>
        <p class="">Phasellus eget enim eu lectus faucibus vestibulum. Suspendisse sodales pellentesque
            elementum.</p>
    </div>
    <button class="">Contact</button>
</div>
```

### Input, button and textarea elements

All disabled elements come with a single background set as `neu-transparent` value. The `:focus` event is set
for `input`, `button`, `textarea` for every background respectively.

`textarea` element is set to have a full width of its container.

```html
<div class="bg-neu-dark text-neu-light-gray panel">
    <h1>Form Preview</h1>
    <label for="" class="">Your Name</label>
    <input type="email" placeholder="Your Name...">
    <label for="" class="">Your Email</label>
    <input type="email" placeholder="Your Email...">
</div>
```

```html
<form>
    <input class="full-small" type="text" placeholder="Name" required name="Name">
    <input class="full-small" type="email" placeholder="E-mail" required name="email">
    <input class="full-small" type="text" placeholder="Subject" required name="Subject" value="">
    <textarea placeholder="Comment"></textarea>
    <button class="" type="submit">SEND MESSAGE</button>
```

`class="full-small"` sets the width of the input to `100%` on mobile devices.

Inside grid and flex
---------------------------------
`col-` and percentage based classes like `.one-third` have been mentioned above as well as `grid-colmun-` classes. More to that, aligning classes are available for `.grid` and `.flex`.

### flex-direction
`.flex-direction-row`

`.flex-direction-row-reverse`

`.flex-direction-column`

`.flex-direction-column-reverse`

### justify-content
`.justify-content-center`

`.justify-content-flex-end`

`.justify-content-flex-start`

`.justify-content-space-between`

`.justify-content-space-around`

`.justify-content-space-evenly`

### align-items
`.align-items-flex-start`

`.align-items-flex-end`

`.align-items-center`

`.align-items-stretch`

`.align-items-baseline`

### align-content
`.align-content-flex-start`

`.align-content-flex-end`

`.align-content-center`

`.align-content-stretch`

`.align-content-space-between`

`.align-content-space-around`

### align-self
`.align-self-center`

`.align-self-stretch`

`.align-self-flex-start`

`.align-self-flex-end`

`.align-self-baseline`

Text positioning
------------------
### text-align
`.text-align-justify`

`.text-align-center`

`.text-align-right`

`.text-align-left`


Borders
------------------
`.border` sets the style of your border to `solid`. Use this class alongside border width, radius and color classes given below.

#### Width
5 sets of border width classes are available. The unit is in `px` and the value differs from `1` to `5`.

1. Top: `.bt1`, `.bt2`, `.bt3`, `.bt4`, `.bt5`
2. Bottom: `.bb1`, `.bb2`, `.bb3`, `.bb4`, `.bb5`
3. Left: `.bl1`, `.bl2`, `.bl3`, `.bl4`, `.bl5`
4. Right: `.br1`, `.br2`, `.br3`, `.br4`, `.br5`
5. All sides: `.bt1`, `.bt2`, `.bt3`, `.bt4`, `.bt5`

#### Colors

Top, right, bottom, left and all sides border colors have turned into classes. For all sides use: `.border-{COLORNAME}` and for sides; use:  

`.border-top-{COLORNAME}`

`.border-right-{COLORNAME}`

`.border-left-{COLORNAME}` 

`.border-bottom-{COLORNAME}`

#### Radius
`.sharp` sets the radius equal to `0`.
`.smooth` sets the radius equal to `12px`.
`.bordered` sets the radius equal to `30px`.
`.rounded` sets the radius equal to `50%`.

Also corners' radius can be set separately.

`sharp-top-right`

`sharp-top-left`

`sharp-bottom-right`

`sharp-bottom-left`

`smooth-top-right`

`smooth-top-left`

`smooth-bottom-right`

`smooth-bottom-left`

`bordered-top-right`

`bordered-top-left`

`bordered-bottom-right`

`bordered-bottom-left`

`rounded-top-right`

`rounded-top-left`

`rounded-bottom-right`

`rounded-bottom-left`

The Carousel Effect
---------------------
The carousel or merry go around effect lets you to display the content in a slidable row. It creates 100 columns in a grid view and hides the elements horizontal scrollbar.
 
`.carousel`: The default mode where each column is set to `320px` width.

`.carousel-150`: Each column is set to `150px` width.

`.carousel-200`: Each column is set to `200px` width.

`.carousel-250`: Each column is set to `250px` width.

`.carousel-300`: Each column is set to `300px` width.

`.carousel-350`: Each column is set to `350px` width.

`.carousel-400`: Each column is set to `400px` width.

`.carousel-450`: Each column is set to `450px` width.


#### Shout outs

Amazing designers at [Dribble](http://dribbble.com/)

[Neumorphism.io](http://neumorphism.io/)

[Michal Malewicz on uxdesign](https://uxdesign.cc/neumorphism-in-user-interfaces-b47cef3bf3a6)

[UI Design and Prototyping on JustinMind](https://www.justinmind.com/blog/neumorphism-ui/)

[Adrian Bece on css-tricks](https://css-tricks.com/neumorphism-and-css/)