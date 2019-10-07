
//https://lodash.com/docs/4.17.15#find


### Get the first object from the response
```javascript
var user = _.find(pm.response.json(), { 
    firstName: "Jia", 
    lastName: "Test3", 
    branchName: "NZ - Clubware Mobile Test Branch 1" 
})
console.log(user.memberId)
```

### search the perticular object from the response
```javascript
//https://lodash.com/docs/4.17.15#find
pm.test("Verify /api/DepartmentType endpoint is up and running", function(){
var responseJSON = pm.response.json().modelList;

var DeptJSON = _.find(responseJSON, function(o) { return o.departmentID == 1; });

console.log(DeptJSON.departmentName);

});

```

https://medium.com/building-ibotta/testing-arrays-and-objects-with-chai-js-4b372310fe6d

### string manupulation
```javascript
var str = pm.response.json().url
pm.environment.set('value', str.split('=', 2)[1])

_.each(pm.response.json(), (arrItem) => {
    pm.environment.set('value', arrItem[0].url.split('=', 2)[1])
})
```


```javascript
itineraryId = itineraryId.replace("&","&amp;");

var data = JSON.parse(postman.getResponseHeader("Location"));
postman.setEnvironmentVariable("dataObj", data.href.substring(10));
```
```javascript
// Using the _.uniq() function to create a new array within the replicated values
let uniqueAnimals = ["Dog", "Cat", "Dog", "Cow", "Dog", "Lion", "Dog", "Horse"];
pm.globals.set("uniqueAnimals", _.uniq(uniqueAnimals));
```

### How to get to request parameters in Postman?
```javascript
pm.request.url.getQueryString()


var query = {};
pm.request.url.query.all().forEach((param) => { query[param.key] = param.value});
```

https://colintoh.com/blog/lodash-10-javascript-utility-functions-stop-rewriting
http://zetcode.com/javascript/lodash/
https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore#_random
https://medium.com/voobans-tech-stories/10-lodash-functions-everyone-should-know-334b372aec5d








# Iterating over collections
```javascript
var collection = [
 'Lois',
 'Kathryn',
 'Craig',
 'Ryan'
];

_.forEach(collection, function(name) {
 console.log(name);
});

// →
// Lois
// Kathryn
// Craig
// Ryan
```

```javascript
var collection = [
 'Timothy',
 'Kelly',
 'Julia',
 'Leon'
];

_.forEach(collection, function(name, index) {
 if (name === 'Kelly') {
 console.log('Kelly Index: ' + index);
 return false;
 }
});

// → Kelly Index: 1
```


# Sorting data
```javascript
var collection = [
 { name: 'Moe' },
 { name: 'Seymour' },
 { name: 'Harold' },
 { name: 'Willie' }
];
_.sortBy(collection, function(item) {
 return item.name;
});


var collection = [
 { name: 'Clancy', age: 43 },
 { name: 'Edna', age: 32 },
 { name: 'Lisa', age: 10 },
 { name: 'Philip', age: 10 }
];
_.sortBy(collection, [ 'age', 'name' ]);
// →
// [
// { name: "Lisa", age: 10 },
// { name: "Philip", age: 10 },
// { name: "Edna", age: 32 },
// { name: "Clancy", age: 43 }
// ]
```

# Filtering collections
```javascript
var collection = [
 { name: 'Moe', age: 47, gender: 'm' },
 { name: 'Sarah', age: 32, gender: 'f' },
 { name: 'Melissa', age: 32, gender: 'f' },
 { name: 'Dave', age: 32, gender: 'm' }
];

_.where(collection, { age: 32, gender: 'f' });

// →
// [
// { name: "Sarah", age: 32, gender: "f" },
// { name: "Melissa", age: 32, gender: "f" }
// ]




var collection = [
 { name: 'Sean', enabled: false },
 { name: 'Joel', enabled: true },
 { name: 'Sue', enabled: false },
 { name: 'Jackie', enabled: true }
];

_.filter(collection, 'enabled');

// →
// [
// { name: "Joel", enabled: true },
// { name: "Jackie", enabled: true }
// ]






var collection = [
 { type: 'shirt', size: 'L' },
 { type: 'pants', size: 'S' },
 { type: 'shirt', size: 'XL' },
 { type: 'pants', size: 'M' }
];

_.filter(collection, function(item) {
return item.size === 'L' || item.size === 'M';
});

// →
// [
// { type: "shirt", size: "L" },
// { type: "pants", size: "M" }
// ]




var collection = [
 { name: 'Ryan', enabled: true },
 { name: 'Megan', enabled: false },
 { name: 'Trevor', enabled: false },
 { name: 'Patricia', enabled: true }
];
_.reject(collection, { enabled: false });
// →
// [
// { name: "Ryan", enabled: true },
// { name: "Patricia", enabled: true }
// ]
```

