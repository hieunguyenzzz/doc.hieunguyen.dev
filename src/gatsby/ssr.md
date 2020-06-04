---
name: Server-side rendering 
menu: Gatsby
route: gatsby/server-side-rendering
---

# Information & API

gatsby use the file `gatsby-ssr.js` on the root folder for server-side rendering so it can update pages

there are API which is useful

## wrapRootElement

 > need to find out: when will this being trigger ?

good place to append `Context` stuff

```js
export const wrapRootElement = ({ element }) => {
  return (
    <LayoutProvider>
      <Elements>{element}</Elements>
    </LayoutProvider>
  )
}
```
## wrapPageElement

place for layout thing

```js
export const wrapPageElement = ({ element, props }) => {
  return <Layout {...props}>{element}</Layout>
}
```