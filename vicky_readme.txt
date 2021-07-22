Name - Fulare Vicky Anil
Department - Msc in PUCSD
Roll no - R19111010
Email -vickyfulare1998@gmail.com
github link for attached assignment - https://github.com/vickyfulare/Sql-Schema-Assignment-agrostar.git
---------------------------------------------------------------------------------------------------------------------------------

Problem:
  You are required to design SQL schema for e-commerce. Your schema should provide
  following functionality
  1 . Users can buy products.
  2 . The same products may be sold by multiple sellers
  3 . Products can have discounts, offers.
  4 .  Order can be cash on delivery, online payment.
  5 . (BONUS) other “must have” use cases related to e-commerce.

---------------------------------------------------------------------------------------------------------------------------------

ANSWER ---

I read a statement or problem so i create e-commerce database and all schemas in that .
 
First i create a e-commerce database .

I create a schemas as following .

1 . User(u_id ,uname ,uaddr)
2 . Product(prod_id ,prodname ,prize ,discounts ,offer  ,u_id )
3 . seller(sno ,sname ,saddr,prod_id )
4 . orders(o_id ,oname ,u_id ,sno)
5 . payment(p_id ,payment_mode ,o_id )

// In Product table u_id is takes a foreign key references for that .
// In seller table prod_id is takes a foreign key references for that .
// In orders table u_id and sno is takes a foreign key references for that .
// In payment table o_id is takes a foreign key references for that .
-------------------------------------------------------------------------------------------------------------------------------

* 1] Now a create a schemas for the following tables 

1 . User
    User(u_id ,uname ,uaddr)

   mysql> desc User;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| u_id  | int(11)     | NO   | PRI | NULL    |       |
| uname | varchar(30) | NO   |     | NULL    |       |
| uaddr | varchar(30) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.07 sec)

2 . Product 
    Product(prod_id ,prodname ,prize ,discounts ,offer  ,u_id )
    
    mysql> mysql> desc Product;
+-----------+--------------+------+-----+---------+-------+
| Field     | Type         | Null | Key | Default | Extra |
+-----------+--------------+------+-----+---------+-------+
| prod_id   | int(11)      | NO   | PRI | NULL    |       |
| prodname  | varchar(30)  | YES  |     | NULL    |       |
| prize     | decimal(8,2) | YES  |     | NULL    |       |
| discounts | varchar(20)  | YES  |     | NULL    |       |
| offer     | varchar(20)  | YES  |     | NULL    |       |
| u_id      | int(11)      | YES  |     | NULL    |       |
+-----------+--------------+------+-----+---------+-------+
6 rows in set (0.00 sec)

3 . seller 
    seller(sno ,sname ,saddr,prod_id )

    mysql> desc seller;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| sno     | int(11)     | NO   | PRI | NULL    |       |
| sname   | varchar(30) | YES  |     | NULL    |       |
| saddr   | varchar(30) | YES  |     | NULL    |       |
| prod_id | int(11)     | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

4 . orders 
    orders(o_id ,oname ,u_id ,sno)

    +-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| o_id  | int(11)     | NO   | PRI | NULL    |       |
| oname | varchar(30) | YES  |     | NULL    |       |
| u_id  | int(11)     | YES  |     | NULL    |       |
| sno   | int(11)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

5 . payment
    payment(p_id ,payment_mode ,o_id )
    
    +--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| p_id         | int(11)     | NO   | PRI | NULL    |       |
| payment_mode | varchar(20) | YES  |     | NULL    |       |
| o_id         | int(11)     | YES  |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

--------------------------------------------------------------------------------------------------------------------------------

* 2] After insert a values the tables as follows -
 
  1 . User 
    
     select * from User ;
    
     mysql> select * from User ;
+------+---------+--------+
| u_id | uname   | uaddr  |
+------+---------+--------+
|    1 | Vicky   | Pune   |
|    2 | Ajay    | Pune   |
|    3 | Akash   | Mumbai |
|    4 | Sachin  | Delhi  |
+------+---------+--------+
4 rows in set (0.04 sec)

 2. Product 
  
   select * from Product ;
   
   +---------+----------+----------+-----------+--------+------+
| prod_id | prodname | prize    | discounts | offer  | u_id |
+---------+----------+----------+-----------+--------+------+
|     201 | TV       | 50000.00 | 10%       | 4 days |    1 |
|     202 | Fridge   | 30000.00 | 15%       | 3 days |    2 |
|     203 | Cooler   | 35000.00 | 12%       | 5 days |    3 |
|     204 | Scooter  | 75000.00 | 20%       | 2 days |    4 |
|     205 | Soaps    |  2000.00 | 22%       | 2 days |    1 |
|     206 | Shampoos |  2500.00 | 10%       | 3 days |    2 |
+---------+----------+----------+-----------+--------+------+
6 rows in set (0.03 sec)

  3 . seller
     select * from seller ;
     
    +------+-------+--------+---------+
