# sequelize-normalization

Sequelize : equelize is a modern TypeScript and Node.js ORM for Postgres, MySQL, MariaDB, SQLite and SQL Server, and more. Featuring solid transaction support, relations, eager and lazy loading, read replication and more.



to install  use : 
```
npm install --save sequelize
```

**Associations**
Sequelize supports the standard associations:     
1. One-To-One ; When a row of a table corresponds to a specific row of another table and vice versa, we have a One-To-One relation between the 2 tables.       

For example – each “Student” in the students’ table has a corresponding “Profile” in the profiles table.    

![pic](https://i0.wp.com/strapengine.com/wp-content/uploads/2022/01/sequelize-one-to-one-association.jpeg?resize=560%2C319&is-pending-load=1#038;ssl=1)       


2. One-To-Many  When one row of a table corresponds to multiple rows of another table it means we can have a One-To-Many relation.   

For example: for each “Student” in the students’ table we will have multiple “Attendance” records(rows) in the attendance table.   

![pic](https://i0.wp.com/strapengine.com/wp-content/uploads/2022/01/sequelize-one-to-many-association.jpeg?w=494&ssl=1)   


3. Many-To-Many.     
When multiple rows of a table correspond to multiple rows of another table we can have a Many-To-Many relation.   

For example: – for each “Student” in the students’ table, we can have multiple rows in the courses table as a “Student” can apply for more than 1 course. Similarly for each “Course” in the courses table, we can have more than 1 “Student” attending the “Course”.  

![pic](https://i0.wp.com/strapengine.com/wp-content/uploads/2022/01/sequelize-many-to-many-association.jpeg?resize=768%2C176&ssl=1)    


**To do this, Sequelize provides four types of associations that should be combined to create them:**    

1. The HasOne association    
2. The BelongsTo association
3. The HasMany association
4. The BelongsToMany association

**Creating the standard relationships**

1. To create a One-To-One relationship, the hasOne and belongsTo associations are used together;
2. To create a One-To-Many relationship, the hasMany and belongsTo associations are used together;
3. To create a Many-To-Many relationship, two belongsToMany calls are used together.


## Defining the Sequelize associations
The four association types are defined in a very similar way. Let's say we have two models, A and B. Telling Sequelize that you want an association between the two needs just a function call:    

```
const A = sequelize.define('A', /* ... */);
const B = sequelize.define('B', /* ... */);

A.hasOne(B); // A HasOne B
A.belongsTo(B); // A BelongsTo B
A.hasMany(B); // A HasMany B
A.belongsToMany(B, { through: 'C' }); // A BelongsToMany B through the junction table C
```
They all accept an options object as a second parameter (optional for the first three, mandatory for belongsToMany containing at least the through property):

```
A.hasOne(B, { /* options */ });
A.belongsTo(B, { /* options */ });
A.hasMany(B, { /* options */ });
A.belongsToMany(B, { through: 'C', /* options */ });
```


# resources

[1. sequelize-normalization](https://sequelize.org/docs/v6/core-concepts/assocs/)