
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

### Asserting Datatype
```javascript
pm.expect(response.id).to.be.a(‘number’);
pm.expect(response.name).to.be.a(‘string’);
pm.expect(response.isDeleted).to.be.a(‘boolean’)
pm.expect(response.isDeleted).to.be.a(‘null’)
pm.expect(response.isDeleted).to.be.a(‘object’)
pm.expect(element.id).to.be.an('array');
```

### Asserting Length
```javascript
pm.expect(pm.response.json().length).to.be.greaterThan(3401);
```


### pm.response
```javascript
pm.response.code:Number
pm.response.reason():Function → String
pm.response.headers:HeaderList
pm.response.responseTime:Number
pm.response.text():Function → String
pm.response.json():Function → Object
```

### pm.expect
```javascript
pm.response.to.have.status(code:Number)
pm.response.to.have.status(reason:String)
pm.response.to.have.header(key:String)
pm.response.to.have.header(key:String, optionalValue:String)
pm.response.to.have.body()
pm.response.to.have.body(optionalValue:String)
pm.response.to.have.body(optionalValue:RegExp)
pm.response.to.have.jsonBody()
pm.response.to.have.jsonBody(optionalExpectEqual:Object)
pm.response.to.have.jsonBody(optionalExpectPath:String)
pm.response.to.have.jsonBody(optionalExpectPath:String, optionalValue:*)
pm.response.to.have.jsonSchema(schema:Object)
pm.response.to.have.jsonSchema(schema:Object, ajvOptions:Object)
```

