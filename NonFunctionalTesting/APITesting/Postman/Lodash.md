
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
