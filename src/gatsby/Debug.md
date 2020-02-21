---
name: Debug
menu: Gatsby
route: gatsby/debug
---

# Debug with Gatsby
## Print all the pages which are going to be created

visit `http://localhost:8000/___graphql` and trigger query for this

```graphql
{
  allSitePage {
    edges {
      node {
        path
        component
        pluginCreator {
          name
          pluginFilepath
        }
      }
    }
  }
}
```
