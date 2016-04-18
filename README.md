mongoose-gridfs
===============

[![Build Status](https://travis-ci.org/lykmapipo/mongoose-gridfs.svg?branch=master)](https://travis-ci.org/lykmapipo/mongoose-gridfs)

mongoose gridfs on top of [gridfs-stream](https://github.com/aheckmann/gridfs-stream)

*Note!: Ensure mongoose connection before use*

## Installation
```sh
$ npm install --save mongoose mongoose-gridfs
```

## Usage
```js
var mongoose = require('mongoose');
var gridfs = require('mongoose-gridfs')(<options>);

//mongoose connect
mongoose.connect('mongodb://localhost/test');

//create or save a file
gridfs.create(<fileDetails>,<readableStream>,function(error,result){
  ...
});

//read a file and receive a stream
var stream  = gridfs.readById(<fileObjectId>);

//read a file and receive a buffer
gridfs.readById(<fileObjectId>,function(error,buffer){
  ...
});

```


## MongoDB `fs.file` Structure
```js
{
  "_id" : <ObjectId>,
  "length" : <num>,
  "chunkSize" : <num>,
  "uploadDate" : <timestamp>,
  "md5" : <hash>,
  "filename" : <string>,
  "contentType" : <string>,
  "aliases" : <string array>,
  "metadata" : <dataObject>,
}
```

## multer `uploaded file` Structure
```js
{
  "fieldname" : <string>,
  "originalname" : <string>,
  "encoding" : <string>,
  "mimetype" : <string>,
  "size" : <num>
}
```


## Literature Reviewed
- [MongoDB GridFS](https://docs.mongodb.org/manual/core/gridfs/)
- [gridfs-stream](https://github.com/aheckmann/gridfs-stream)


## Licence

The MIT License (MIT)

Copyright (c) 2015 lykmapipo & Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE. 