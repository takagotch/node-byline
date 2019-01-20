### node-byline
---
https://github.com/jahewson/node-byline

```
npm install byline

npm link

npm test
```

```js
var fs = require('fs');
  byline = require('byline');
var stream = byline(fs.createReadStream('sample.txt', { encoding: 'utf-8' }));
stream.on('data', function(line){
  console.log(line);
});

var fs = require('fs');
  byline = require('byline');
var stream = fs.createReadStream('sample.txt');
stream = byline.createStream(stream);
stream.on('data', function(line){
  console.log(line);
});

var stream = fs.createReadStream('sample.txt');
stream = byline.createStream(stream);
stream.pipe(fs.createWriteStream('nolines.txt'));

var stream = fs.createReadStream('sample.txt');
stream = byline.createStream(stream);
stream.pipe(fs.createWriteStream('nolines.txt'));
var input = fs.createReadStream('LICENSE');
var lineStream = byline.createStream();
input.pipe(lineStream);
var output = fs.createWriteStream('test.txt');
lineStream.pipe(output);

var stream = fs.createReadStream('sample.txt');
stream = byline.createStream(stream);
stream.on('readable', function(){
  var line;
  while(null !== (line =stream.read())){
    console.log(line);
  }
});

bar LineStream = require('byline').LineStream;
var input = fs.createReadStream('sample.txt');
var output = fs.createWriteStream('nolines.txt');
var lineStream = new LineStream();
input.pipe(lineStream);
lineStream.pipe(output);
```

```
// package.json
"dependencies": {
"byline": ">=2.1.0 < 3.0.0"
}
```


