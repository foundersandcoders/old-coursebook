# What are databases?

A database describes the structure in which data can be stored and accessed.

# why do we need them?

**Size**
 - Databases allow you to manipulate large amounts of data without opening up a large spreadsheet - if you had 2 million lines of data you wouldn't be able to open it in a spreadsheet.

**Ease of Updating**
Multiple people can update at any one time, changes won't be over written,

**Accuracy**
Rules can be applied to ensure consistency - e.g. defining the format of dates, and how they are inputted.  

**Security**
You can determine who has what 'rights' - i.e. control who can view and/or edit files. This is important because it is required by law in many area and professions.

**Redundancy**
Redundancy can be eliminated to give consistent data. For example you do not want, and therefore should not have exactly the same product in two places within the database, as this could lead to conflicts.

**Importance**
If there is a crash files are automatically backed up.



# What is a relational database?

A relational database is built up of data in tabular forms.

For example you may have a table for customer information and a table for employees.
- Each row would represent an employee or customer.
- Each column represents a single attribute of each employee or customer.

With a relational database you can get a row using a key, which is a unique value e.g. social security number, repetition will be disallowed. This unique key could have a computer generated number(synthetic key/ surrogate key).


# What is the difference between an SQL and NoSQL database?

SQL
It stands for Structured Query Language. it s a declarative query language, which used to make queries in databases these tend to be relational databases. You start by writing what you want in broad terms so the algorithm is not specify written out, i.e. select all books over 40 pounds is written as select* from books where list price > £40.

SQL uses the CRUD (create, read, update, delete),
The acronym CRUD refers to all of the major functions that are implemented in relational database applications. Each letter in the acronym can map to a standard SQL statement, HTTP method or DDS operation:

| #  | #  |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

NoSQL (not only SQL)
Typically does not use SQL but may support the language. There is no predefined schema this means that data can be added to the data base in any format. Documents can be stored instead of just updating columns and rows as you would in relational database. You can store data of different compositions i.e. a string or an object. Each document you add to the database has a unique ID.
key values stores are a way of storing data, you have a two column table, with keys in one column with any type of value in the other i.e. string, object ect.
graph data bases are another way of storing data using NoSQL, everything is stored as connected nodes, located in, works in, manages, reports to,  
