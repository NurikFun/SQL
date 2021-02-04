# SQL

# 1. Union

< query 1 >
UNION [ALL]
< query 2 >

The UNION clause combines the results of two SELECT statements into a single result set. If the ALL parameter is given, all the duplicates of the rows returned are retained; otherwise the result set includes only unique rows. Note that any number of queries may be combined. Moreover, the union order can be changed with parentheses.

The following conditions should be observed:

  1. The number of columns of each query must be the same;

  2. Result set columns of each query must be compared by the data type to each other (as they follows);

  3. The result set uses the column names from the first query;

  4. The ORDER BY clause is applied to the union result, so it may only be written at the end of the combined query.
  
 
 **Find the model numbers and prices of the PCs and laptops:**
 
 SELECT model, price FROM PC
 UNION
 SELECT model, price FROM Laptop
 ORDER BY price DESC;
 
    model   	Price
    1121   	850
    1232   	600
    1232   	400
    1232   	350
    1233   	980
    1233   	950
    1233   	600
    1260   	350
    1298   	1050
    1298   	700
    1321   	970
    1750   	1200
    1752  	1150
    
    
# 2. Intersect and Except (Пересечение и разность)

Within the standard of  SQL language there are clauses of SELECT statement for fulfillment of operations of intersection and subtraction of the queries. Such queries are INTERSECT  [ALL] (intersection) and EXCEPT [ALL] (subtraction), which operate analogously to UNION statement. Into the resulting set only those rows are included that are in the both queries (INTERSECT) and only those rows of the first query, that are absent in the second one (EXCEPT). Thereby both of the queries, that are involved in the operation, should be characterized by the same number of columns, and the corresponding columns should have the same (or implied) data types. The titles of the columns of the resulting set are formed from the titles of the first query.

If the key word ALL is not used, that the duplicate strings should be automatically canceled during fulfillment of the operation. If ALL is indicated, than the number of duplicate rows is subject to the following rules (n1 – the number of duplicate rows of the first query, n2 – the number of duplicate rows of the second query):

INTERSECT ALL: min(n1, n2)
EXCEPT ALL: n1 - n2, if n1>n2.

**Select the ships, which are included both into Ships table and into Outcomes table.**

SELECT name FROM Ships
INTERSECT
SELECT ship FROM Outcomes;

**Find the makers producing PCs but not laptops.**

select maker from product where type = 'PC'
intersect 
select maker from product where type = 'Laptop'




    
