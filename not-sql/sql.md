# About sql 
### SQL :  stands for Structured Query Language
its allow you to access and manipulate databases.

# _notes_  
## _1 select_
 its uesed to retrieve data from a SQL database .  
 1. to retrive query for a specific columns use :      
          **SELECT** column-name, column-name,        
           **FROM** mytable;         

 2. to retrieve  all columns use *:     
    **SELECT** *      
    **FROM** mytable;     

 ## _2 Queries with constraints_
 
    
 It allows you to retrive only specific data that meets spiecific conditions by using   (**whre** /**and**/**or**).      

 SELECT column-name , another_column,        
 **FROM** mytable        
**WHERE** condition
    **AND/OR** another_condition        
   **AND/OR** condition ;   
  
  **Hulpfull table :** 
| Operator     | 	Condition        | 	SQL Example                 |
| :---         |     :---:         |          ---:                 |
| =, !=, < <=, >, >= |    Standard numerical operators        | 	col_name != 4                  |
BETWEEN … AND … |Number is within range of two values (inclusive)            | 		col_name BETWEEN 1.5 AND 10.5               |
| NOT BETWEEN … AND|Number is not within range of two values (inclusive)            | col_name NOT BETWEEN 1 AND 10|
|IN (…)|Number exists in a list   |col_name IN (2, 4, 6) 	                |                
|NOT IN (…)	|	Number does not exist in a list   |col_name NOT IN (1, 3, 5) 	                |  
|LIKE	|Case insensitive exact string comparison   |col_name LIKE "ABC" | 
| NOT LIKE	|Case insensitive exact string inequality comparison  |col_name  NOT LIKE "ABC" | 	                 
|%|Used anywhere in a string to match a sequence of zero or more characters (only with LIKE or NOT LIKE)  |col_name LIKE "%AT%"(matches"AT", "ATTIC", "CAT" or even "BATS") | 
|-|Used anywhere in a string to match a single character (only with LIKE or NOT LIKE)   |col_name LIKE "AN_"(matches "AND", but not "AN") |          






## _3 Filtering and sorting Query results_
1. The **ORDER BY** keyword is used to sort the result-set in ascending or descending order.      
its sorts as ascending order by default.   
**DESC**  :           descending order      
**ASC**     :   scending order
2. **DISTINCT** keyword will blindly remove duplicate rows
3. **LIMIT** will reduce the number of rows to return
3. **OFFSET** will specify where to begin counting the number rows from.     



## _4 Simple SELECT Queries_
SELECT column, another_column,      
FROM mytable     
WHERE condition(s)     
ORDER BY column ASC/DESC   
LIMIT num_limit OFFSET num_offset;


## _5 Multi-table queries with JOINs_
A **JOIN**  used to combine rows from two or more tables, based on a related column between them 

## _6 Inserting rows_

we use **INSERT** to  inserting data into a database   


**INSERT INTO** mytable  
(column, coulmn2)  
VALUES (value_or_expr, another_value_or_expr),   
      (value_or_expr_2, another_value_or_expr_2)


## _7 Updating rows_

using to update existing data        

  **UPDATE** mytable  
**SET** column = value_or_expr,   
    other_column = another_value_or_expr, 
    
**WHERE** condition;


## _8 Deleting rows_
to delet data from database      
**DELETE** FROM mytable   
**WHERE** condition;   


## _9 CREATE TABLE_
we use **CREATE TABLE** to creat new table 
before creat table you have to be sure that if theres table with the same name or not  use **IF NOT EXISTS**       



    






     

    



 
