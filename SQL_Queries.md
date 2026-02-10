## **Sales Insights Project Data Analysis Using SQL :**

**==========================================================================================================**

###### 

##### **1. Show all customer records**

###### 

###### &nbsp;   `SELECT \* FROM customers;`

###### 

##### **2. Show total number of customers**

###### 

###### &nbsp;   `SELECT count(\*) FROM customers;`

###### 

##### **3. Show transactions for Chennai market and market code for chennai is Mark001**

###### 

###### &nbsp;   `SELECT \* FROM transactions where market\_code='Mark001';`

###### 

##### **4. Show distrinct product codes that were sold in chennai**

###### 

###### &nbsp;   `SELECT distinct product\_code FROM transactions where market\_code='Mark001';`

###### 

##### **5. Show transactions where currency is US dollars**

###### 

###### &nbsp;   `SELECT \* from transactions where currency="USD"`

###### 

##### **6. Show transactions in 2020 join by date table**

###### 

###### &nbsp;   `SELECT transactions.\*, date.\* FROM transactions INNER JOIN date ON transactions.order\_date=date.date where date.year=2020;`

###### 

##### **7. Show total revenue in year 2020**



###### &nbsp;   `SELECT SUM(transactions.sales\_amount) FROM transactions INNER JOIN date ON transactions.order\_date=date.date where date.year=2020 and transactions.currency="INR\\r" or transactions.currency="USD\\r";`

###### &nbsp;	

##### **8. Show total revenue in year 2020, January Month**

###### 

###### &nbsp;   `SELECT SUM(transactions.sales\_amount) FROM transactions INNER JOIN date ON transactions.order\_date=date.date where date.year=2020 and and date.month\_name="January" and (transactions.currency="INR\\r" or transactions.currency="USD\\r");`

###### 

##### **9. Show total revenue in year 2020 in Chennai**

###### 

###### &nbsp;   `SELECT SUM(transactions.sales\_amount) FROM transactions INNER JOIN date ON transactions.order\_date=date.date where date.year=2020

###### and transactions.market\_code="Mark001";`

###### 

###### 

##### **Data Analysis Using Power BI**

##### **============================**

###### 

##### **1. Formula to create norm\_amount column**

###### 

###### `= Table.AddColumn(#"Filtered Rows", "norm\_amount", each if \[currency] = "USD" or \[currency] ="USD#(cr)" then \[sales\_amount]\*75 else \[sales\_amount], type any)`

###### 

###### 

###### 

###### 

