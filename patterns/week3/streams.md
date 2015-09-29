# Streams

There are some core methods within Node.js which allow users to create readable and writable streams.

streams are pipes which allow you to easily read data from a source and pipe it to a destination, a stream is an **eventEmitter** which implements some special methods _(they allow you to listen for events and invoke actions when they occur)_. depending on which methods are used the streams become either readable or writable streams, or even both (duplex)

#### Some Examples;

Opening a read stream on an existing file;
``` javascript
var fs = require('fs');  // file system
var rstream = fs.createReadStream('existingFile');
```

Opening a write stream for storing data in a file;
```javascript
var fs = require('fs');  // file system
var wstream = fs.createWriteStream('fileToWrite');
```

Using streams from http;
```javascript
var http = require('http');
var server = http.createServer(function (req, res) {
  var rstream = fs.createReadStream('existingFile');
  rstream.pipe(res);
});
server.listen(8000, '127.0.0.1');  // start
```
