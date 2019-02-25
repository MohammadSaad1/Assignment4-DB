DONE IN SQL WORKBENCH

# Assignment4-DB

<b>Excersise 1</b>

///// Create a database user for each of the four roles, and be restrictive in what the each user can do in the database.

In the readme file, argue why the permissions are as they are. //// 

The following users have been created with the following permissions:

Inventory:  
Update, Insert and Select from Product table and Productlines table.

The reason for that is that the inventory should be able to enter it, insert and select the data if needed.
Its not allowed the delete permission since it the possibility to delete tables and not just rows or columns.

<CITE> CREATE USER 'Inventory';	
GRANT UPDATE, INSERT, SELECT ON classicmodels.products TO Inventory;
GRANT UPDATE, INSERT, SELECT ON classicmodels.productlines TO Inventory;

 </CITE>

Bookkeeping: 
SELECT from Orders, Customer and Payments tables. 

No permissions is given except for the select, since its not supposed to chnge anything, but just to alarm if payments is not paid.

<CITE> CREATE USER 'Bookkeeping';	
GRANT SELECT ON classicmodels.orders TO Bookkeeping;
GRANT SELECT ON classicmodels.customers TO Bookkeeping;
GRANT SELECT ON classicmodels.payments TO Bookkeeping;
 </CITE>

HR: 
Usage from employees and offices.

HR is only supposed to look at the data and nothing more, and thereofer is the only given permission the possibility of viewing data.

<CITE> CREATE USER 'HR';	
GRANT USAGE ON classicmodels.employees TO HR;
GRANT USAGE ON classicmodels.offices TO HR;

 </CITE>

Sales: 
Can update, insert and select from Orders. 

Its supposed to create orders, get them and update them only. Not allowed to delete other tables and play around in the DB.


<CITE> CREATE USER 'Sales';	
GRANT UPDATE, INSERT, SELECT ON classicmodels.orders TO Sales;

 </CITE>

It: 
It is given all permission to all tables and DB's due to the fact that it is supposed to manage the whole DB without exceptions.


<CITE> CREATE USER 'IT';	
GRANT ALL PRIVILEGES ON *.* TO IT;</CITE>

<b> Excersise 2 </b>

INSERT INTO classicmodels.employees
VALUES (1, 'gurli', 'gris', 'vedik', 'sda@dsd.dk', 22, 33, 'chef');

INSERT INTO classicmodels.employees
VALUES (33, 'burli', 'bus', 'vedik', 'ssdasa@dsd.dk', 22, 33, 'ven');

INSERT INTO classicmodels.products
VALUES(23, 'Glaasses', 'Holdud', '10', 'friend', 'Good quality', true, 20000, 2.2);


INSERT INTO classicmodels.orders
VALUES (3, '2013-01-04 17:24:19', '2014-01-04 17:24:19', '2014-01-04 17:24:19', 
'Arrived', 'No comment', '31');

<b> Excersise 3 </b>
Following statement is called to backup all DB's. (From CMD Prompt in the BIN file of SQL server)
mysqldump.exe --all-databases