| sno  | sname | saddr  | prod_id |
+------+-------+--------+---------+
| 1001 | Akash | Pune   |     201 |
| 1002 | Vivek | Pune   |     204 |
| 1003 | Vikas | Mumbai |     202 |
| 1004 | Sagar | Mumbai |     205 |
| 1005 | Ram   | Delhi  |     203 |
| 1006 | Sham  | Delhi  |     206 |
+------+-------+--------+---------+
6 rows in set (0.01 sec)

 4 . orders
     select * from orders ;
    
    +------+----------------+------+------+
| o_id | oname          | u_id | sno  |
+------+----------------+------+------+
|  101 | Vegetables     |    1 | 1001 |
|  102 | Non-Vegetables |    4 | 1004 |
|  103 | Fast-Food      |    2 | 1002 |
|  104 | Chinese        |    3 | 1003 |
+------+----------------+------+------+
4 rows in set (0.00 sec)

 5 . payment 
     select * from payment ;
   
    mysql> select * from payment;
+------+--------------+------+
| p_id | payment_mode | o_id |
+------+--------------+------+
|   11 | Cash         |  101 |
|   12 | Online       |  102 |
|   13 | Online       |  103 |
|   14 | Cash         |  104 |
|   15 | Cash         |  105 |
+------+--------------+------+
5 rows in set (0.00 sec)
 ------------------------------------------------------------------------------------------------------------------------------------
* Now lets performs some test cases for the creating a schemes .

    Q1]- Find a user name whose buy a product 'TV' .
    Ans - mysql> select uname from User , Product Where User.u_id=Product.u_id AND prodname='TV';
        +--------+
        | uname  |
        +--------+
        | Vicky  |
        +--------+
        1 row in set (0.40 sec)

   Q2]- Find a product name whose user name is sachin .

    Ans - mysql> select prodname from User ,Product where User.u_id=Product.u_id AND uname='Sachin';
        +----------+
        | prodname |
        +----------+
        | Scooter  |
        +----------+
        1 row in set (0.31 sec)
  Q3]- Find a seller name whose product name is 'Fridge' .

  Ans - mysql> select sname from Product ,seller where Product.prod_id=seller.prod_id AND prodname='Fridge';
      +-------+
      | sname |
      +-------+
      | Vikas |
      +-------+
      1 row in set (0.00 sec)

  Q4]- update a prize of user 'Ajay' by 500 .

  Ans -mysql> update Product ,User set prize=prize+500 where User.u_id=Product.u_id AND uname='Ajay';
Query OK, 2 rows affected (0.13 sec)
Rows matched: 2  Changed: 2  Warnings: 0

mysql> select * from Product;
+---------+----------+----------+-----------+--------+------+
| prod_id | prodname | prize    | discounts | offer  | u_id |
+---------+----------+----------+-----------+--------+------+
|     201 | TV       | 50000.00 | 10%       | 4 days |    1 |
|     202 | Fridge   | 30500.00 | 15%       | 3 days |    2 |
|     203 | Cooler   | 35000.00 | 12%       | 5 days |    3 |
|     204 | Scooter  | 75000.00 | 20%       | 2 days |    4 |
|     205 | Soaps    |  2000.00 | 22%       | 2 days |    1 |
|     206 | Shampoos |  3000.00 | 10%       | 3 days |    2 |
+---------+----------+----------+-----------+--------+------+
6 rows in set (0.00 sec)

  Q5]- Find oname whose pay the payments online .
mysql> select oname from orders ,payment where orders.o_id=payment.o_id AND payment_mode='online';
+----------------+
| oname          |
+----------------+
| Non-Vegetables |
| Fast-Food      |
+----------------+
2 rows in set (0.01 sec)

  Q6] - Find oname whose pay the payments cash .

   mysql> select oname from orders ,payment where orders.o_id=payment.o_id AND payment_mode='cash';
+------------+
| oname      |
+------------+
| Vegetables |
| Chinese    |
+------------+
2 rows in set (0.00 sec)

 Q7] Print the prizes in ascending order in Product table.
  
  mysql> select * from Product order by prize asc;
+---------+----------+----------+-----------+--------+------+
| prod_id | prodname | prize    | discounts | offer  | u_id |
+---------+----------+----------+-----------+--------+------+
|     205 | Soaps    |  2000.00 | 22%       | 2 days |    1 |
|     206 | Shampoos |  3000.00 | 10%       | 3 days |    2 |
|     202 | Fridge   | 30500.00 | 15%       | 3 days |    2 |
|     203 | Cooler   | 35000.00 | 12%       | 5 days |    3 |
|     201 | TV       | 50000.00 | 10%       | 4 days |    1 |
|     204 | Scooter  | 75000.00 | 20%       | 2 days |    4 |
+---------+----------+----------+-----------+--------+------+
6 rows in set (0.00 sec)

---------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------








     
 

