# Domain Model

## Simplified user stories

- [x] Must be able to add bagel to basket
- [x] Must be able to remove bagel from basket
- [x] Must be able to check if basket is full
- [x] Must be able to change basket capacity
- [x] Must be able to check if item exists in basket
- [x] Warn when user removes non-existent item from basket
- [x] Must be able to check total cost of items in basket
- [x] Must be able to check cost of bagel before adding to basket
- [x] Must be able to choose fillings for bagel
- [x] Must be able to check cost of filling before adding to bagel order
- [x] Must be able to add coffee to basket
- [x] Must be able to check cost of coffee before adding to basket
- [x] Must be able to add promotion to product


## Methods

### Product (Bagel, coffee, etc.)

| Function Name  | Parameters               | Behavior                       | Returns      |
|----------------|--------------------------|--------------------------------|--------------|
| GetCost        | double cost              |                                |              |
| SetCost        | double newCost           |                                |              |
| AddPromo       | int amount, double price | Add a new promotion on product | void         |

### Basket

| Function Name            | Parameters             | Behavior                                        | Returns |
|--------------------------|------------------------|-------------------------------------------------|---------|
| Basket                   | int? capacity          | Constructor, sets capacity to cart              | void    |
| Add                      | string SKU, int amount | Adds product to basket                          | void    |
| Remove                   | string SKU, int amount |                                                 | void    |
| SetCapacity              | int newCapacity        | Sets the new capacity of a basket               | void    |
| [private] CheckDiscounts |                        |                                                 |         |
| [private] CheckCapacity  |                        | Checks whether the basket can fit more products | bool    |
| GetTotal                 |                        | Sets the new capacity of a basket               | double  |
| Order                    |                        | Submits the bagel order                         | void    |
| [override] ToString      |                        | Generates a string representation of cart       | string  |

### BasketItem
- Product
- Amount

### Inventory

| Function Name | Parameters                  | Behavior                          | Returns |
|---------------|-----------------------------|-----------------------------------|---------|
| Add           | Product product, int amount |                                   |         |
| Remove        | Product product, int amount |                                   |         |
| GetProduct    | string SKU                  | Get product by SKU                | Product |
| GetStock      |                             | Get stock of the specific product | int     |

### Order

| Function Name       | Parameters      | Behavior                                          | Returns |
|---------------------|-----------------|---------------------------------------------------|---------|
| Order               | List<OrderLine> | Constructor                                       | void    |
| [override] ToString |                 | Generate string representation of order (receipt) | string  |

### OrderLine
- Product
- Amount
- Price
- Discount
