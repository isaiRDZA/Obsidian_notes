The `orders` table has the following columns;
- `id` - the order id
- `product_id` - the product id
- `price` - the price of the individual product item
- `quantity` - the quantity of items in the order

1. Given an `orders` table, calculate the `price` times `quantity` of each order. Include the `id` and `product_id` columns in the result.
```sql
select id, 
	product_id, 
	quantity * price
from orders
```
![[Pasted image 20241103132602.png]]
