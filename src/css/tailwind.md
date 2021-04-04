---
name: Tailwindcss
menu: Css
---

# Tailwind css


they created all the css class ready for using

## Setup

##### tailwind.config.js

```javascript
const defaultTheme = require('tailwindcss/defaultTheme');

// gatsby-plugin-purgecss already handling unused css.
module.exports = {
  purge: {
    enabled: false,
  },
  theme: {
    extend: {
    },
  },
  variants: {},
  plugins: [],
};

```

##### postcss.config.js

```javascript
module.exports = {
  plugins: [
    require('tailwindcss'),
    require('autoprefixer'),
  ]
}
```
##### tailwind.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

##### postcss-cli

this package is being used to generated css from tailwind.css

```
postcss css/tailwind.css -o public/build/tailwind.css
```
## how to use Tailwind

### essential thing

#### 4 breakpoint: 

|breakpoint|in px|
|---|---|
|sm|640px|
|md|768px|
|lg|1024px|
|xl|1280px|

#### responsive 

apply style on individual breakpoint
i.e
```
sm:m-8 // small screen will have mergin:8
```


### classes

```
m-{1-9} : margin
mx-{1-9}: margin horical way
my-{1-9}: margin vertical way
p-{1-9}: padding

rounded-lg
shadow-xl
bg-indigo-500
tracking-wider
font-semibold
uppercase
```
#### `Container`

> The .container class sets the max-width of an element to match the min-width of the current breakpoint. This is useful if you'd prefer to design for a fixed set of screen sizes instead of trying to accommodate a fully fluid viewport.






