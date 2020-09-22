---
name: Checkout
menu: Magento
route: magento/checkout
---

# All about checkout
## Background information

Magento use 1 phtml template for checkout
```
vendor/magento/module-checkout/view/frontend/templates/onepage.phtml
```

some jobs done by this template

- all the backend data include quote data, shipping data, payment data was inject into js by `window.checkoutConfig`, these data is grabbed by
```
`vendor/magento/module-checkout/view/frontend/web/js/model/quote.js`, all the js object can retrieve the quote information by adding this js as dependency
```

- all the customer data is injected into js by `window.customerData`

## checkout total
### sort order for this totals is configured on admin panel

> Stores->Configuration->SALES->Sales->General->Checkout Totals Sort Order

## Customization on checkout

### Inject custom information into checkout

> see `vendor/magento/module-checkout/Model/CompositeConfigProvider.php`

### add more information into quote item and sales item

<https://magento.stackexchange.com/a/277601>