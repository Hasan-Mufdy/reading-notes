# Databases and ERDs

### DBMS

- Database is a collection of related data and data is a collection of facts and figures that can be processed to produce information.

- Mostly data represents recordable facts. Data aids in producing information, which is based on facts. For example, if we have data about marks obtained by all students, we can then conclude about toppers and average marks.

- A database management system stores data in such a way that it becomes easier to retrieve, manipulate, and produce information.

#### Characteristics

- Real-world entity − A modern DBMS is more realistic and uses real-world entities to design its architecture. It uses the behavior and attributes too. For example, a school database may use students as an entity and their age as an attribute.

- Relation-based tables − DBMS allows entities and relations among them to form tables. A user can understand the architecture of a database just by looking at the table names.

- Isolation of data and application − A database system is entirely different than its data. A database is an active entity, whereas data is said to be passive, on which the database works and organizes. DBMS also stores metadata, which is data about data, to ease its own process.

- Less redundancy − DBMS follows the rules of normalization, which splits a relation when any of its attributes is having redundancy in values. Normalization is a mathematically rich and scientific process that reduces data redundancy.

- Consistency − Consistency is a state where every relation in a database remains consistent. There exist methods and techniques, which can detect attempt of leaving database in inconsistent state. A DBMS can provide greater consistency as compared to earlier forms of data storing applications like file-processing systems.

- Query Language − DBMS is equipped with query language, which makes it more efficient to retrieve and manipulate data. A user can apply as many and as different filtering options as required to retrieve a set of data. Traditionally it was not possible where file-processing system was used.

### MVC

Model–view–controller (MVC) is a software design pattern commonly used for developing user interfaces that divides the related program logic into three interconnected elements. This is done to separate internal representations of information from the ways information is presented to and accepted from the user.

#### Database keys:

- Primary Key: A primary key is a unique identifier for a record in a table. It ensures that each record can be uniquely identified and provides a way to reference the record from other tables. In the example above, book_id, author_id, and publisher_id are primary keys.

- Foreign Key: A foreign key establishes a relationship between two tables. It refers to the primary key of another table, creating a link between the two. In the example, the author_id in the Books table is a foreign key referencing the author_id in the Authors table.

- Composite Key: A composite key consists of multiple columns that together form a unique identifier for a record. It is used when a single column does not provide enough uniqueness. For example, if a database needs to track the attendance of students in a class, a composite key could be a combination of student_id and class_id, ensuring that each student's attendance in a specific class is unique.

#### database schema:

- A database schema is a logical representation or blueprint of the structure of a database. It defines how the data is organized, how the tables are related to each other, and the constraints and rules that govern the data. A schema provides a framework for creating, modifying, and accessing the database.
