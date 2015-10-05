#LevelBD

## What are databases?

A database describes the structure in which data can be stored and accessed.

## Why do we need them?

**Size**

Databases allow you to manipulate large amounts of data without opening up a large spreadsheet - if you had 2 million lines of data you wouldn't be able to open it in a spreadsheet.

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



## What is a relational database?

A relational database is built up of data in tabular forms.

For example you may have a table for customer information and a table for employees.
- Each row would represent an employee or customer.
- Each column represents a single attribute of each employee or customer.

With a relational database you can get a row using a key, which is a unique value e.g. social security number, repetition will be disallowed. This unique key could have a computer generated number(synthetic key/ surrogate key).


## What is the difference between an SQL and NoSQL database?

SQL
It stands for Structured Query Language. it s a declarative query language, which used to make queries in databases these tend to be relational databases. You start by writing what you want in broad terms so the algorithm is not specify written out, i.e. select all books over 40 pounds is written as select* from books where list price > £40.

SQL uses the CRUD (create, read, update, delete),
The acronym CRUD refers to all of the major functions that are implemented in relational database applications. Each letter in the acronym can map to a standard SQL statement, HTTP method or DDS operation:

![screenshot from 2015-10-05 14 48 24](https://cloud.githubusercontent.com/assets/13470325/10281996/2ce3dbb0-6b70-11e5-89d7-8bd340e5fb9c.png)

NoSQL (not only SQL)
Typically does not use SQL but may support the language. There is no predefined schema this means that data can be added to the data base in any format. Documents can be stored instead of just updating columns and rows as you would in relational database. You can store data of different compositions i.e. a string or an object. Each document you add to the database has a unique ID.
key values stores are a way of storing data, you have a two column table, with keys in one column with any type of value in the other i.e. string, object ect.
graph data bases are another way of storing data using NoSQL, everything is stored as connected nodes, located in, works in, manages, reports to,  

| **SQL**  | **NoSQL**  |
| ------------- | ------------- |
| Good fit for complex queries (powerful) | Simplicity of Design |
| Vertically scalable | Horizontally scalable  |
| Scale by increasing hardware horse-power | Scaled by increasing the number of database servers |
| More stable → Better fit for heavy duty, transactional type applications | Partition Tolerance <br> ‘Eventually’ consistent - i.e. database changes are propagated to all nodes eventually. <br> ...data loss happens though - not stable enough |
| Predefined Schema | Dynamic schema for unstructured data |
| | Better fit for hierarchical data storage. |
| | Preferred for large data sets (big data). |


# How to use LevelDB

Before downloading make sure you have a package.json file.

Download LevelDB ```npm install level --save```.
This saves it to your package.json under dependencies.

To use LevelDB in your index.js file and create a database:
```
var level = require('level')
var db = level('./db')
```

Then type ```node index.js``` into command line and it will create the db folder.

The basic operations are put(key,value), get(key), delete(key).

Because LevelDB is a key/value data store, every key has to be unique! If they are not the most recent key will overwrite the last.

To put data into this database:

```
db.put('sport','football', function(err) {
    if (err) {
      console.log ('Erorr!')
    }
    else {
      console.log("It worked!")
    }
})
```

Where 'sport' refers to the key and 'football' refers to the value. Then running ```node index.js``` in your command line will add this to the database. Note: nothing will show up in the command line when you do this.

To get this data from the database:

```
db.get('sport', function(err, sport) {
  console.log(sport)
  })
```

Now running ```node index.js``` in the command line should print out the value 'football'.

To delete from the database:
```
db.del('sport', function (err) {

})
```

You can specify a value encoding e.g.
```
var db = level('./db', { valueEncoding: 'json' })
```
This means the value does not have to be a string but instead can look like:
```
db.put('sport', { type: 'football', score: '3-1' }, function(err) {
  db.get('sport', function (err, sport) {
    console.log(sport.score);
  });
});
```
Now running ```node index.js``` will print out '3-1'.

###How does the DB store information? 
LevelDB uses a key / value data store. Keys are sorted lexicographically, this is useful when querying. The basic operations which levelDB uses are Get() Put() Del() and Batch(), these operations manipulate your database a similar way to http requests. The Batch operation links a series of the other operations together, it will either fail or succeed. 

###What are the different data types that can be stored? e.g. strings, lists, hashes, sets
Both the keys and values are stored as simply arrays of bytes, so content can be anything from strings to binary.
###What are the advantages and disadvantages of this database? 
####speed;
This database is very fast and can handle large amounts of data because it is written in the low level language C++. Google’s snappy compression library is an optional dependancy that can decrease the on disk size of levelDB stores with minimal sacrifice of speed. 
####scalability;
LevelDB is scalable as the command base is small but can be added to, by adding packages from node for example the map-reduce package makes it so that when you update one key, only a relevant protion of the data needs to be recalculated. You can also implement something like lambada architecture which help you manage big amounts of data which allows you to query large amounts of data using batches. LevelDB structures data in a noSQL format, so you are not confined to adding data which is structured in a certain way.
####data Structure;
LevelDB provides a highly transparent, light-weight foundation for you to compose higher-level features on top of. For example npm level-js allows you to have the same code running no the server side and the client side so you can see the result of your console.log from the browser.
####query performance;
callers can provide a custom comparison function to override the sort order. One limitation is that this is not an SQL database, so the data model is not relational, this means that SQL language cant be used to query the data. 

###What application areas is it suitable for?
The core functionality of levelDB is quite basic, this has lead to the open source community creating a large amount of packages which can be used to make Levedb useful for a wide selection of applications, this is shown by the difference in the types of companies who are using it.
google: chrome,
Bit coin: blockchain database,
Minecraft: pocket edition,
Autodesk: AutoCAD

Recommended video to watch: https://www.youtube.com/watch?v=sR7p_JbEip0

Recommended reading:

https://en.wikipedia.org/wiki/LevelDB

http://leveldb.org/

http://dailyjs.com/2013/04/18/leveldb-and-node-1/

http://dailyjs.com/2013/05/02/leveldb-and-node-2/

