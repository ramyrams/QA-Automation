
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

# Logging / Debugging variables
``` javascript
var myVar = pm.globals.get("myVar");
console.log(myVar);
```

# Local variables
``` javascript
Local variables are only available withing the request that has set them or when using Newman / Collection runner during the entire exection.

When to use:

whenever you would like to override all other variable scopes — for whatever reason. Not sure though then this is needed.
Setting

pm.variables.set('myVariable', MY_VALUE);
Getting

pm.variables.get('myVariable', MY_VALUE);
Removing
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



# Assertion library examples
```javascript
//Assert if substring exists in target
  pm.test("Check if pattern is in target string",function () {
      pm.expect('foobar').to.have.string('bar');
  });
  
//Strict Comparison
  const TEN = 10;
  pm.test('Check if number is equal to 10', function () {
      pm.expect(TEN).to.equal(10);
  });
  
//Loose comparison
  pm.test("Our JSON is loosely equal to the provided JSON", function () {
   pm.expect(data1).to.deep.equal(data2);
  });


//Assert the value of response
  pm.test("Check response value", function () {
      var jsonData = pm.response.json();
      pm.expect(jsonData.value).to.eql(100);
  });
  
//Assert the current environment
  pm.test("Check if environment is production", function () {
      pm.expect(pm.environment.get('env')).to.equal('production');
  });
  
//Assert the type of the target is equal to the given string type
    pm.test("Check if target is string", function () {
     pm.expect('Postman').to.be.a('string');
    });
    pm.test("Check if target is an object", function () {
     pm.expect({a: 1}).to.be.an('object');
    });
    pm.test("Check if target is undefined", function () {
     pm.expect(undefined).to.be.an('undefined');
    });


//Assert if the target is empty
    pm.test("Check if array is empty", function () {
     expect([]).to.be.empty;
    });
    pm.test("Check if string is empty", function () {
     pm.expect('').to.be.empty;
    });
	
	
	pm.test("Check if array is empty", function () {
     pm.expect([]).to.be.an('array').that.is.empty;
    });
	
	
//Assert that the target contains the keys passed
    pm.test("Check if object contains all provided keys", function () {
     pm.expect({a: 1, b: 2}).to.have.all.keys('a', 'b');
    });

    pm.test("Checking if object contains any ONE of the keys", function () {
     pm.expect({a: 1, b: 2}).to.have.any.keys('a', 'b');
    });

    pm.test("Check if object contains any NONE of the provided keys", function () {
     pm.expect({a: 1, b: 2}).to.not.have.any.keys('c', 'd');
    });

//Assert that the target contains said property
    pm.test("Check if object contains the property", function () {
     pm.expect({a: 1}).to.have.property('a');
    });

	pm.test("Check if object contains all the keys", function () {
     pm.expect({a: 1, b: 2}).to.be.an('object').that.has.all.keys('a', 'b');
    });	
	
	
	
//Assert the length of target
    pm.test("Check the length of the target", function () {
     pm.expect('foo').to.have.lengthOf(3);
    });

    pm.test("Check the size of the target", function () {
     pm.expect([1, 2, 3]).to.have.lengthOf(2);
    });
//Assert that the target array has the same members as the given array set
    pm.test("Check if the target has same members as the array set", function () {
     pm.expect([1, 2, 3]).to.have.members([2, 1, 3]);
    });	
	

//Assert that the target contains the provided item
    pm.test("Check if the target array includes the number provided", function () {
     pm.expect([1, 2, 3]).to.include(2);
    });
    pm.test("Check if the target object includes the properties provided", function () {
     pm.expect({a: 1, b: 2, c: 3}).to.include({a: 1, b: 2});
    });

	pm.test("Check if the target is an array that includes the number specified", function () {
     pm.expect([1, 2, 3]).to.be.an('array').that.includes(2);
    });


```

```javascript
pm.test("Your test name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.value).to.eql(100);
});


//Check if status code is 200:
pm.response.to.have.status(200);

//Checking multiple status codes:
pm.expect(pm.response.code).to.be.oneOf([201,202]);

//Response time below 100ms:
pm.expect(pm.response.responseTime).to.be.below(9);


//Header exists:
pm.response.to.have.header(X-Cache');
pm.expect(pm.response.headers.get('X-Cache')).to.eql('HIT');


//Cookie exists:
pm.expect(pm.cookies.has('sessionId')).to.be.true;
pm.expect(pm.cookies.get('sessionId')).to.eql(’ad3se3ss8sg7sg3');

//Any content type / HTML responses
pm.response.to.have.body("OK");
pm.response.to.have.body('{"success"=true}');
Partial body match / body contains:
pm.expect(pm.response.text()).to.include('Order placed.');

## JSON responses
const response = pm.response.json();
pm.expect(response.age).to.eql(30);
pm.expect(response.name).to.eql('John);

//Nested value check:
pm.expect(response.products.0.category).to.eql('Detergent');
```

	

# Postman Echo
```javascript
pm.sendRequest('https://postman-echo.com/time/now', function (err, res) {
    if (err) { console.log(err); }
    else {
        var currentTime = res.stream.toString();
        console.log(currentTime);
        pm.environment.set("currentTime", currentTime);
    }
});
```

# Workflows
```javascript
postman.setNextRequest(“Request name");
postman.setNextRequest(null);
```

	
# XML responses
```javascript
//Convert XML body to JSON:
const response = xml2Json(responseBody);
```


# pm.sendRequest
```javascript
//Allows to send simple HTTP(S) GET requests from tests and pre-request scripts. Example:
pm.sendRequest('http://example.com', function (err, res) {
    console.log(err ? err : res.json());
});

Full-option HTTP(S) request:

const postRequest = {
    url: 'http://example.com', method: 'POST',
    header: 'X-Foo:foo',
    body: {
        mode: 'raw',
        raw: JSON.stringify({ name: 'John' })
    }
};
pm.sendRequest(postRequest, function (err, res) {
    console.log(err ? err : res.json());
});

```


