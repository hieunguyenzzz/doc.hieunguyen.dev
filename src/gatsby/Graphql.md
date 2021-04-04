---
name: GraphQL
menu: Gatsby
---

# Graphql

## How to use graphQL on gatsby

There are 2 ways of using graphQL on Gatsby, 1 for page component, and another for non-page component

### The 1st way for page component

Export a query on page component

```js
import React from "react"
import Layout from "../components/layout"
import { graphql } from "gatsby"

export default ({data}) => (
    <Layout>
        <h1>About {data.site.siteMetadata.title}</h1>
        <p>
            We're the only site running on your computer dedicated to showing the best
            photos and videos of pandas eating lots of food.
        </p>
    </Layout>
)

export const query = graphql`
    query {
        site {
            siteMetadata {
                title
            }
        }
    }
`

```

### The 2nd way for non-page component


```js
export default ({ children }) => {
    const data = useStaticQuery(
        graphql`
            query {
                site {
                    siteMetadata {
                        title
                    }
                }
            }
        `
    )

    return (
        <h1>{data.site.siteMetadata.title}</h1>
    )
}
```
