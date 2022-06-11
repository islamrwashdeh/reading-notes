# Data Modeling

**SQL vs NoSQL**

| **Differences** | **SQL** |**NoSQL** |
| :---         |     :---:      |          ---: |
| called   | Relational Databases (RDBMS)   |   non-relational or distributed |
| table   | table based databases    | document based     |
|  schema  | predefined schema     |  dynamic schema     |
|  type of data to be stored  | not best fit for hierarchical data storage   |  fits better for the hierarchical data storage   |not good fit for complex queries.   |
| scalability  | vertically scalable    |horizontally scalable. |




## Data Modeling Concepts

1. ***Data Modeling – Table Elements***

![pic](https://www.essentialsql.com/wp-content/uploads/2021/11/Database-Table-Data-Modeling.png)   

The **Table Name**, which is located at the top of the table.   
The **Primary Keys**.  Remember the primary keys uniquely identify each row in a table.  A table typically has one primary key, but can have more.  When the key has more than one column, it is called a compound key.     

**Table Columns** – There can be one or more table columns.  To keep the diagrams simple, I don’t show the data types.  I may introduce those later when we focus on more comprehensive modeling.       

**Foreign Key** – This is a column or set of columns which match a primary key in another table.




2. ***Data Modeling – Table Relationships***    

![pic](https://www.essentialsql.com/wp-content/uploads/2014/06/DataModel-Relations1.png)   

*one-to-many relationship*   

We connect lines between tables to show relationships.  In some cases an entry in one table can be related to more than one entry in another.

## Sequelize v6

**Sequelize** is a promise-based Node.js ORM tool for Postgres, MySQL, MariaDB, SQLite, Microsoft SQL Server, Amazon Redshift and Snowflake’s Data Cloud. It features solid transaction support, relations, eager and lazy loading, read replication and    more.        

      



**example**

```
const { Sequelize, Model, DataTypes } = require('sequelize');
const sequelize = new Sequelize('sqlite::memory:');

class User extends Model {}
User.init({
  username: DataTypes.STRING,
  birthday: DataTypes.DATE
}, { sequelize, modelName: 'user' });

(async () => {
  await sequelize.sync();
  const jane = await User.create({
    username: 'janedoe',
    birthday: new Date(1980, 6, 20)
  });
  console.log(jane.toJSON());
})();

```


## resources

1.   [nosql vs sql](https://canvas.instructure.com/courses/4839234/discussion_topics/14886093)


2. [sql modeling techniques](https://www.essentialsql.com/get-ready-to-learn-sql-7-simplified-data-modeling/)

3. [sql vs nosql](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)