# Finding items in collections
```javascript

var collection = [
 { name: 'Derek', age: 37 },
 { name: 'Caroline', age: 35 },
 { name: 'Malcolm', age: 37 },
 { name: 'Hazel', age: 62 }
];
_.find(collection, { age:37 });
// → { name: "Derek", age: 37 }



.findLast(collection, { age:37 });
// → { name: "Malcolm", age: 37 }

```

# Building unique arrays
```javascript
var collection = [
 'Walter',
 'Brenda',
 'Arthur',
 'Walter'
];
_.uniq(collection);
// → [ "Walter", "Brenda", "Arthur" ]
```

# Grouping collection items
```javascript
var collection = [
 { name: 'Lori', size: 'S' },
 { name: 'Johnny', size: 'M' },
{ name: 'Theresa', size: 'S' },
 { name: 'Christine', size: 'S' }
];
_.groupBy(collection, 'size');
// →
// {
// S: [
// { name: "Lori", size: "S" },
// { name: "Theresa", size: "S" },
// { name: "Christine", size: "S" }
// ],
// M: [
// { name: "Johnny", size: "M" }
// ]
// }


var collection = [
 { name: 'Andrea', age: 20 },
 { name: 'Larry', age: 50 },
 { name: 'Beverly', age: 67 },
 { name: 'Diana', age: 39 }
];
_.groupBy(collection, function(item) {
return item.age > 65 ? 'retired' : 'working';
});
// →
// {
// working: [
// { name: "Andrea", age: 20 },
// { name: "Larry", age: 50 },
// { name: "Diana", age: 39 }
// ],
// retired: [
// { name: "Beverly", age: 67 }
// ]
// }
```

# Counting collection items
```javascript
var collection = [
 { name: 'Douglas', age: 52, experience: 5 },
 { name: 'Karen', age: 36, experience: 22 },
 { name: 'Mark', age: 28, experience: 6 }, 
{ name: 'Richard', : age: 30, experience: 16 }
];
_.min(collection, 'age'),
// → { name: "Mark", age: 28, experience: 6 }
_.max(collection, function(item) {
 return item.age + item.experience;
});
// → { name: "Karen", age: 36, experience: 22 }






var collection = [
 { name: 'Gloria' },
 { name: 'Janice' },
 { name: 'Kathryn' },
 { name: 'Roger' }
];
var first = _.first(collection);
_.size(collection); // → 4
_.size(first); // → 1
_.size(first.name); // → 6
```


# Validating some or all items
```javascript
var collection = [
 { name: 'Jonathan' },
 { first: 'Janet' },
 { name: 'Kevin' },
 { name: 'Ruby' }
];
if (!_.every(collection, 'name')) {
return 'Missing name property';
}
// → "Missing name property"
```

# Unions, intersections, and differences
```javascript
var css = [
 'Philip',
 'Donald',
 'Mark'
];
var sass = [
 'Gary',
 'Michelle',
 'Philip'
];
var less = [
 'Wayne',
 'Ruth',
 'Michelle'
];
_.union(css, sass, less);
// →
// [
// "Philip",
// "Donald",
// "Mark",
// "Gary",
// "Michelle",
// "Wayne",
// "Ruth"
// ]




var css = [
 'Rachel',
 'Denise',
 'Ernest'
];
var sass = [ 
'Lisa',
 'Ernest',
 'Rachel'
];
var less = [
 'Ernest',
 'Rachel',
 'William'
];
_.intersection(css, sass, less);
// → [ "Rachel", "Ernest" ]





var sass = [
 'Lisa',
 'Ernest',
 'Rachel'
];
var less = [
 'Ernest',
 'Rachel',
 'William'
];
return _.xor(sass, less);
// → [ "Lisa", "William" ]
```

# Plucking values
```javascript
var collection = [
 { name: 'Virginia', age: 45 },
 { name: 'Debra', age: 34 },
 { name: 'Jerry', age: 55 },
 { name: 'Earl', age: 29 }
];
_.pluck(collection, 'age');
// → [ 45, 34, 55, 29 ]

```



