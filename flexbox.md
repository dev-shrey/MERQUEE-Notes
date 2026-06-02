# CSS FLEXBOX COMPLETE DOCUMENTATION

## What is Flexbox?

Flexbox (Flexible Box Layout) is a one-dimensional CSS layout system used to arrange, align, and distribute space among elements inside a container.

Flexbox is designed to make layouts responsive and easier to manage compared to older techniques such as floats and inline-block layouts.

Flexbox can control layout in:

* Row Direction (Horizontal)
* Column Direction (Vertical)

---

# Why Do We Need Flexbox?

Before Flexbox:

* Block elements stacked vertically.
* Inline elements offered limited layout control.
* Centering elements was difficult.
* Equal spacing required extra calculations.
* Responsive layouts were harder to create.

Flexbox solves these problems by giving the parent element control over how its child elements are arranged.

---

# Flex Container and Flex Items

## Flex Container

A flex container is the parent element on which `display: flex` or `display: inline-flex` is applied.

```html
<div class="container">
    <div class="box">1</div>
    <div class="box">2</div>
    <div class="box">3</div>
</div>
```

```css
.container{
    display:flex;
}
```

---

## Flex Items

The direct children of a flex container become flex items.

```html
<div class="box">1</div>
<div class="box">2</div>
<div class="box">3</div>
```

When `display:flex` is applied:

* Children become Flex Items.
* Normal block layout rules are replaced by Flexbox rules.

---

# Real Life Example

Imagine a bookshelf.

* Bookshelf = Flex Container
* Books = Flex Items

The bookshelf controls:

* Arrangement of books
* Alignment of books
* Space between books
* Distribution of available space

---

# Main Axis and Cross Axis

Every Flexbox layout is based on two axes.

## Main Axis

The direction in which flex items are placed.

## Cross Axis

The direction perpendicular to the Main Axis.

---

## Row Direction

```css
.container{
    flex-direction:row;
}
```

```text
Main Axis  →

[1] [2] [3]

Cross Axis ↓
```

---

## Column Direction

```css
.container{
    flex-direction:column;
}
```

```text
[1]
[2]
[3]

Main Axis ↓

Cross Axis →
```

---

# Golden Rule

```text
justify-content
↓
Main Axis

align-items
↓
Cross Axis

align-content
↓
Flex Lines

align-self
↓
Individual Flex Item
```

---

# Flex Container Properties

These properties are applied to the parent element.

---

# 1. display:flex

Creates a flex container.

```css
.container{
    display:flex;
}
```

Before:

```text
1
2
3
```

After:

```text
1 2 3
```

### Real Life Example

Students standing one below another are asked to stand in a single line.

---

# 2. display:inline-flex

Creates a flex container that behaves like an inline element.

```css
.container{
    display:inline-flex;
}
```

### Difference

| display:flex     | display:inline-flex  |
| ---------------- | -------------------- |
| Block Level      | Inline Level         |
| Takes Full Width | Takes Required Width |

---

# 3. flex-direction

Defines the direction of the Main Axis.

## row

```css
flex-direction:row;
```

Output:

```text
1 2 3
```

---

## row-reverse

```css
flex-direction:row-reverse;
```

Output:

```text
3 2 1
```

---

## column

```css
flex-direction:column;
```

Output:

```text
1
2
3
```

---

## column-reverse

```css
flex-direction:column-reverse;
```

Output:

```text
3
2
1
```

---

# 4. justify-content

Aligns items along the Main Axis.

## flex-start

```css
justify-content:flex-start;
```

```text
1 2 3
```

---

## center

```css
justify-content:center;
```

```text
      1 2 3
```

---

## flex-end

```css
justify-content:flex-end;
```

```text
            1 2 3
```

---

## space-between

```css
justify-content:space-between;
```

```text
1      2      3
```

---

## space-around

```css
justify-content:space-around;
```

```text
 1    2    3
```

---

## space-evenly

```css
justify-content:space-evenly;
```

```text
   1   2   3
```

### Real Life Example

Three friends sitting on a bench.

justify-content controls how available space is distributed between them.

---

# 5. align-items

Aligns items along the Cross Axis.

