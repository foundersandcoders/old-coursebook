## When to use REDIS?

- Caching - because of its speed. Redis can store any size of string, it can store any content you need to serve in your app; from simple components to entire pages

- List online people in a chat application the list of people/devices that are connected changes frequently (as people join/leave).

- If you have enough time to think about your DB design

- Sessions in your app (which require a DB/io read on every request but don't contain content) should be checked/set as quickly as possible

- If you need really high performance. Beating the performance Redis provides is nearly impossible

## Who uses REDIS?

- Instagram uses Redis heavily to run their main feed, activity feed and session store

- Github – Github is using Redis for exception handling and queue management

- Stack Overflow uses Redis as a caching layer for their entire network.

Pinterest is a heavy user of Redis. They use it for their follower model, which is their graph of who is following whom

Twitter makes heavy use of Redis, and has open-sourced some of the projects they built internally to take advantage of Redis

Tumblr uses Redis to power dashboard notifications for their tens of millions of users


## REDIS CHEATSHEET

To run redis server in terminal:
``REDIS-SERVER``

To run redis commands in terminal:
``REDIS-CLI``

To create a key and assign it a value
``SET server:name "naaz"``

``GET server:name`` --> result="naaz"

``SET connections 10``

``GET connections`` --> result=10

``INCR connections``. This increases the value of connections by 1 --> result=11

``DECR connections``. This decreases the value of connections by 1

If you want your value to expire after a set period of time, you can use the following:

``SET resource:lock "redis Demo"``

``EXPIRE resource:lock 120`` This causes resource:lock to be deleted in 120 secs

``TTL resource:lock``
This shows you how much time is left before "redis Demo" is deleted from resource:lock

## Lists
A list is a series of ordered values

``RPUSH``
puts the new value at the end of the list e.g. ``RPUSH friends "Alice"``

``LPUSH`` puts the new value at the start of the list e.g. ``LPUSH friends "Sam"``

``LLEN`` returns current length of the list

``LRANGE`` gives a subset of the list - takes the index of the first element you want to retrieves as its first parameter and the index of the last element you want to retrieve as its second parameter. if -1 is the second parameter then retrieves elements until end of the list e.g. ``LRANGE friends 0 -1``

``LPOP`` - removes the first element from the list and returns it
RPOP - removes the last element from the string and returns it

## Set
A set is similar to a list but does not have a specific order and each element may only appear once

``SADD`` adds given value to the set e.g. SADD superpowers "flight"

``SREM`` removes the given value from the set e.g. ``SREM superpowers "reflexes"``

``SISMEMBER`` - tests is the given value is in the set. 1 --> is there. 0--> not there e.g. ``SISMEMBER superpowers "flight"``

``SMEMBERS`` returns a list of all the members of this set, e.g. ``SMEMBERS superpowers``

``SUNION`` combines 2/more sets and returns the list of all elements e.g. ``SUNION superpowers birdpowers``

## Sorted set
A Sorted set is similar to a regular set but each value has an associated score. Score is used to sort elements in the set

E.g.

``ZADD hackers 1940 "Alan Key"``

``ZADD hackers 1906 "Grace Hopper"`` --> here scores are years of the birth and values are the name of famous hackers

``ZRANGE`` e.g. ``ZRANGE 0 1`` --> Grace Hopper, Alan Key

## Hashes

 Hashes are used to store an object. Maps between string fields and string values - perfect data type to represent objects. All hash commands: http://redis.io/commands#hash

e.g.

``HSET user:1000 password "secret"``

``HSET user:1000 email "john.smith@example.com"``

``HMSET`` used to set multiple fields at once e.g. ``HMSET user:1001 name "Mary Jones" password "hidden"``

``HGETALL user:1000`` --> returns password "secret", email "john.smith@example.com"

``HGET`` e.g. ``HGET user:1000 email`` --> returns john.smith@example.com


##Guide to Installing Redis

There are two ways of installing Redis which is open source software. 
Installing Redis has only two dependencies, a working GCC compiler and libc as Redis is written in C.

## Linux/Mac

Pointing to the correct directory in your terminal for your project. Here are the commands to be entered in command line for getting the latest version of Redis. Full instructions can be found on Redis website.
[click here](http://redis.io/topics/quickstart)

		```wget http://download.redis.io/redis-stable.tar.gz
		tar xvzf redis-stable.tar.gz
		cd redis-stable
		make```
		
## Windows/ Virtual box

If you are using windows or a virtual box creating a development environment you may wish to use Vagrant [click here ](https://github.com/docdis/learn-redis) for instructions.

## Which Node Modules ?  

There are a number of npm modules you can install to use with Redis.
Two recommended node modules are:  

https://www.npmjs.com/package/redis.

https://github.com/redis/hiredis-node.

The commands needed to install both modules are : 

```npm install redis hiredis --save```

## Check if Redis is working

External programs talk to Redis using a [TCP](http://searchnetworking.techtarget.com/definition/TCP) socket and a Redis specific protocol. This protocol is implemented in the Redis client libraries for the different programming languages. However to make hacking with Redis simpler Redis provides a command line utility that can be used to send commands to Redis. This program is called redis-cli.
The first thing to do in order to check if Redis is working properly is sending a PING command using redis-cli (Note you need to open a new terminal window for this and the redis needs to be running ```redis-server```).


```$ redis-cli ping
PONG```

Congratulations you have installed Redis!!!
