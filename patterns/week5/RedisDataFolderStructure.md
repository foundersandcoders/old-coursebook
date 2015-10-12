# Redis Data Types and Folder Structure!

This readme offers __significant__ introductions to Lists, Sets, Sorted Sets and Hashes. This list is not exhaustive: there are many Redis data types, and certain facets of this __byzantine__ underworld shall also be examined in a more superficial fashion.

## Redis Data Types Summary
* Lists: collections of string elements sorted according to the order of insertion. They are basically linked lists
* Sets: collections of unique, unsorted string elements.
Sorted sets: _similar_ to Sets but where every string element is associated to a floating number value, called a __score__. The elements are always taken sorted by their score, so unlike Sets it is possible to retrieve a range of elements (for example you may ask: give me the top 10, or the bottom 10).
* Hashes: maps composed of fields associated with __values__. Both the field and the value are __strings__. This is _very_ similar to javascript objects.
* Bit arrays: it is possible, using special commands, to handle String values like an array of __bits__: you can set and clear individual bits, count all the bits set to 1, find the first set or unset bit, and so forth.
* HyperLogLogs: this is a probabilistic data structure which is used in order to estimate the cardinality of a set. Don't be scared, it is simpler than it seems... See later in the HyperLogLog section of this tutorial
* For a list of commands for these data types, please refer to a previous FAC readme [here](https://github.com/FAC6/book/blob/master/patterns/week4/redisCheatsheet.md)

## Translating between Redis and Node-redis commands

Most Redis command used at the Redis Command line can be implemented through __Node__ :+1::+1:

The basic structure is the following:
```
REDIS-COMMAND Arguments

client.”REDIS-COMMAND”(Arguments)
```
At the Redis command line the _Arguments_ are separated by spaces whilst in Node the Arguments are separated by commas. In the Redis documentation, to set a new hash, the HSET command is explained:

#### Example 1
```
redis> HSET hashkey hashtest1 "Some value"
```
To use this command in Node-redis, write it as follows:
```
client.hset("hashkey", "hashtest 1", "Some value", function(err, reply){} );
```
#### Example 2

Redis has a function called ```DBSIZE``` that tests the size of the whole db :open_mouth:. As such, this function does not take any _arguments_. For example, if the Redis function returns something from the database in order to return a value from the database it is necessary to add a function using the following syntax:

```
client.dbsize(function(err, reply){
           return reply;
});
```
## Strings

* You can use Strings as atomic _counters_ using commands in the INCR family: ```INCR```, ```DECR```, ```INCRBY```
* You can append to strings with the ```APPEND``` command
* You can use Strings as __random access vectors__ with ```GETRANGE``` and ```SETRANGE```
* … and encode a lot of data in __tiny__ space, or create a Redis backed Bloom Filter using ```GETBIT``` and ```SETBIT```! :boom::boom:

## Lists

### Form (A Javascript outline of the list)
```
Key - { number *(unique)* : string }
```
```
eg  { 1: A, 2: B, 3: B} or [A, B, B]
```
### Example (for Node)

The following code in node __creates__ a list and __pushes__ the date to the first position.
```
client.rpush(["Dates", date]);
```
This code returns the entries in the list between the two values.
```
client.lrange('Dates', 0, -1)
```

### Uses
* __Timeline modelling__ a timeline in a social network, using ```LPUSH``` in order to add new elements in the user __timeline__, and using ```LRANGE``` in order to retrieve a few of recently inserted items!
* Keeping lists same length - You can use ```LPUSH``` together with ```LTRIM``` to create a list that never exceeds a __given number__ of elements, but just remembers the _latest_ N elements
* __Lists__ can be used as a message passing primitive - for instance the well known Resque Ruby library for creating background jobs
* You can do a lot more with lists, this data type supports a number of commands, including blocking commands like ```BLPOP```

## Sets

### Form

```
key - { Member *(unique)* }
```

### Example / commands

For a full list of commands see [here](http://redis.io/commands#set)!

This command returns all the members from a particular set in the database:

```
client.smembers('gethSet', function(err, reply) {
1  console.log(reply);
});

```
### Uses
* __Unique visits__ to site - You can track unique things using Redis Sets. Want to know all the unique IP addresses visiting a given blog post? Simply use ```SADD``` every time you process a page view. You are sure repeated IPs will __not be inserted__ :+1:
* Tagging - Redis Sets are good to represent _relations_. You can create a tagging system with Redis using a Set to represent every __tag__. Then you can add all the IDs of all the objects having a given tag into a Set representing this particular tag, using the ```SADD``` command. Do you want all the IDs of all the Objects having a three different tags at the same time? Just use ```SINTER```
* Random elements - You can use Sets to extract elements at random using the ```SPOP``` or ```SRANDMEMBER``` commands

## Sorted sets

### Form
```
Key - { Score (floating point/number) : Member (unique) }
```
### Example

For a full list of Sorted Set commands see [here](http://redis.io/commands#sorted_set)!

The following commands add a value to a sorted set and returns the number of values in that set.
```
client.zadd ('gethSSet', '4', 'Green');

client.zcard ('gethSSet', function(err, reply) {
  console.log(reply);
});
```

### Uses
* Any type of __scoreboard__ - Take a leader board in a massive online game, where every time a new score is submitted you update it using ```ZADD```. You can _easily_ take the top users using ```ZRANGE```, you can also, given an user name, return its rank in the listing using ```ZRANK```. Using ```ZRANK``` and ```ZRANGE``` __together__ you can show users with a score similar to a given user. All verrrrrrry quickly :boom:
* Sorted Sets are often used in order to __index data__ that is stored inside Redis. For instance if you have many hashes representing __users__, you can use a sorted set with elements having the age of the user as the score and the ID of the user as the value. So using ```ZRANGEBYSCORE``` it will be _trivial_ and _fast_ to retrieve all the users with a given interval of ages

## Hashes

Everything in a Redis database is in _key-value pairs_. The value has to take one of the following forms: string, hash, list, set and sorted set.

### Form
```
Key - { Field: value }
```

### Example

```
client.hmset ('user:1000', 'username', 'antirez', 'password', 'P1pp0', 'age', '34');
client.hgetall(‘user:1000’);
HSET user:1000 password 12345
HGETALL user:1000
```

### Uses

* Hashes are structure types containing an unordered table of _keys_ to _values_
* Hashes are great for representing __objects__, because the number of fields (e.g. ‘name’, ‘surname’, ‘age’) you can put inside a hash are unlimited! :+1:
* ```HMSET``` can be used to set multiple fields of the hash. Whilst ```HGET``` can be used to retrieve a single field, ```HMGET``` can be used to return an array of values. There’s a full list of hash commands in the ‘Resources’ section, at the end of this .md file :point_down:
* In a lot of ways, hashes are like _strings_ but they give us a bit more control, and therefore provide a more _accurate_ representation. The benefit would be the ability to _pull_ and _update/delete_ specific pieces of data, without having to get or write the entire value

Redis out! :wave::wave::wave:

# Folder structure 101

__Typically__ a repo root folder will contain files which are _specific_ to where the application will be hosted (e.g. a Heroku Procfile), or _key files_ for the project (LICENSE). Package.json files can be found with full-stack or back-end repos, and __don’t forget__ your README file!

The rest of the files __should__ be located within other folders so people coming across the project know where to look (that is, if you _want_ other people to contribute to your project!). If this is something you are open to, then you can always explain your file structure within your opening readme (without _necessarily_ having an amazing structure).

The __key__ thing to be mindful of is that your __TEAM__ knows your file structure, and that you __stick__ to the structure throughout the project. If your files and folders get out of hand, it will be _difficult_ to stay on top of workflows and avoid merge conflicts with team members working _simultaneously_.  

We’ve found that a lot of folder structure is down to personal opinion. A programmer Derick Bailey lists some rules he follows [here](https://lostechies.com/derickbailey/2012/02/02/javascript-file-folder-structures-just-pick-one/), which we've detailed:

* He puts all his Javascript in one or two files;
* He includes that file or files on every page that uses any Javascript
Those files are cached effectively such that they are only ever downloaded once (until they change);
* ...and Pages call the functions they need from those external files.  

If your site is __20 pages__ and they all use a _little bit_ of Javascript, put it all in one files, include it on every page and call the functions with inline Javascript as necessary in each file


#### Folders by File Type

There are __downsides__ to organising your files according to file type. :-1::-1:  With any application that moves beyond a trivial number of files, these content-type, mime-type, code-type and general type-based folder structures turn in to a __bloated pile of junk__ that is _very_ difficult to sift through. Who wants to look at a folder with 20, 50 or 100 files in it, when you only really care about 2, 5 or 10 of those files? And what happens when you suddenly have an object type that doesn’t fit your pre-established conventions?

However, you might have a JavaScript app that makes use of a templating engine (of which there are _dozens_, these days). It’s not always a good idea to pre-load every possible template in to the user’s browser, for __download size__ and __performance__ reasons. Sometimes it makes sense to fetch the template that you want the first time it’s requested.

#### Folders by File Functions

An _alternative_ is to organize JavaScript files by __functional area of the application__. That is, to group files together in folders based on the area of the application that they facilitate. For example, it is possible to put a very simple model, collection and view definitions that are very closely related, in the same file.

JavaScript in a browser environment really doesn’t care what the _file_ and _folder_ structure is. But that doesn’t mean we as developers shouldn’t care. Pick a file and folder structure that fits the constraints of your application and change the structure as your app’s constraints change.

### How many files should be in your root folder?

Most often we have seen tidy root folders with less than 5 files - these will likely consist of your ‘README.md’, ‘package.json’, ‘.gitignore’, ‘Procfile’ (if you’re using Heroku) and ‘.travis.yml’. If you only have one main webpage, then your html file (e.g. ‘index.html’) will also probably reside in your root directory.

Any more than the above files in the root can make the file structure look a bit messy and Claire or Michelle won’t like it! :wink: It’s best to separate any other files into relevant clusters/folders (e.g. test, public, js, css, etc.).

### What are the best practices for the naming of files?

We have seen a number of different examples of files and folders but some common ones are as such:
```
├── app.js
├── package.json
├── Public
│   ├── img/
│   ├── js/
│   └── css/
├── Routes
├── Views
│   ├── Partials
│   │   ├── sidebar.html
│   │   ├── footer.html
│   │   └── header.html
│   ├── index.html
│   └── page.html
```
### Hapi folder structure
To begin with, the important parts of the structure for now are:
```
package.json
index.js
node_modules/
src/
|-config/
  |-constants.js
|-controllers/
|-dao/
|-middleware/
  |-basic-auth.js
  |-db.js
|-models/
|-routes/
|-util/
|-validate/
```

*package.json: Holds project configuration.
*index.js: The starting point for the API.
*node_modules/: All modules described in package.json will be automatically placed here using npmcommands such as npm install mysql --save.
*src/: Our source code base folder.
*src/config/: Application level configuration files.
*src/config/constants.js: Application level configuration constants.
*src/controllers/: Controllers modules/files.
*src/dao/: Data Access Object modules/files.
*src/middleware/: Holds modules/files that deals with different code environments.
*src/middleware/basic-auth.js: Our Basic Authentication strategy module. We'll see it latter.
*src/middleware/db.js: Abstracts our database initialization and manipulation.
*src/models/: Modules/files abstraction of our database schema.
*src/routes/: Modules/files that know which controllers should handle the incoming requests.
*src/util/: Help us with mixins methods.
*src/validate/: Knows how the incoming request should behave.


 * __test__ - a folder designated for all frontend _and / or_ backend testing
 * __public__ - a folder which usually contains the so-called ‘public’ files in a repo - think index.html or main.css
 * __config__ - usually contains filenames which configure the environment for the application to be run in, so you _may_ find environment variables in this folder
 * __src__ or __lib__ may contain _specific_ resources or libraries which are required to decorate or run the webpage / application. Some SCSS or other styling files _could_ be found here
 * __file names__ shouldn’t be too long (e.g huwmongous.md), but also shouldn’t be __meaningless and short__ (e.g. hm.md). Make sure that the name represents the actual function of the file



### How your folder's tree structure could look :+1::+1:

![repo_3](https://cloud.githubusercontent.com/assets/13470325/10430201/b52b24d0-70f5-11e5-9f9e-1d9da93800df.png)

![repo_2](https://cloud.githubusercontent.com/assets/13470325/10430198/b2dd81a0-70f5-11e5-9ba4-3bc15eaa8fa0.png)

![repo_1](https://cloud.githubusercontent.com/assets/13470325/10430209/bfa23b9c-70f5-11e5-90b4-dde9bbfe2200.png)

![nice structure](https://files.gitter.im/hdrdavies/RedisStructures/26xG/rsz_folderstructure.png)


### RESOURCES
Give redis a go NOW! - <http://try.redis.io/>  
Redis Cheatsheet - <https://github.com/FAC6/book/blob/master/patterns/week4/redisCheatsheet.md>  
Broader summary of data types - <http://redis.io/topics/data-types>  
Redis commands! - <http://redis.io/commands#hash>   
Use cases - <http://stackoverflow.com/questions/7888880/what-is-redis-and-what-do-i-use-it-for>  
Further use cases with scalibility - <http://goo.gl/UB84sG>  
MDN’s Redis tips for devs - <https://developer.mozilla.org/en-US/docs/Mozilla/Redis_Tips>  
More detail on redis commands - <http://openmymind.net/redis.pdf>   
JS File structure -
<https://lostechies.com/derickbailey/2012/02/02/javascript-file-folder-structures-just-pick-one/>
