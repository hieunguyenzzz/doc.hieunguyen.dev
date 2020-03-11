---
name: Eten
menu: Magento
route: magento/eten
---

# Eten

## vendor module 

## Information

module name: Wsoftpro_Vendor

vendor is eav entity

## sample vendor
mevlana id:87
a-ora-pizza id:380

## sample vendor attribute
attribute 

vendor_shop_url id: 177
vendor_shop_name id:  157
menu_category id: 223 text

### product attribute 
vendor 186 int

## Frontend
http://eten.m2loc/a-ora-pizza? 

=> this is category page 
layout file is catalog_category_view
category page is connected with vendor by vendor_id field on `catalog_category_entity`

## the import files 

some product id 
201010
201009
201008
201007
201015

product with options

201073
201008


test.csv
6186 O5PRPQN3Q
37RRO331  

## problem
### app/code/Wsoftpro/Vendor/view/frontend/layout/catalog_category_view.xml

=> this is disable cache of category page

### really slow on the backend 
- restaurant page is really slow
- product page is slow


error when compiling 

```
Wsoftpro\CheckoutCustom\Controller\Checkout\Success
		Extra parameters passed to parent construct: $checkoutSession, $paymentHelper, $mollieModel, $mollieHelper. File: /var/www/eten/data/www/exten_original/app/code/Wsoftpro/CheckoutCustom/Controller/Checkout/Success.php
```


## importing technical information

entity: catalog_product
class: Magento\CatalogImportExport\Model\Import\Product
$this->getOptionEntity() \\ Magento\CatalogImportExport\Model\Import\Product\Option

Magento\CatalogImportExport\Model\Import\Product\Option::_importData();

```
$multiRowData = Array
(
    [0] => Array
        (
            [_custom_option_store] => 
            [_custom_option_title] => Topping
            [_custom_option_sort_order] => 1
            [_custom_option_row_sort] => 0
            [_custom_option_type] => checkbox
            [_custom_option_row_title] => Tomatensaus
            [_custom_option_row_price] => 1.000000
            [_custom_option_price] => 1.000000
            [_custom_option_is_required] => 1
            [_custom_option_row_sku] => NN7212PR55PQO
            [_custom_option_sku] => NN7212PR55PQO
            [_custom_option_max_characters] => 0
            [_custom_option_file_extension] => 
            [_custom_option_image_size_x] => 0
            [_custom_option_image_size_y] => 0
        )

    [1] => Array
        (
            [_custom_option_store] => 
            [_custom_option_title] => 
            [_custom_option_sort_order] => 1
            [_custom_option_row_sort] => 1
            [_custom_option_type] => 
            [_custom_option_row_title] => Mozzarella kaas
            [_custom_option_row_price] => 1.500000
            [_custom_option_price] => 1.500000
            [_custom_option_is_required] => 1
            [_custom_option_row_sku] => NN7330PR5571O
            [_custom_option_sku] => NN7330PR5571O
            [_custom_option_max_characters] => 0
            [_custom_option_file_extension] => 
            [_custom_option_image_size_x] => 0
            [_custom_option_image_size_y] => 0
        )

)


$optionData = Array
(
    [option_id] => 2
    [sku] => 
    [max_characters] => 0
    [file_extension] => 
    [image_size_x] => 0
    [image_size_y] => 0
    [product_id] => 2052
    [type] => checkbox
    [is_require] => 1
    [sort_order] => 1
)

$option = Array
(
    [0] => Array
        (
            [option_id] => 2
            [sku] => 
            [max_characters] => 0
            [file_extension] => 
            [image_size_x] => 0
            [image_size_y] => 0
            [product_id] => 2052
            [type] => checkbox
            [is_require] => 1
            [sort_order] => 1
        )

)


$title = Array
(
    [2] => Array
        (
            [0] => Topping
        )

)

$type = Array
(
    [values] => Array
        (
            [2] => Array
                (
                    [0] => Array
                        (
                            [option_type_id] => 3
                            [sort_order] => 0
                            [sku] => NN7212PR55PQO
                        )

                    [1] => Array
                        (
                            [option_type_id] => 4
                            [sort_order] => 1
                            [sku] => NN7330PR5571O
                        )

                )

        )

    [prices] => Array
        (
            [3] => Array
                (
                    [0] => Array
                        (
                            [price] => 1
                            [price_type] => fixed
                        )

                )

            [4] => Array
                (
                    [0] => Array
                        (
                            [price] => 1.5
                            [price_type] => fixed
                        )

                )

        )

    [titles] => Array
        (
            [3] => Array
                (
                    [0] => Tomatensaus
                )

            [4] => Array
                (
                    [0] => Mozzarella kaas
                )

        )

)

```



## options import

### options export from default magento 

name=Topping,
type=checkbox,
required=1,
price=1.000000,
sku=NN7212PR55PQO,
max_characters=0,
file_extension=,
image_size_x=0,
image_size_y=0,
price_type=fixed,
option_title=Tomatensaus|
name=Topping,type=checkbox,required=1,price=1.500000,sku=NN7330PR5571O,max_characters=0,file_extension=,image_size_x=0,image_size_y=0,price_type=fixed,option_title=Mozzarella kaas 

