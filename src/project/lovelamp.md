---
name: love lamp
menu: project
route: project/lovelamp
---


# love lamp

git repo: https://github.com/moltin/gatsby-demo-store


css framework: tailwindcss

## task

### replace moltinClient by MagentoClient
1. moltinClient is being used on CartContext, CheckoutContext

### remove Product Collection

1. product collection is duplicated to product category, some files at:

```text
pages/collection.js
```

### abstract the price display 

```javascript
//src/components/Product.js
const formatPrice = price.currency + price.value;

// src/templates/ProductPage.js

```

### make the on sales dynamic

file path: src/components/Product.js
variable: on_sale need to be dynamic

### add SEO component to product page

it does not work so I have to remove it for now 

## processing

trying to get createPage stuff work `gatsby-test` for templates/ProductPage.js and template/ProductList.js