---
name: GraphQL Boilerplate
menu: Magento
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

## Category 

### get all categories

```text

{
  category(id: 2) {
    children {
      id
      url_key
      url_path
      products {
        items {
          id
        }
      }
      children {
        id
        url_key
        url_path
        products {
          items {
            id
          }
        }
        children {
          id
          path
          url_key
           url_path
           products {
            items {
              id
            }
          }
        }
      }
    }
  }
}
```
