---
name: Gatsby Boilerplate
menu: Gatsby
route: gatsby/boilerplate
---

# Gatsby Boilerplate
## Typography Module

##### `gatsby-config.js`
```js
module.exports = {
  plugins: [
    {
      resolve: `gatsby-plugin-typography`,
      options: {
        pathToConfigModule: `src/utils/typography`,
      },
    },
  ],
}
```
##### `src/utils/typography`

```js
import Typography from "typography"
import fairyGateTheme from "typography-theme-fairy-gates"
const typography = new Typography(fairyGateTheme)
export const { scale, rhythm, options } = typography
export default typography
```
## Linking between pages

### `<Link />` component

```js
import React from "react"
import { Link } from "gatsby" // this is the one 
import Header from "../components/header"

export default () => (
  <div style={{ color: `purple` }}>
    <Link to="/contact/">Contact</Link> 
    <Header headerText="Hello Gatsby!" />
    <p>What a world.</p>
    <img src="https://source.unsplash.com/random/400x200" alt="" />
  </div>
)
```
