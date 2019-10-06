
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
