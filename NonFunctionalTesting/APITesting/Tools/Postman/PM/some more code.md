```javascript

pm.environment.set("random_number", _.random(1, 5))



_.each([1, 2, 3], (value, index) => {
  console.log(value)
})

[1, 2, 3].forEach((value, index) => {
  console.log(value)
})

_.forEach({ 'a': 1, 'b': 2 }, (value, key) => {
  console.log(key);
});

({ 'a': 1, 'b': 2 }).forEach((value, key) => { // !error
  console.log(key); 
});





pm.request.url.getQueryString() 

var query = {};
pm.request.url.query.all().forEach((param) => { query[param.key] = param.value});


To get value of specific query parameter:-
pm.request.url.query.get(<Parameter name>)

To get all query parameter as a list:-
pm.request.url.query.all()

To get query string of URI:-
pm.request.url.getQueryString()



pm.request.requestName


To get value of specific path variable :
pm.request.url.variables.get(‘id’);

To get all path variable in a list:
pm.request.url.variables.all();



// To verify if the status code is from a list of expected status code
pm.test("Status code is either 200 or 201", function () {
    pm.expect(pm.response.code).to.be.oneOf([201,200]);
});



//To ignore case sensitive of string
pm.test("Status code contains name", function () {
    pm.expect(pm.response.status.toLowerCase()).to.eql("OK".toLowerCase());
});

// To verify response time is in between
pm.test("Response time is in between 20 and 1200ms", function () {
    pm.expect(_.inRange(pm.response.responseTime, 20, 1201)).to.eql(true);
});

// To verify response size is not zero
pm.test("Response size is not zero", function () {
    pm.expect(pm.response.responseSize).to.not.equal(0);
});

```