### pm.response.to.be.*
```javascript
pm.response.to.be.info
pm.response.to.be.success
pm.response.to.be.redirection
pm.response.to.be.clientError
pm.response.to.be.serverError
pm.response.to.be.error
pm.response.to.be.ok
pm.response.to.be.accepted
pm.response.to.be.badRequest
pm.response.to.be.unauthorized
pm.response.to.be.forbidden
pm.response.to.be.notFound
pm.response.to.be.rateLimited
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



var timeInSeconds = parseInt((new Date()).getTime() / 1000);
var sigString = postman.getGlobalVariable("apiKey") + postman.getGlobalVariable("secretKey") + timeInSeconds
var token = CryptoJS.SHA256(sigString);
postman.setGlobalVariable("token", token);



### Code reuse between requests

postman.setGlobalVariable("loadHelpers", function loadHelpers() {
    let helpers = {};
 
    helpers.verifyCount = function verifyCount(expectedCount) {
        var jsonData = JSON.parse(responseBody);
        tests["Response count is: " + expectedCount] 
            = jsonData.length === expectedCount;
    }
 
    // ...additional helpers
 
    return helpers;
} + '; loadHelpers();');




//Then from other requests helpers are taken from global variables and verification functions can be used:
var helpers = eval(globals.loadHelpers);
helpers.verifyCount(4);


### Loop
var jsonData = JSON.parse(responseBody);
var expectedCount = 4
tests["Response count is: " + expectedCount] = jsonData.length === expectedCount;
 
for(var i=1; i<=expectedCount; i++) {
    tests["Verify id is: " + i] = jsonData[i-1].id === i;
}

### null
pm.expect(pm.response.json().name).to.equal("Transformers")
pm.expect(pm.response.json().id).to.be.not.null 
m.response.json().id


### Adding a GET Request

http://localhost:8082/spring-boot-rest/auth/foos/{{id}}

pm.expect(pm.response.json().id).to.equal(pm.variables.get("id"))



### How find object in array by property value?

{
    "companyId": 10101,
    "regionId": 36554,
    "filters": [
        {
            "id": 101,
            "name": "VENDOR",
            "isAllowed": false
        },
        {
            "id": 102,
            "name": "COUNTRY",
            "isAllowed": true
        },
        {
            "id": 103,
            "name": "MANUFACTURER",
            "isAllowed": false
        }
    ]
}
 
pm.test("Check the country filter is allowed", function () {
    // Parse response body
    var jsonData = pm.response.json();

    // Find the array index for the COUNTRY
    var countryFilterIndex = jsonData.filters.map(
            function(filter) {
                return filter.name; // <-- HERE is the name of the property
            }
        ).indexOf('COUNTRY'); // <-- HERE is the value we are searching for

    // Get the country filter object by using the index calculated above
    var countryFilter = jsonData.filters[countryFilterIndex];

    // Check that the country filter exists
    pm.expect(countryFilter).to.exist;

    // Check that the country filter is allowed
    pm.expect(countryFilter.isAllowed).to.be.true;
});


### How find nested object by object name

{
    "id": "5a866bd667ff15546b84ab78",
    "limits": {
        "59974328d59230f9a3f946fe": {
            "lists": {
                "openPerBoard": {
                    "count": 13,
                    "status": "ok", <-- CHECK ME
                    "disableAt": 950,
                    "warnAt": 900
                },
                "totalPerBoard": {
                    "count": 20,
                    "status": "ok",  <-- CHECK ME
                    "disableAt": 950,
                    "warnAt": 900
                }
            }
        }
    }
}

function findObjectContaininsLists(limits) {
    // Iterate over the properties (keys) in the object
    for (var key in limits) {
        // console.log(key, limits[key]);
        // If the property is lists, return the lists object
        if (limits[key].hasOwnProperty('lists')) {
            // console.log(limits[key].lists);
            return limits[key].lists;
        }
    }
}

### How to compare value of a response with an already defined variable?
// Getting values from response
var jsonData = pm.response.json();
var username = jsonData.userName;

// Saving the value for later use
pm.globals.set("username", username);


pm.test("Your test name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.value).to.eql(pm.globals.get("username"));
});

### How to compare value of a response against multiple valid values?
{
    "SiteId": "aaa-ccc-xxx",
    "ACL": [
        {
            "GroupId": "xxx-xxx-xx-xxx-xx",
            "TargetType": "Subscriber"
        }
    ]
}

pm.test("Should be subscriber or customer", function () {
    var jsonData = pm.response.json();
    pm.expect(.TargetType).to.be.oneOf(["Subscriber", "Customer"]);
});


### How to parse a HTML response to extract a specific value?


<form name="loginForm" action="/login" method="POST">
        <input type="hidden" name="_csrf" value="a0e2d230-9d3e-4066-97ce-f1c3cdc37915" />
        <ul>
            <li>
                <label for="username">Username:</label>
                <input required type="text" id="username" name="username" />
            </li>
            <li>
                <label for="password">Password:</label>
                <input required type="password" id="password" name="password" />
            </li>
            <li>
                <input name="submit" type="submit" value="Login" />
            </li>
        </ul>
</form>


// Parse HTML and get the CSRF token
responseHTML = cheerio(pm.response.text());
console.log(responseHTML.find('[name="_csrf"]').val());

### How to do a partial object match assertion?

pm.test("Should include object", function () {
    var jsonData = pm.response.json();
    var expectedObject = {
        "firstName": "Jane",
        "lastName": "Doe",
        "companyName": "ACME"
    }
    pm.expect(jsonData).to.include(expectedObject);

    // Optional check if properties actually exist
    pm.expect(jsonData).to.have.property('uid');
    pm.expect(jsonData).to.have.property('pid');
});


### Sending asynchronous request
pm.sendRequest("https://staging-server:10000/api/person/viktor", function(err, resp) {
  var person = resp.json();
  pm.test("Person was updated correctly", function() {
    pm.expect(person.city).to.equal("stockholm");
  }
} 



// we can do stuff to the data here to ensure it fits our needs
// for example, perhaps we want to ensure the user is over 18
var age = parseInt(jsonData.results[0].dob.age, 10);
if (age<18) age = age + 18;


### Assert: An array to be empty
pm.expect([2]).to.be.an(‘array’).that.is.empty;

### Verify objects
m.test(“Test Name”, function(){

let a= {

“name” : “Harish”

};

let b= {

“name”  : “Harish”

};

pm.expect(a).to.eql(b);

});


### Loop
for(i=0; i < response.body.length; i++) {
          console.log(response.body[i])
          response.body[i].should.have.property('id')
      }



// expect interface
expect(response).to.have.header('content-type', 'application/json');

// should interface
response.should.have.header('content-type', 'application/json');



var responseJSON = pm.response.json();
for(i=0; i< pm.response.json().length;i++){
	console.log(responseJSON[i].organizationTypeID);
}


pm.sendRequest({
    url: pm.environment.get("api-url") + 'v1/authenticate',
    method: 'POST',
    header: {
        'content-type': 'application/json',
        'x-site-code': pm.environment.get("x-site-code")
    },
    body: {
        mode: 'raw',
        raw: JSON.stringify({ email: pm.environment.get("email"), password: pm.environment.get("password") })
    }
}, function (err, res) {
    pm.environment.set("authorization", "Bearer " + res.json().token);
});


pm.sendRequest({
      url:  pm.environment.get("OAUTH_URL")+"/uaa/oauth/token", 
      method: 'POST',
      header: {
        'Accept': 'application/json',
        'Content-Type': 'application/x-www-form-urlencoded',
        'Authorization': 'Basic Abcdefghijk=='
      },
      body: {
          mode: 'urlencoded',
          urlencoded: [
            {key: "grant_type", value: "password", disabled: false},
            {key: "username", value: pm.environment.get("OAUTH_USERNAME"), disabled: false},
            {key: "password", value: pm.environment.get("OAUTH_PASSWORD"), disabled: false}
        ]
      }
  }, function (err, res) {
        pm.globals.set("token", res.json().access_token);
  });

# on a pre-run script

pm.environment.set("token", pm.environment.get("admin_token"));

pm.sendRequest({
    url: "http://127.0.0.1:5000/api/toggles/{{$guid}}", // PM dynamic var
    method: "PUT",
    header: {
        "Content-Length": "1",
        "Authorization": "Bearer {{token}}",
        "Content-Type": "application/json"
    },
    body: {},
    function (err, res) {
        pm.environment.set("toggle_id", res.json().name)
    }
});


