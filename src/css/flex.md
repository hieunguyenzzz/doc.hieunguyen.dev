---
name: Flex
menu: Css
route: css/flex
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


## Child 

##### `order`
##### `flex-grow`
##### `flex-shrink`
##### `flex-basis`
##### `flex`
##### `align-self`

this attribute is useful when you want to only align specific child item. This property accepts the same values as [align-items](#align-items)