### options export from test file

name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7212PR55PQO,option_title=Tomatensaus (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7330PR5571O,option_title=Mozzarella kaas (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7330PR557OO,option_title=Cherry tomaatjes (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7101PR5577O,option_title=Olijven (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7101PR55Q0O,option_title=Knoflook (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=2.50,price_type=fixed,sku=NN7010PR55Q3O,option_title=Gedroogde rauwe ham (+€ 2,50)|name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7010PR55QPO,option_title=Champignons (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7330PR55QRO,option_title=Artisjokken (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=2.50,price_type=fixed,sku=NN7301PR55RNO,option_title=Gorgonzola (+€ 2,50)|name=Toppings,type=checkbox,required=0,price=2.50,price_type=fixed,sku=NN7212PR55R5O,option_title=Pegorino (+€ 2,50)|name=Toppings,type=checkbox,required=0,price=2.50,price_type=fixed,sku=NN7301PR55RQO,option_title=Taleggio (+€ 2,50)|name=Toppings,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7330PR5P01O,option_title=Parmezaan (+€ 2,00)|name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7301PR5P0OO,option_title=Rode ui (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7010PR5P07O,option_title=Salami (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=2.50,price_type=fixed,sku=NN7010PR5P10O,option_title=Salami pikante (+€ 2,50)|name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7010PR5P13O,option_title=Spaanse peper (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=3.00,price_type=fixed,sku=NN7330PR5P1PO,option_title=Buffalo mozzarella (+€ 3,00)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7010PR5P1RO,option_title=Aubergine (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7101PR5PNNO,option_title=Paprika (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7301PR5PN5O,option_title=Tonijn (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7301PR5PNQO,option_title=Mortadella (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7330PR5P31O,option_title=Ansjovis (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=3.00,price_type=fixed,sku=NN7212PR5P3OO,option_title=Bresaola (+€ 3,00)|name=Toppings,type=checkbox,required=0,price=1.50,price_type=fixed,sku=NN7212PR5P37O,option_title=Spinazie (+€ 1,50)|name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7301PR5PO0O,option_title=Rucola (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=1.00,price_type=fixed,sku=NN7301PR5PO3O,option_title=Ananas (+€ 1,00)|name=Toppings,type=checkbox,required=0,price=3.50,price_type=fixed,sku=NN7212PR5POPO,option_title=Verse burrata (+€ 3,50)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7101PR5QN3O,option_title=Cola (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7010PR5QNPO,option_title=Fanta (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7330PR5QNRO,option_title=Cola zero (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7212PR5Q3NO,option_title=Fanta cassis (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7301PR5Q35O,option_title=Sprite (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7330PR5Q3QO,option_title=Lipton ice tea peach (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7010PR5QO1O,option_title=Liptone ice tea green (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7330PR5QOOO,option_title=Chocomel (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7301PR5QO7O,option_title=Schweppes tonic (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7101PR5Q50O,option_title=Schweppes bitterlemon (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7101PR5Q53O,option_title=Minute maid appelsap (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7301PR5Q5PO,option_title=Minute maid jus d' orange (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7301PR5Q5RO,option_title=Fristi (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7301PR5QPNO,option_title=Fernandes cherry bouquet (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7212PR5QP5O,option_title=Fernandes green punch (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7330PR5QPQO,option_title=Red Bull (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7010PR5Q71O,option_title=Acqua panna (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=2.00,price_type=fixed,sku=NN7010PR5Q7OO,option_title=San pellegrino (+€ 2,00)|name=Drankje,type=checkbox,required=0,price=13.90,price_type=fixed,sku=NN7010PR5Q77O,option_title=Wijn pinot grigio (+€ 13,90)|name=Drankje,type=checkbox,required=0,price=13.90,price_type=fixed,sku=NN7212PR5QQ0O,option_title=Wijn montepulciano (+€ 13,90)|name=Drankje,type=checkbox,required=0,price=3.95,price_type=fixed,sku=NN7212PR5QQ3O,option_title=La croisade rosé (+€ 3,95)|name=Drankje,type=checkbox,required=0,price=3.95,price_type=fixed,sku=NN7330PR5QQPO,option_title=La croisade merlot (+€ 3,95)|name=Drankje,type=checkbox,required=0,price=3.95,price_type=fixed,sku=NN7010PR5QQRO,option_title=La croisade chardonnay (+€ 3,95)|name=Drankje,type=checkbox,required=0,price=3.95,price_type=fixed,sku=NN7010PR5QRNO,option_title=La croisade medium/sweet (+€ 3,95)|name=Drankje,type=checkbox,required=0,price=3.95,price_type=fixed,sku=NN7301PR5QR5O,option_title=Birra peroni (+€ 3,95)
7R5330RPQPRO
