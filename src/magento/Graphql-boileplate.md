---
name: GraphQL Boilerplate
menu: Magento
route: magento/graphql-boilerplate
---

# GraphQL Boilerplate
## Product

### filter by sku


```graphql
{
  products(
    filter: { 
      sku: {
        like: "24-WB%"
      } 
    }
  ) {
    items {
      sku
    }
  }
}
```

**wanna get all products ?** filter by category id 2
