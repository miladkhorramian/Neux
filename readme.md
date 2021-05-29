Neux Complete Guide
=============================

This markup page will notify important aspects of neux.css

#### Self intro:

##### Neumorphism is not a new deliverance in this project

The abstract of Neumorphism has been around for quite a time and UI designers have released many designing concepts on
multiple platforms like dribbble.com. Neux is inspired by patents and predecessors in frontend libraries and frameworks.

Colors, backgrounds and shadows
-------------------------------

The \_variables.scss file contains of 32 rgba color variables which includes 19 common Material colors and 13 Neu colors
that were extracted through experience. The defined colors have their own respective text, background and shadow classes
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

   `.row-firm` keeps the flexing direction at row on every device.


3. Two sets of column grid classes have been coded which work with containers and rows.


4. In addition to above, margin and padding adjusters are also available: `0`, `.5rem`, `1rem`, `2rem`, `3rem`, `4rem`
   , `5rem`.

5. Also, up to 8 columns are written from `grid-template-columns` css attribute for `display: grid/ inline-grid`

   e.g. `.grid-columns-3`.

### Margin classes:

##### Top margin:

`.mt-0`, `.mt-half`, `.mt-1`, `.mt-2`, `.mt-3`, `.mt-4`, `.mt-5`.

##### Right margin:

`.mr-0`, `.mr-half`, `.mr-1`, `.mr-2`, `.mr-3`, `.mr-4`, `.mr-5`.

##### Bottom margin:

`.mb-0`, `.mb-half`, `.mb-1`, `.mb-2`, `.mb-3`, `.mb-4`, `.mb-5`.

##### Left margin:

`.ml-0`, `.ml-half`, `.ml-1`, `.ml-2`, `.ml-3`, `.ml-4`, `.ml-5`.

##### Horizontal margin:

`.mh-0`, `.mh-half`, `.mh-1`, `.mh-2`, `.mh-3`, `.mh-4`, `.mh-5`.

##### Vertical margin:

`.mv-0`, `.mv-half`, `.mv-1`, `.mv-2`, `.mv-3`, `.mv-4`, `.mv-5`.

##### All sides:

`.m-0`, `.m-half`, `.m-1`, `.m-2`, `.m-3`, `.m-4`, `.m-5`.

### Padding classes:

same pattern as margin classes.

##### Top padding:

`.mt-0`, `.mt-half`, `.mt-1`, `.mt-2`, `.mt-3`, `.mt-4`, `.mt-5`.

### Display and positioning

Common positioning values are turned into classes. `.fixed`, `.relative`, `.absolute`, `.sticky`.

Common display values: `.block`, `.flex` `.grid`, `.inline-block`, `.inline-flex`, `.inline-grid`.

Top, bottom, left and right set as `0` have their classes respectively `.top`, `.bottom`, `.left`, `.right`.

#### Class .row associated with class .col-n (n defers from 1 to 11)

If you want to take the whole width of the row with one column, use `.col-12`.

By default, each column is responsive but if you intend to keep the layout, after each column class, use `.small`.

```html
<div class="row-firm mt-1">
    <div class="col-3 small test-div bg-red">col-3</div>
    <div class="col-5 small test-div bg-blue-gray">col-3</div>
    <div class="col-2 small test-div bg-green">col-3</div>
</div>
```

![.row](imgs/row.jpg)

#### Class .grid associated with class grid-columns-n (n defers from 2 to 8)

Perfect combination for carousals. Provides a set of same-width-set columns with a `fr` gap.

![.grid](imgs/grid.jpg)

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

#### Shout outs

Amazing designers at [Dribble](http://dribbble.com/)

[Neumorphism.io](http://neumorphism.io/)

[Michal Malewicz on uxdesign](https://uxdesign.cc/neumorphism-in-user-interfaces-b47cef3bf3a6)

[UI Design and Prototyping on JustinMind](https://www.justinmind.com/blog/neumorphism-ui/)

[Adrian Bece on css-tricks](https://css-tricks.com/neumorphism-and-css/)