---
name: Tailwindcss
menu: Css
route: css/tailwind
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
|sm|1px|
|md|1px|
|lg|1px|
|xl|1px|

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




