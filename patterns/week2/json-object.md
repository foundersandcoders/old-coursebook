# JSON and API's

## What?

JSON stands for JavaScript Object Notation. It looks like this:

```javascript
    {"company":"Founders & Coders", "foundername":"Dan Sofer"}
```

## Why?

JSON is **really** useful as although it uses Javascript syntax the format is text only. This means the data can by read by any programming language.

When you make a request to an api for data it will likely be sent back to you in JSON format. You can then access this data and display/manipulate it within your code whatever language you're working in.

## How?

#### JSON values can be:

- A number, string or boolean
- Null
- An array:

```javascript
 "employees":[
    {"firstName":"Katerina", "lastName":"Pascoulis"},
    {"firstName":"Huw", "lastName":"Davies"}
  ]
```
* An object (curly brackets):

```javascript
  {"firstName":"Huw", "lastName":"Davies"}
```

#### To access JSON values

To turn a JSON text into a Javascript object the function JSON.parse() is used. For example:

```javascript
var myJsonText = {"coders":[
   {"firstName":"Katerina", "lastName":"Pascoulis"},
   {"firstName":"Huw", "lastName":"Davies"}] }

var myJavascriptObject = JSON.parse(myJsonText)
```
You can then access this data as below:

```html
<p id=jsondemo> </p>

<script>
document.getElementById("jsondemo").innerHTML =
obj.coders[0].firstName + " " + obj.coders[0].lastName;
</script>
```

To turn your javascript object back into a JSON object the function JSON.stringify() is used:

```javascript

JSON.stringify({ x: 5, y: 6 });
//returns '{"x":5,"y":6}' or '{"y":6,"x":5}'

```

## XML and JSON

#### XML

1. Text-based
2. Position-independent

These reasons encouraged people to use XML as it had a higher level of
application-independence than other data-interchange formats. XML
was already a W3C standard so it was difficult for JSON to win fans.

However, XML is not well suited to data-interchange, and it has a lot of bad features.
JSON has all the advantages of XML but is much more suited to data
interchange.

#### XML vs JSON

##### Simplicity

JSON is **much** simpler. It has a small grammar and maps more directly
onto the data structures used in modern programming languages

##### Readibility

JSON is easier to read than XML, as well as being easier to write. The
same is true for machines as well.

##### Data structures

XML requires converting data structure into a document structure, which
can be complicated. JSON objects are based on arrays and records, which is
what data is made of! Unfortunately, XML structures are based on elements
(nestable), attributes (not nestable), raw text, entities, DTDs and other meta
structures. Not as data-happy as JSON.

###### Orientation

XML is document-orientated, where JSON is data-orientated. JSON can always
be mapped more easily to object-orientated systems.

##### Migration

XML vocabulary is easily converted to JSON, making migration straightforward.
JSON is becoming more popular as time goes on in the computer industry,
partly because the ease and simplicity of making the change from XML to
the now-superior JSON.

