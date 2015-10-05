# MongoDB

![alt text](https://serverdensity-wpengine.netdna-ssl.com/wp-content/themes/blog.new/images/random/mongodb.png)

## What are databases?
Databases can be termed as:
>Organised collections of data which can be used to store information, and in turn manipulated to produce previously stored information

Further back in 'database history', databases used to be flat. Information was stored in one long text file, with fields associated to each record:

>``
Lname, FName, Age, Salary|Smith, John, 35, $280|Doe, Jane, 28, $325|Brown, Scott, 41, $265|Howard, Shemp, 48, $359|Taylor, Tom, 22, $250.
``

It was a pretty inefficient structure as one had to search in sequence through each record to find information. It was also hard to present the data by only displaying some of the fields.

## Why do we need them?

They can be used to support internal operations of organizations and to underpin online interactions with customers and suppliers. They can also hold administrative information and more specialized data, such as engineering data or economic models.

There are many reasons to go with database software rather than your standard Microsoft Excel. As a first point, they are easier to update, so for large companies or other organisations multiple people are able to update them at the same time.

Accuracy is also far improved because you can set rules for what data is to be input and what schema it follows. Finally, security is another of the primary reasons you may plump for a database such as MongoDB- you can set who has access to the data for peace as mind and on another front, all data is protected from being lost even with crashes.

## What is a relational database?
In short, relational databases are linked by virtual keys or IDs between tables which are not stored in the current database (which would be a waste of valuable data space).

![relational diagram](https://upload.wikimedia.org/wikipedia/commons/4/4c/Relational_key_SVG.svg)

## What is the difference between an SQL and NoSQL database?

We found a _verrrrry_ useful table: 

![SQL vs NoSQL table](https://files.gitter.im/foundersandcoders/databases/KfA0/rsz_sqlvsnosql.png)

 * NoSQL doesn’t necessarily mean there is no SQL, it means ‘not only’ SQL
 * The idea of SQL vs. NoSQL and the idea of only needing one is not necessarily true. Many companies implement both models and use them side by side, as there are clearly benefits and shortcomings in both types of database
 * SQL runs on CRUD principle- Create, read, update, delete

### How does MongoDB store information?
MongoDB is a NoSQL, document based database. The smallest unit is a _document_, a number of which is formed into _collections_, which in turn make up a _database_. Not every document has to have the same structure, in keeping with the NoSQL style, and one major appeal of MongoDB is that fields in a document can store _arrays_ or _sub-documents_.

##### A Document! 

![document](https://files.gitter.im/foundersandcoders/databases/xWoB/Document.png)

##### A Collection! 

![collection](https://files.gitter.im/foundersandcoders/databases/6KpM/Collection.png)

### What are the different data types that can be stored?

* Strings
* Integers (32- or 64-bit)
* JavaScript Dates
* Arrays
* Booleans
* Null
* BSON Objects
* BSON Arrays

BSON is a data interchange format used within MongoDB, and is based on __JSON__. BSON stands for Binary JSON, with the difference being that BSON is designed to be efficient both in storage space and scan-speed compared to JSON.

### What are the advantages and disadvantages of this database?
* Speed- MongoDB is generally fast, but the way how you structure and index your documents and collections has a big influence on the performance of your application, so care should be taken here
* Schema-less- MongoDB is a document database, as mentioned above in which one collection holds a number of different documents
* Flexible- the number of fields, content and size of the document can change
* Structure of a single object is clear
* No complex joins- where joins can be complex in SQL
* Deep query ability- MongoDB supports dynamic queries on documents. The user can save, query
and retrieve data as BSON
* Easy scalability
* Internal memory is used for storing the working set, eliciting faster access of data

### What application areas is it suitable for?
Below are some examples of its uses and reasons for why MongoDB is suited to the task:
##### High volume data feeds
* Machine Generated Data
  * More Machines, more sensors, more data
  * Multiple types of structure
* Stock Market Data
  * High Frequency trading
* Social Media Firehoses
  * Multiple sources of data
  * Constant changes in format

##### Product Data
* E-Commerce sites
  * Involves diverse product portfolios
  * Requires complex querying and filtering
* Flash Sales
  * Scales for short bursts of high-volume traffic

##### Content Management
* News sites
  * Suits comments and user generated content
  * Suits personalisation of content and layout

##### User Data Management
* Video Games
  * User state and session management (Used by the FIFA video game series!)

### Who is using MongoDB and what are they using it for?
* LinkedIn is for their backend DB, where they use Voldemort for other areas of their stack. MongoDB is useful here as user profiles can differ hugely in their content, and the site needs to handle large amount of varied search traffic
* CERN uses it as the primary back-end for the Data Aggregation System for the Large Hadron Collider (ooooooh!)
* eBay uses MongoDB in the search suggestion and the internal Cloud Manager State Hub

### How do you install MongoDB?

Here are the links that worked for us:

Walkthrough for Ubuntu [here](http://www.liquidweb.com/kb/how-to-install-mongodb-on-ubuntu-14-04/),
and their official one [here](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/).

Walkthrough for Apple [here](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-os-x/).

You may run into problems installing this on Crouton. See the following information [here](http://stackoverflow.com/questions/28348748/mongodb-xubuntu-crouton-cant-start-service) which will hopefully help.

### How do you access the database from the command line?

Start a server in one terminal window  with the command:

>``mongod``

In another window, begin the MongoDB shell with the command:

>``mongod  --shell``

The database is now accessible from the command line. One can also access MongoDB  through node using the instructions for npm module below. You may need to use ``sudo`` if you have permission problems. 


##### Sidenote!
When importing the test database into MongoDB, you need to change into the directory where your .json data file is saved before you run the ``mongo import`` command. Run it in your command line, not the mongo shell.

### Which npm module should you use for MongoDB?
MongoDB uses one _very originally_ called ``mongodb``. Follow the walkthrough [here](https://docs.mongodb.org/getting-started/node/client/).

### How do you host MongoDB on heroku?
Please follow the link [here](https://github.com/FAC6/book/blob/master/patterns/week3/hostApplicationHeroku.md ) for deploying to Heroku.

After this step is completed, you should add the MongoLab add-on:  
1. Go to your Dashboard and click on the app just created by you  
2. Open the Resources tab and then add a new add-on by…  
3. Clicking on EDIT or PLUS button under Add-ons session  
4. Search for MongoLab, and add it!  

The MongoLab add-on contributes one config variable to your Heroku environment: MONGOLAB_URI. This variable is a URI containing all the MongoDB connection information needed to connect to your database.

### Resources
Relational database information - http://searchsqlserver.techtarget.com/definition/relational-database  
Document databases & Mongo-   http://derickrethans.nl/introduction-to-document-databases.html  
Database popularity rankings (guess who's top out of the 4 we studied!) -   http://db-engines.com/en/ranking  
Using MongoDB with node.js - http://www.smashingmagazine.com/2014/05/detailed-introduction-nodejs-mongodb/

### References
https://en.wikipedia.org/wiki/MongoDB  
http://www.slideshare.net/mongodb/common-use-cases-hannes?next_slideshow=1  
https://scotch.io/tutorials/use-mongodb-with-a-node-application-on-heroku  
