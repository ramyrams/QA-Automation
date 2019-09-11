
# Global variables

### Setting
```javascript
//Set a global variable
pm.globals.set('myVariable', MY_VALUE);
```

### Getting
```javascript
//Get a global variable
pm.globals.get('myVariable');
pm.variables.get('myVariable');
```

### Removing
```javascript
//Clear a global variable
pm.globals.unset('myVariable');
```

```javascript
//Remove ALL global variables (rather unusual)
pm.globals.clear();
```


# Variables
```javascript
var value = pm.variables.get("variable_key");
```

# Response handling

```javascript
//Check if response body contains a string
pm.test("Body matches string", function () {
    pm.expect(pm.response.text()).to.include("string_you_want_to_search");
});

//Check if response body is equal to a string
pm.test("Body is correct", function () {
    pm.response.to.have.body("response_body_string");
});

//Check for a JSON value
pm.test("Your test name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.value).to.eql(100);
});

//Content-Type header is present
pm.test("Content-Type header is present", function () {
    pm.response.to.have.header("Content-Type");
});

//Response time is less than 200ms
pm.test("Response time is less than 200ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(200);
});

//Status code is 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

//Code name contains a string
pm.test("Status code name has string", function () {
    pm.response.to.have.status("Created");
});

//Successful POST request status code
pm.test("Successful POST request", function () {
    pm.expect(pm.response.code).to.be.oneOf([201,202]);
});
```



# Validate response structure
```javascript
//JSON schema validation with tv4
var schema = {
 "items": {
 "type": "boolean"
 }
};
var data1 = [true, false];
var data2 = [true, 123];

pm.test('Schema is valid', function() {
  pm.expect(tv4.validate(data1, schema)).to.be.true;
  pm.expect(tv4.validate(data2, schema)).to.be.true;
});

//JSON schema validation with ajv
var Ajv = require('ajv'),
    ajv = new Ajv({logger: console}),
    schema = {
        "properties": {
            "alpha": {
                "type": "boolean"
            }
        }
    };

pm.test('Schema is valid', function() {
    pm.expect(ajv.validate(schema, {alpha: true})).to.be.true;
    pm.expect(ajv.validate(schema, {alpha: 123})).to.be.false;
});
```



# Encode/decode
### Decode base64 data
```javascript
// Assume `base64Content` has a base64 encoded value
var rawContent = base64Content.slice('data:application/octet-stream;base64,'.length);

// CryptoJS is an inbuilt object, documented here: https://www.npmjs.com/package/crypto-js
var intermediate = CryptoJS.enc.Base64.parse(base64content);
pm.test('Contents are valid', function() {
  pm.expect(CryptoJS.enc.Utf8.stringify(intermediate)).to.be.true; // a check for non-emptiness
});

### Convert XML body to a JSON object
var jsonObject = xml2Json(responseBody);


## Send an asynchronous request
pm.sendRequest("https://postman-echo.com/get", function (err, response) {
    console.log(response.json());
});
```
