Name - Fulare Vicky Anil
Department - Msc in PUCSD
Roll no - R19111010
Email -vickyfulare1998@gmail.com
github link for attached assignment - 
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

----------------------------------------------------------------------------------------------------------------------------------

I attached a vicky_readme.txt file in that all schemas are defined and some queries are fired according to mention schemas .

---------------------------------------------------------------------------------------------------------------------------------
