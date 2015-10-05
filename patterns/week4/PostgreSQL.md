# POSTGRESQL

## What is a database?

> A database is a computerised system that makes it easy to search, select and store information.


## Relational vs Non-relational?

### Relational

A relational database is a collection of data items organised as a set of formally described tables from which data can be accessed. Each table in a re

The rows contain the values or data instances; these are also called *records* or *tuples*.

'Relational' refers to the connections between tables in a database.

SQL or *Structured Query Language* are table based (relational) databases.

### Non-relational

NoSQL databases do not adhere to the structure desribed above. They are commonly document based, key-value pairs, graph databases or wide-column stores.
Document oriented databases allows us to embed metadata within our data entries. This means that each database entry contains extensive metadata needed to query it.

For example, same data stored in a key-value database, may have raw data stored in an entry value:
```
Bob Smith
bob.smith@example.com
(123) 555-0178
(890) 555-0133
123 Back St.
Boys, AR, 32225
US
```
In this example, it is easy for a human to read the post-code or person's first name or phone number - but for a computer to read and process these specific bits of information, it would be very difficult to write an algorithm which decodes it.

The same data stored as a value in a *docment-oriented* database, might look something like this:

```xml
<contact>
   <firstname>Bob</firstname>
   <lastname>Smith</lastname>
   <email type=Home>bob.smith@example.com</email>
   <phone type=Cell>(123) 555-0178</phone>
   <phone type=Work>(890) 555-0133</phone>
   <address>
     <type>Home</type>
     <street1>123 Back St.</street1>
     <city>Boys</city>
     <state>AR</state>
     <zip>32225</zip>
     <country>US</country>
   </address>
 </contact>
```
Note that within the value, context is given to each information. This allows for advanced automated processing. For instance, one could simply generate tables of addresses, phone numbers, countries etc, just from the contact entries.


## PostgreSQL (our PG tips)

PostgreSQL is an object-relational database management system.

### Data types

<table class="table table-bordered">

<tbody>

<tr>

<th>Name</th>

<th style="width:75px;">Storage Size</th>

<th style="width:175px;">Description</th>

<th>Range</th>

</tr>

<tr>

<td>smallint</td>

<td>2 bytes</td>

<td>small-range integer</td>

<td>-32768 to +32767</td>

</tr>

<tr>

<td>integer</td>

<td>4 bytes</td>

<td style="width:39%;">typical choice for integer</td>

<td>-2147483648 to +2147483647</td>

</tr>

<tr>

<td>bigint</td>

<td>8 bytes</td>

<td>large-range integer</td>

<td>-9223372036854775808 to 9223372036854775807</td>

</tr>

<tr>

<td>decimal</td>

<td>variable</td>

<td>user-specified precision,exact</td>

<td>up to 131072 digits before the decimal point; up to 16383 digits after the decimal point</td>

</tr>

<tr>

<td>numeric</td>

<td>variable</td>

<td>user-specified precision,exact</td>

<td>up to 131072 digits before the decimal point; up to 16383 digits after the decimal point</td>

</tr>

<tr>

<td>real</td>

<td>4 bytes</td>

<td>variable-precision,inexact</td>

<td>6 decimal digits precision</td>

</tr>

<tr>

<td style="width:23%;">double precision</td>

<td>8 bytes</td>

<td>variable-precision,inexact</td>

<td>15 decimal digits precision</td>

</tr>

<tr>

<td>smallserial</td>

<td>2 bytes</td>

<td>small autoincrementing integer</td>

<td>1 to 32767</td>

</tr>

<tr>

<td>serial</td>

<td>4 bytes</td>

<td>autoincrementing integer</td>

<td>1 to 2147483647</td>

</tr>

<tr>

<td>bigserial</td>

<td>8 bytes</td>

<td>large autoincrementing integer</td>

<td>1 to 9223372036854775807</td>

</tr>

</tbody>

</table>



### Installation

#### MacOS

Go to http://www.postgresapp.com and follow the instructions to install PostgreSQL on Mac. We recommend using this link to download over homebrew, it was much easier.

#### Linux

To install PostgreSQL on Ubuntu, follow the instructions on the postgresql website:
http://www.postgresql.org/download/linux/ubuntu/

We found it necessary to use the **PostgreSQL Apt repository**, following instructions lower down the page.

### Working with PostgreSQL from the command line.

#### Creating a database

In Ubuntu we found it easiest to follow this guide to get PostgreSQL running once we'd installed it.
https://help.ubuntu.com/community/PostgreSQL#Alternative_Server_Setup

Create a database by entering the following in the

```
createdb [database name]
```

#### Creating table

```sql
CREATE TABLE IF NOT EXISTS films(
    filmid SERIAL
   title text,
   year int,
   directorid int references directors(directorid),
   rating int
);
```
This command creates a table called 'films'. It is a command which defines the database, it is known as the database *schema*.

The *filmid* field has been given datatype SERIAL which gives it a unique auto-incrementing integer value.

The *directorid* field has been assigned as a foreign key, referencing a *directorid* field in another table called 'directors'

#### Viewing relations

To view the schema you've created, type:
```sql
\dt
```
at your postgres prompt.

#### To add rows to your table
```sql
INSERT INTO films (title, title, year, rating) VALUES
('The Martian', 2015, 'Ridley Scott', 4);
```
This command inserts a row into the table 'films'. Note that we did not need to specify a 'filmid', as this is automatically generate, due to it have type *SERIAL*.
#### Viewing the rows in your table
```sql
SELECT * FROM films;
```
This command views all rows in the table 'films'.

#### Alter table

```sql
ALTER TABLE films
    ALTER filmid TYPE INT;
```
This command would change the field 'filmid' in table 'films' to take type *INT*.

#### Joins

```sql
SELECT * from films
JOIN directors
USING (directorid) WHERE name='Riddley Scott';
```
This command joins the table *directors* to the table *films* selecting all films which were directed by 'Riddley Scott'. This is possible because we assigned  a foreign key in the *films* table, creating a relationship between the two tables.

### Integration with Node

##PG Tips Library
Using PostgresSQL can be used with node with the ["pg"] (https://www.npmjs.com/package/pg module). 

Below is an example of using the 'pg' module to connect to a postgreSQL database and add a table.
```
var pg = require('pg');
var connectionString = process.env.DATABASE_URL || 'postgres://localhost:5432/todo';
// the client method from pg module connects a single client to a postgres instance, run some queries, and disconnect.
var client = new pg.Client(connectionString); 
var query = client.query('CREATE TABLE items(id SERIAL PRIMARY KEY, text VARCHAR(40) not null, complete BOOLEAN)'); //adding the SQL to creat table in database
query.on('end', function() { client.end(); });
```
*handy tip - you may want to open two window of terminal to run the node server and query the postgreSQL database.

The link below is to a short tutorial on creating a simple app using node and postgreSQL database, that we found useful.
http://mherman.org/blog/2015/02/12/postgresql-and-nodejs/#.VhJKDbRVikp

https://github.com/brianc/node-postgres worth visiting the github page of the creator of the 'pg' module, note that there are quite a few open issues at the moment.

#### Object Relational Mapping

It can be very useful to use an ORM when using SQL databases in a Node project. Using an ORM allows you to create, query and manage your SQL database in Node using javascript.
We understand the bookshelf.js is the best one to go with.

### Heroku integration

// No references (!!!!!!!!!!!!!!!!!!!!!!!!!) (idiots)


