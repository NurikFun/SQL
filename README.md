# SQL

*1. *Union*

< query 1 >
UNION [ALL]
< query 2 >

The UNION clause combines the results of two SELECT statements into a single result set. If the ALL parameter is given, all the duplicates of the rows returned are retained; otherwise the result set includes only unique rows. Note that any number of queries may be combined. Moreover, the union order can be changed with parentheses.

The following conditions should be observed:

  1. The number of columns of each query must be the same;

  2. Result set columns of each query must be compared by the data type to each other (as they follows);

  3. The result set uses the column names from the first query;

  4. The ORDER BY clause is applied to the union result, so it may only be written at the end of the combined query.
  
 
 Find the model numbers and prices of the PCs and laptops:
 
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
    
    
    
