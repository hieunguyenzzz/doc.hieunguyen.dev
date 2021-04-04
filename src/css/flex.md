---
name: Flex
menu: Css
---

# Flex in CSS

## Container

##### `display: flex;`

The flex container becomes flexible

##### `flex-direction`

The column value stacks the flex items vertically

possible value:
-   column
-   column-reverse
-   row
-   row-reverse

> note that when you set the direction to a reversed row or column, start and end are also reversed. look at the example bellow


```css
/* with this example these child elements will end up showing at top-left of the container*/
#pond {
    display: flex;
    flex-direction: row-reverse;
    justify-content: flex-end;
}
```

> Notice that when the flex direction is a column, `justify-content` changes to the vertical and `align-items` to the horizontal.

```css
/*with this example these childs elements will end up showing as column, and being pushed to the bottom */
#pond {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
}
```

##### `flex-wrap`

possible values:
-   nowrap (default):   by default it is `nowrap` which force all the childs to sit into 1 row.
-   wrap:               this will float childs to stay on next rows
-   wrap-reverse:       this will float childs to stay on next rows, reverse order vertically

##### `flex-flow`

The `flex-flow` property is a shorthand property for setting both the `flex-direction` and `flex-wrap` properties.

For example, you can use `flex-flow: row wrap` to set rows and wrap them.

##### `justify-content`

The `justify-content` property is used to align the flex items:

-   center
-   flex-start
-   flex-end
-   space-around
-   space-between

##### `align-items`

The `align-items` property is used to align the flex items vertically.

- flex-start
- flex-end;
- center;
- baseline
- stretch ( default) 

##### `align-content`
align-content determines the spacing between lines

- flex-start: Lines are packed at the top of the container.
- flex-end: Lines are packed at the bottom of the container.
- center: Lines are packed at the vertical center of the container.
- space-between: Lines display with equal spacing between them.
- space-around: Lines display with equal spacing around them.
- stretch: Lines are stretched to fit the container.


## Child 

##### `order`
##### `flex-grow`
##### `flex-shrink`
##### `flex-basis`
##### `flex`
##### `align-self`

this attribute is useful when you want to only align specific child item. This property accepts the same values as [align-items](#align-items)

