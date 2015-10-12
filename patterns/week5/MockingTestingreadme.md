# Mocking and testing

## Mocking
** What does mocking mean in relation to testing? **
 - creating objects that simulate the behaviour of real objects e.g. fake redis and shot

** Advantages and disadvantages of mocking **
- your tests won't require use of the real object


# Fake redis #

` npm install fakeredis`

You can use fakeredis as you would use node_redis, just changing the module name from redis to fakeredis.
Read more about it here: https://www.npmjs.com/package/fakeredis

## Advantages
Fake redis helps with writing tests in the following ways:
- your tests won't require an actual redis
- allows you to safely run multiple tests in parallel


## Disadvantages
- the output of some commands e.g. `SMEMBERS`, `HKEYS`, `HVALS` comes out sorted alphabetically to provide for simpler texting. However, this means that some tests that make use of undocumented Redis behaviours such as the chronological order of retrieval for members in a set may fail when attempted with fake redis.

  For example, if items were added to a list in the order Banana, Pear and finally Apple:
The list would appear on fake redis as follows:
`Apple`
`Banana`
`Pear`

  As opposed to the following list on redis:
`Banana`
`Pear`
`Apple`

  This could be an issue e.g. if you are testing that the last data entry gets added to the bottom of the list, this will fail in fake redis.

- There are some missing commands e.g `CONFIG GET`, `CONFIG SET`, `FLUSHALL`.

## How to test your database without mocking

Handler function
```js
var redis = require('redis');

module.exports = function handler(req, res) {
  var url = req.url;
  var urlArray = url.split('/');
  var username = urlArray[2];
  var post = urlArray[3];

  if (req.method === 'POST') {
    client.hmset(username, 'post', post, function(err, reply) {
        console.log('Err >>>>>>>>' + err+ 'REPLY >>>>>>'+reply)
        res.writeHead(200, {
            "Content-Type": "text/html"
        });
        res.end(reply.toString());
    })
}
}
```
Test to see if database has replied 'OK' meaning data entry has been successfully added.
``` js
var shot = require("shot");
var handler = require("./handler.js");
var test = require("tape");
test('have we added an entry to the database', function(test){
  var request = {
    method: 'POST',
    url: "/redistest/"
  };
  shot.inject(handler,request,function (response){
    var results = response.payload;
    test.equal(results , 'OK', 'Test has run')
    test.end();
  })
})
```
