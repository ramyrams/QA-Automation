
```javascript
var sdk = require('postman-collection'),
      url = new sdk.Url(request.url),
      urlJson = url.toJSON();

console.log(urlJson);
```

```javascript
var fs = require('fs'), // needed to read JSON file from disk
    Collection = require('postman-collection').Collection,
    myCollection;

// Load a collection to memory from a JSON file on disk (say, sample-collection.json)
myCollection = new Collection(JSON.parse(fs.readFileSync('sample-collection.json').toString()));

// log items at root level of the collection
console.log(myCollection.toJSON());
```


http://www.postmanlabs.com/postman-collection/
