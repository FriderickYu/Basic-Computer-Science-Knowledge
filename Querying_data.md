# Querying data and Sorting data

```mysql
select column from table_name;
```

<img src="./pic/Querying_data/select.jpg" width = "246" height = "78" alt="select" align=center/>

When executing the `SELECT` statement. MySQL evaluates the `FROM` clause before the `SELECT` clause

Try to avoid to use `select *`, because it affects the efficiency, please write the column name specifically

`order by` shows you how to sort result set

```sql
select column
from table_name
order by
column1 [ASC|DESC]
```

By default, `order by` clause uses `ASC`

<img src="./pic/Querying_data/order_by.jpg" width = "382" height = "78" alt="order_by" align=center/>

`order by` clause can also sort a result set by an expression

```mysql
SELECT 
	orderNumber, orderLineNumber, priceEach * quantityOrdered
FROM
	orderdetails
ORDER BY
	priceEach * quantityOrdered DESC;
```

To make the query more readable, you can assign the expression in the `SELECT` clause a *column alias* and use that *column alias* in the `order by` clause

```mysql
SELECT 
	orderNumber, orderLineNumber, 
	priceEach * quantityOrdered AS subtotal
FROM
	orderdetails
ORDER BY
	subtotal DESC;
```

`FIELD(String, str1, str2, str3...)`

`FIELD()` returns the position of the String in the str1, str2... If the String is not in the list, `FIELD()` returns 0.

`SELECT FIELD('A', 'A', 'B', 'C');`

Returns 1 because the position of the string `A` is the first position on the list `A`, `B` and `C`

```sql
SELECT 
	orderNumber, `status`
FROM
	orders
ORDER BY FIELD(`status`,
        'In Process',
        'On Hold',
        'Cancelled',
        'Resolved',
        'Disputed',
        'Shipped');
```

sorted status by the following order

**Noticed**: In MySQL, `NULL` comes before `non-Null` values. So when you use `order by` defaultly, `NULL` appears first in the result set