## flex-start

```css
align-items:flex-start;
```

Items move to the start.

---

## center

```css
align-items:center;
```

Items move to the center.

---

## flex-end

```css
align-items:flex-end;
```

Items move to the end.

---

## stretch

```css
align-items:stretch;
```

Items stretch to fill available height.

---

## baseline

```css
align-items:baseline;
```

Aligns text baselines instead of box boundaries.

### Real Life Example

People standing inside an elevator.

align-items decides whether they stand at the top, center, or bottom.

---

# 6. flex-wrap

Controls whether items stay on a single line or move to the next line.

## nowrap

```css
flex-wrap:nowrap;
```

Default value.

Items remain on a single line.

---

## wrap

```css
flex-wrap:wrap;
```

Items move to the next line when space is insufficient.

---

## wrap-reverse

```css
flex-wrap:wrap-reverse;
```

Items wrap in reverse direction.

### Real Life Example

Books on a shelf.

When one shelf is full, books move to the next shelf.

---

# 7. align-content

Controls alignment of multiple flex lines.

Works only when:

```css
flex-wrap:wrap;
```

AND

* Multiple flex lines exist.
* Extra space exists on the Cross Axis.

---

## Values

```css
align-content:flex-start;
align-content:center;
align-content:flex-end;
align-content:space-between;
align-content:space-around;
align-content:space-evenly;
align-content:stretch;
```

### Real Life Example

Classroom seating.

* align-items controls students inside rows.
* align-content controls entire rows.

---

# 8. flex-flow

Shorthand for:

```css
flex-direction
+
flex-wrap
```

Example:

```css
flex-flow:row wrap;
```

Equivalent to:

```css
flex-direction:row;
flex-wrap:wrap;
```

---

# Flex Item Properties

These properties are applied to child elements.

---

# 1. order

Changes the visual order of items.

```css
.box1{
    order:3;
}

.box2{
    order:1;
}

.box3{
    order:2;
}
```

Output:

```text
2 3 1
```

### Real Life Example

Queue management at a ticket counter.

---

# 2. flex-grow

Controls how extra space is distributed.

```css
.box1{
    flex-grow:1;
}

.box2{
    flex-grow:2;
}

.box3{
    flex-grow:1;
}
```

Ratio:

```text
1 : 2 : 1
```

### Real Life Example

Pizza sharing.

Person B receives twice as many slices as Person A and Person C.

---

# 3. flex-shrink

Controls shrinking when available space is less than required.

Default:

```css
flex-shrink:1;
```

Items are allowed to shrink.

---

Prevent shrinking:

```css
flex-shrink:0;
```

Items maintain their size.

### Real Life Example

Clothes can be compressed in a travel bag.

A laptop should not be compressed.

---

# 4. flex-basis

Defines the initial main size of a flex item before free space is distributed.

```css
flex-basis:200px;
```

### Real Life Example

Each guest is initially assigned one seat before adjustments are made.

---

# 5. flex

Shorthand for:

```css
flex-grow
flex-shrink
flex-basis
```

Instead of:

```css
flex-grow:1;
flex-shrink:1;
flex-basis:0;
```

Use:

```css
flex:1;
```

---

## Common Values

```css
flex:1;
flex:2;
flex:1 1 200px;
```

---

# 6. align-self

Overrides align-items for a specific flex item.

```css
.special{
    align-self:flex-end;
}
```

Only that item changes position.

### Real Life Example

Class photo.

Everyone stands in the center except one student.

---

# Important Differences

## align-items vs align-content

| align-items         | align-content           |
| ------------------- | ----------------------- |
| Controls Items      | Controls Lines          |
| Works With One Line | Requires Multiple Lines |
| More Common         | Less Common             |

---

## flex-grow vs flex-shrink

| flex-grow           | flex-shrink           |
| ------------------- | --------------------- |
| Handles Extra Space | Handles Lack of Space |
| Expands Items       | Compresses Items      |

---

## width vs flex-basis

| width                   | flex-basis                        |
| ----------------------- | --------------------------------- |
| General Sizing Property | Flexbox Sizing Property           |
| Independent             | Participates In Flex Calculations |

---
