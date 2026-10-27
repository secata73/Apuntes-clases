### Gual

---
### Syntek
Cómo entrar base de datos 
~~~SQL
cd C:\xampp\mysql\bin
mysql -u root


SELECT * FROM products 
WHERE price > (SELECT AVG(price) FROM products);

SELECT * FROM PRODUCTS WHERE city = "s%";

SELECT CustomerName from Customers WHERE customerName LIKE "or%";
SELECT CustomerName from Customers WHERE CustomerName LIKE "_r%";
SELECT CustomerName from Customers WHERE CustomerName LIKE "a_%";
SELECT CustomerName from Customers WHERE CustomerName LIKE "a%o";

select CustomerName AS "Lista de clientes" from customers ORDER BY "Lista de clientes" ASC;

select CustomerName AS ListadeClientes from customers ORDER BY ListadeClientes ASC;

SELECT * FROM customers WHERE CustomerID IN (SELECT CustomerID FROM orders);

SELECT orders.OrderID, customers.CustomerName, orders.OrderDate FROM orders inner join customers ON orders.CustomerID = customers.CustomerID;

SELECT orders.OrderID, Customers.CustomerName, shippers.ShipperName
FROM
 (orders INNER JOIN customers ON orders.CustomerID = customers.CustomerID)
INNER JOIN shippers
ON orders.ShipperID = shippers.ShipperID;


SELECT customers.CustomerName, orders.OrderID
FROM customers
LEFT JOIN orders
ON customers.CustomerID = orders.CustomerID
ORDER BY customers.CustomerName;

//modificar para que muestre los clientes que NO han hecho una orden 
SELECT customers.CustomerName, orders.OrderID
FROM customers
LEFT JOIN orders
ON customers.CustomerID = orders.CustomerID
WHERE orders.CustomerID IS NULL
ORDER BY customers.CustomerName;

//modificar para que muestre el número de clientes que NO han hecho una orden 
SELECT COUNT(*) AS "Número de clientes sin órdenes"
FROM customers
LEFT JOIN orders
ON customers.CustomerID = orders.CustomerID
WHERE orders.CustomerID IS NULL;


//right join 
SELECT orders.OrderID, employees.LAstNAme, employees.FirstName
FROM orders
RIGHT JOIN employees
ON orders.EmployeeID = employees.EmployeeID
ORDER BY orders.OrderID;

//Full join no existe en MySQL, pero se puede simular con una combinación de LEFT JOIN y RIGHT JOIN. Aquí hay un ejemplo de cómo hacerlo:
SELECT c.CustomerId, c.CustomerName, o.OrderID, o.OrderDate
FROM customers AS c
LEFT JOIN orders AS o
ON c.CustomerID = o.CustomerID
UNION
SELECT c.CustomerId, c.CustomerName, o.OrderID, o.OrderDate
FROM customers AS c
RIGHT JOIN orders AS o
ON c.CustomerID = o.CustomerID

SELECT
    a.CustomerName AS Cliente1,
    b.CustomerName AS Cliente2,
    a.City
FROM customers a, customers b
WHERE a.CustomerID <> b.CustomerID
AND a.City = b.City
ORDER BY a.City;


SELECT shippers.ShipperName, COUNT(orders.OrderID) AS NumeroDeOrdenes
FROM orders LEFT JOIN shippers
ON orders.ShipperID = shippers.ShipperID
GROUP BY shippers.ShipperNAme
ORDER BY NumeroDeOrdenes DESC;
- 
SELECT COUNT(CustomerID), Country 
FROM customers
GROUP BY Country
ORDER BY COUNT(CustomerID) 

SELECT employees.LastName, COUNT(orders.OrderID) AS NumeroDeOrdenes
FROM orders
INNER JOIN employees AS e
ON o.EmployeeID = employees.EmployeeID
GROUP BY employees.LastName
HAVING COUNT(Orders.OrderID) > 10;
~~~

```sql
SELECT CustomerName, City, Country
FROM customers
ORDER BY 
    CASE 
        WHEN City IS NULL THEN country 
        ELSE City 
    END;
```
SQL contains
NOT NULL - ensures that a column cannot have a null 

event_date DATE, yyy-mm-dd
created_at DATETIME yyyy-mm-dd HH:mm:ss
~~~sql

create database testTec;

CREATE TABLE employees (
id int AUTO_INCREMENT PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
email VARCHAR(40) UNIQUE,
hire_date DATE,
salary DECIMAL(8,2),
department_id INT
);

CREATE TABLE departments(
id INT AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(100) NOT NULL
);

CREATE TABLE employees (
id int AUTO_INCREMENT PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
email VARCHAR(40) UNIQUE,
hire_date DATE,
salary DECIMAL(8,2),
department_id INT,
FOREIGN KEY(department_id) REFERENCES departments(id)
);

CREATE TABLE events(
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    event_date DATE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO events (name,event_date)
VALUE ('Conferencia LOREAL', "2026-10-23");

ALTER TABLE employees AND COLUMN birthdate DATE; --- crear
ALTER TABLE employees DROP COLUMN birthdate DATE; --- eliminar

AlTER TABLE employees CHANGE COLUMN birthdate dob DATE;;
ALTER TABLE employees MODIFY COLUMN salary DECIMAL (10,2) NOT NULL;
ALTER TABLE employees RENAME to staff;
ALTER TABLE staff ADD PRIMARY KEY (id);

CREATE TABE orders(
    id INT AUTO_INCREMENT PRIMARY KEY,
    customer_id INT NOT NULL,
    name VARCHAR(100) NOT NULL
);

CREATE TABLE customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

ALTER TABLE orders
ADD CONSTRAINT fk_customers
FOREIGN KEY (customer_id) REFERENCES customers(id);

ALTER TABLE orders
DROP FOREIGN KEY fk_customers;
~~~

### martha
