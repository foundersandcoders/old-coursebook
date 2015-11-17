# JSON and API's

## What?

JSON stands for JavaScript Object Notation. It looks like this:

<pre><code>
    {"company":"Founders & Coders", "foundername":"Dan Sofer"}
</code></pre>

## Why?

JSON is **really** useful as although it uses Javascript syntax the format is text only. This means the data can by read by any programming language.

When you make a request to an api for data it will likely be sent back to you in JSON format. You can then access this data and display/manipulate it within your code whatever language you're working in.
#### JSON values can be:

- A number, string or boolean
- Null
- An array

 <pre><code>"employees":[
    {"firstName":"Katerina", "lastName":"Pascoulis"},
    {"firstName":"Huw", "lastName":"Davies"}
  ]</code></pre>
* An object (curly brackets):

  <pre><code>{"firstName":"Huw", "lastName":"Davies"}</code></pre>


#### To access JSON values
