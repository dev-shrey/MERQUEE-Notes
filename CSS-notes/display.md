# CSS DISPLAY PROPERTY COMPLETE DOCUMENTATION

## Introduction

The `display` property is one of the most important CSS properties.

It controls how an HTML element is displayed on a webpage and how it interacts with other elements around it.

Almost every layout in CSS depends on the display property.

### Syntax

```css
selector{
    display:value;
}
```

Common values:

```css
display:block;
display:inline;
display:inline-block;
display:none;
```

---

# Why Do We Need Display?

Every HTML element has a default display behavior.

For example:

* `<div>` is block by default.
* `<span>` is inline by default.
* `<img>` is inline-block by default.

Sometimes the default behavior is not suitable for our design.

The display property allows us to change that behavior.

---

# 1. display: block

A block element always starts on a new line and takes the full width available.

### Syntax

```css
div{
    display:block;
}
```

### Characteristics

✔ Starts on a new line

✔ Takes full available width

✔ Width works

✔ Height works

✔ Margin works

✔ Padding works

### Common Block Elements

```html
<div></div>
<p></p>
<h1></h1>
<h2></h2>
<section></section>
<article></article>
```

### Example

```html
<div>HTML</div>
<div>CSS</div>
<div>JavaScript</div>
```

Output:

```text
HTML
CSS
JavaScript
```

Each element starts on a new line.

### Real Life Example

Imagine students sitting on separate benches.

```text
Bench 1 -> HTML

Bench 2 -> CSS

Bench 3 -> JavaScript
```

Each student gets an entire bench.

---

# 2. display: inline

An inline element stays in the same line and only takes the width required by its content.

### Syntax

```css
span{
    display:inline;
}
```

### Characteristics

✔ Stays on the same line

✔ Takes only content width

✔ Left and right padding works

✔ Left and right margin works

✘ Width does not work

✘ Height does not work

✘ Top and bottom margins do not affect layout as expected

### Common Inline Elements

```html
<span></span>
<a></a>
<strong></strong>
<em></em>
```

### Example

```html
<span>HTML</span>
<span>CSS</span>
<span>JavaScript</span>
```

Output:

```text
HTML CSS JavaScript
```

All elements remain on the same line.

### Width Example

```css
span{
    width:200px;
}
```

The width will not apply because inline elements ignore width and height.

### Real Life Example

Imagine three friends sitting on the same bench.

```text
HTML CSS JavaScript
```

Each friend occupies only the space they need.

---

# 3. display: inline-block

Inline-block combines the behavior of both inline and block elements.

### Syntax

```css
div{
    display:inline-block;
}
```

### Characteristics

✔ Stays on the same line

✔ Width works

✔ Height works

✔ Margin works

✔ Padding works

✔ Can sit beside other elements

### Example

```html
<div>HTML</div>
<div>CSS</div>
<div>JavaScript</div>
```

```css
div{
    display:inline-block;
    width:100px;
    height:100px;
}
```

Output:

```text
[HTML] [CSS] [JavaScript]
```

All elements remain on the same line while respecting width and height.

### Real Life Example

Imagine shops in a market.

```text
[Shop 1] [Shop 2] [Shop 3]
```

Each shop has its own fixed size but stands beside other shops.

---

# 4. display: none

The element is completely removed from the webpage.

### Syntax

```css
div{
    display:none;
}
```

### Characteristics

✔ Element becomes invisible

✔ No space is reserved

✔ Element is removed from normal document flow

✔ Other elements move into its place

### Example

```html
<div>HTML</div>
<div class="hide">CSS</div>
<div>JavaScript</div>
```

```css
.hide{
    display:none;
}
```

Output:

```text
HTML
JavaScript
```

The CSS element disappears completely.

### Real Life Example

Imagine removing a chair from a room.

```text
Before:

Chair 1
Chair 2
Chair 3

After removing Chair 2:

Chair 1
Chair 3
```

The removed chair occupies no space.

---

# display:none vs visibility:hidden

Many beginners confuse these two properties.

## display:none

```css
display:none;
```

Output:

```text
HTML     JavaScript
```

The element is removed completely.

---

## visibility:hidden

```css
visibility:hidden;
```

Output:

```text
HTML          JavaScript
```

The element becomes invisible but its space remains reserved.

### Real Life Example

display:none

Chair removed from room.

visibility:hidden

Chair covered with an invisible cloth.

The chair still occupies space.

---

# Block vs Inline vs Inline-Block

| Property         | Block | Inline  | Inline-Block |
| ---------------- | ----- | ------- | ------------ |
| Starts New Line  | Yes   | No      | No           |
| Width Works      | Yes   | No      | Yes          |
| Height Works     | Yes   | No      | Yes          |
| Margin Works     | Yes   | Partial | Yes          |
| Padding Works    | Yes   | Partial | Yes          |
| Takes Full Width | Yes   | No      | No           |

---

# Visual Comparison

## Block

```text
HTML
CSS
JavaScript
```

---

## Inline

```text
HTML CSS JavaScript
```

---

## Inline-Block

```text
[HTML] [CSS] [JavaScript]
```

---

# Common Interview Questions

## Q1. What is the default display value of a div?

Answer:

```css
display:block;
```

---

## Q2. What is the default display value of a span?

Answer:

```css
display:inline;
```

---

## Q3. Why does width not work on inline elements?

Answer:

Because inline elements only occupy the space required by their content and ignore width and height properties.

---

## Q4. Difference between inline and inline-block?

| Inline               | Inline-Block         |
| -------------------- | -------------------- |
| Width does not work  | Width works          |
| Height does not work | Height works         |
| Content width only   | Custom size possible |

---

## Q5. Difference between display:none and visibility:hidden?

display:none

* Hidden
* No space occupied

visibility:hidden

* Hidden
* Space still occupied

---

# Summary

## display:block

```css
display:block;
```

* Starts on a new line
* Takes full width
* Width and height work

---

## display:inline

```css
display:inline;
```

* Stays on same line
* Width and height do not work
* Uses content width

---

## display:inline-block

```css
display:inline-block;
```

* Stays on same line
* Width and height work
* Combines inline and block behavior

---

## display:none

```css
display:none;
```

* Completely hides element
* Removes element from layout
* No space reserved

---
