---
name: Fundamenntal
menu: Css
route: css/fundamental
---

## Basic CSS need to know

###  Outline

the area outside border, not a part of the element's dimension

CSS has following outline properties

```
outline-style (required)
outline-color
outline-width
outline-offset
outline
```

`outline-style` is required for other properly to have effect
`outline-offset` adding space between border and the outline

### Text


`text-color`
`background-color`
`text-align`
`direction`
`text-decoration` (underline, bottomline stuff)
`text-transform` ( specify lowercase, uppercase ) 
`text-indent` specify the indentation of the first line
`letter-spacing` space between the characters in a text 
`line-height` space between lines
`word-spacing` space between words
`white-space` ????
`text-shadown` add shadown to text

> if you define `color` you will have to also define `background-color`

`text-align` (left,right,center, justify)

justify will make all the content has same width, ( like magazine)

### Font 

there are 2 types of font family names
- generic family  (type of font: serif, san-serif, monospace)
- font family ( the font name: Times New Roman, Arial )

each generic family has several font
`font-family`
`font-style`
`font-weight` (bold, not bold ..etc)
`font-variant` (lower letter will be cap, however these cap will be smaller than normal cap)
`font-size`
`font-google` if you dont like default font pool you can add hundred more of font using google font
i.e 
```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css?familty=Sofia" />
<style>
    body {
        font-family: Sofia,serif;   
    }
</style>
```
 
### Icons

### Lists

`list-style-image`  specify any image to be list item marker 
`list-style-position` (outside | inside | none) - if it is none the margin and padding should be also removed 

### Table

`border`
`border-collapse`


##### Responsive table 
it will display a horizontal scroll bar if the screen is too small

wrap the table by a div with 

