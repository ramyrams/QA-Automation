

### Generate UUID
```javascript
var uuid = require('uuid'); 
var myUUID = uuid.v4(); 
console.log(myUUID);
```

//Generate Timestamp
```javascript
const moment = require('moment');
console.log(`Timestamp: ${moment().valueOf()}`);
```

//Generate number
```javascript
var firstName =  '$randomLoremWord';
var ranint = _.random(1000); // Return random number between 0 to 1000
var ranin1 = _.random(15, 20, true); // Return random floating numbers between 15 and 20

console.log(Math.random().toString(36).slice(2));
console.log(Math.random().toString(36).substr(2, 5));

console.log(_.times(20, () => _.random(35).toString(36)).join(''));


console.log("firstName" + firstName);
console.log("ranint" + ranint);
console.log("randomString" + randomString(10));
console.log("randomString A: " + randomString(10, 'A'));
console.log("randomString N: " + randomString(10, 'N'));


console.log("this is from pre" + 3274);
pm.environment.set('IndividualFirstName', 'IndividualFirstName From API {{$randomLoremWord}}');

pm.environment.set('TestUUID', myUUID);


function randomString(len, an){
    an = an&&an.toLowerCase();
    var str="", i=0, min=an=="a"?10:0, max=an=="n"?10:62;
    for(;i++<len;){
      var r = Math.random()*(max-min)+min <<0;
      str += String.fromCharCode(r+=r>9?r<36?55:61:48);
    }
    return str;
}
```
