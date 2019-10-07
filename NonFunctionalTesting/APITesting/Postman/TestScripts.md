https://postman-quick-reference-guide.readthedocs.io/en/latest/dynamic-variables.html

```javascript
pm.test()

pm.test("Test Description", function () {
    
})
```

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

expect('foo').to.be.a('string');
expect({a: 1}).to.be.an('object');
expect(null).to.be.a('null');
expect(undefined).to.be.an('undefined');
expect(new Error).to.be.an('error');
expect(Promise.resolve()).to.be.a('promise');
expect(new Float32Array).to.be.a('float32array');
expect(Symbol()).to.be.a('symbol');

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
pm.response.to.be.json;
```

### pm.expect
```javascript
pm.expect(pm.response.headers.get("Content-Type")).to.eql("application/json");

pm.expect(jsonData.data.owner).to.have.property('property_name','property_value)

pm.expect('foo').to.have.lengthOf(3); /
pm.expect(jsonData.data[0].userId).to.exist //check if it is not equal to undefined

pm.expects(pm.response.json().enabled).to.be.true;
pm.expects(pm.response.json().enabled).to.be.false;

pm.expect(pm.response.json().value).to.equal("viktor");
pm.expect(pm.response.text()).to.include("wheeled")
pm.expect(jsonData.name).to.eql('Sand Crawler')

pm.expect(pm.response.code).to.be.oneOf([201,202]);
pm.expect(pm.response.json().value).to.eql(12345);
pm.expects(pm.response.json().value).to.equal(10);
pm.expect(pm.response.json().value).to.be.below(100);
pm.expects(pm.response.json().value).to.be.within(1, 20);
pm.expects(pm.response.json().values).to.be.empty;
pm.expect(pm.response.json().values).not.empty;
pm.expects(pm.response.json().values).to.have.lengthOf(5);
pm.expects(pm.response.json().values).to.have.lengthOf.above(5);
pm.expect(jsonData.data.length).to.be.above(0);

pm.expect(token).not.to.eql(null)
pm.expect(jsonData.data[0].userId).to.not.be.null; //if it is not equal to null

pm.expect(json).to.have.property('userId');
pm.expect(json).to.have.property('id');
pm.expect(json).to.have.property('title');
pm.expect(json).to.have.property('bady');

\\Verifying request
pm.expect(req).to.have.param('orderby', 'date');
pm.expect(req).to.not.have.param('orderby');
pm.expect(req).to.have.cookie('session_id', '1234');
pm.expect(req).to.not.have.cookie('PHPSESSID');


\\Verifying Response body
pm.expect(response).to.be.json;
pm.expect(response).to.be.html;
pm.expect(response).to.be.text;


\\Verifying Header information
expect(response).to.have.status(500);
expect(response).to.have.header('x-api-key');
expect(response).to.have.header('content-type', 'text/plain');
expect(request).to.have.header('content-type', /^text/);
expect(response).to.have.header('content-type', 'application/json; charset=utf-8');
expect(response).to.have.headers;



expect('127.0.0.1').to.be.an.ip;
```


### pm.response
```javascript
pm.response.to.have.jsonBody("");
pm.response.to.not.have.jsonBody("error")


pm.response.to.have.property(‘status’, ‘OK’);
pm.response.to.have.header(“Content-Type”);


pm.response.to.not.be.error;
pm.response.to.be.error

pm.response.to.have.jsonBody("");
pm.response.to.not.have.jsonBody("error")




response.should.have.status(200); 
response.body.should.not.be.empty;
response.ok.should.be.true;            // sucess with code 2XX
response.error.should.be.true; //failures

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
```javascript
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
```

### Loop
```javascript
var jsonData = JSON.parse(responseBody);
var expectedCount = 4
tests["Response count is: " + expectedCount] = jsonData.length === expectedCount;
 
for(var i=1; i<=expectedCount; i++) {
    tests["Verify id is: " + i] = jsonData[i-1].id === i;
}
```

```javascript
pm.test("Loop Data", function () {
    
    var responseParentJSON = pm.response.json().modelList;

    responseParentJSON.forEach(result => {
        pm.expect(result).to.be.a('object').and.have.keys(listKey);

        let rn = result.roleName;
        console.log(rn);
        console.log('${rn.replace(" ", "")}@example.com');
        
    });

})
```



### null
```javascript
pm.expect(pm.response.json().name).to.equal("Transformers")
pm.expect(pm.response.json().id).to.be.not.null 
m.response.json().id
```

### Adding a GET Request
```javascript
http://localhost:8082/spring-boot-rest/auth/foos/{{id}}

pm.expect(pm.response.json().id).to.equal(pm.variables.get("id"))
```


### How find object in array by property value?
```javascript
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
```

### How find nested object by object name
```javascript
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
```

### How to compare value of a response with an already defined variable?
```javascript
// Getting values from response
var jsonData = pm.response.json();
var username = jsonData.userName;

// Saving the value for later use
pm.globals.set("username", username);


pm.test("Your test name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.value).to.eql(pm.globals.get("username"));
});
```

### How to compare value of a response against multiple valid values?
```javascript
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
```

### How to parse a HTML response to extract a specific value?
```javascript

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
```

### How to do a partial object match assertion?
```javascript
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
```

### Sending asynchronous request
```javascript
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
```

### Assert: An array to be empty
```javascript
pm.expect([2]).to.be.an(‘array’).that.is.empty;
```

### Verify objects
```javascript
m.test(“Test Name”, function(){

let a= {

“name” : “Harish”

};

let b= {

“name”  : “Harish”

};

pm.expect(a).to.eql(b);

});

```

### Loop
```javascript
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


    response.body.id.should.equal(12345);
    response.body.age.should.be.above(18).and.below(99);
    response.body.firstName.should.be.a('string').and.not.empty;
    response.body.lastName.should.be.oneOf(['Smith', 'Jones', 'Robinson']);



https://postman-quick-reference-guide.readthedocs.io/en/latest/dynamic-variables.html
```

### Request creation
```javascript

var requestUrl = pm.environment.get("url") + "/mediaitem/");

pm.sendRequest(requestUrl, function (err, res) {
    // do stuff
});

// Save the object as a variable.
// JSON.stringify will serialize the object so that Postman can save it
pm.globals.set('user', JSON.stringify(user));

{
    "user": {{user}}
    "address": {
        "street": "Foo"
        "number": "2"
        "city": "Bar"
    }
}


function getRandomNumber(minValue, maxValue) {
    return Math.floor(Math.random() * (maxValue - minValue +1)) + min;
}

var myRandomNumber = getRandomNumber(0, 100);
```

### Random
```javascript
console.log(Math.floor(Math.random() * 1000));
console.log(_.random(0, 1000));
```

### How to read links from response and execute a request for each of them?
```javascript
{
    "links": [
        "http://example.com/1",
        "http://example.com/2",
        "http://example.com/3",
        "http://example.com/4",
        "http://example.com/5"
    ]
}

// Parse the response
var jsonData = pm.response.json();

// Check the response
pm.test("Response contains links", function () {
    pm.response.to.have.status(200);
    pm.expect(jsonData.links).to.be.an('array').that.is.not.empty;
});


// Iterate over the response
var links = jsonData.links;

links.forEach(function(link) {
    pm.test("Status code is 404", function () {
        pm.sendRequest(link, function (err, res) {
            pm.expect(res).to.have.property('code', 404);
        });
    });
});
```



### Status Check
```javascript
pm.test("Status code is 200 OK", function () {     
    pm.response.to.have.status(200);  
    pm.response.to.be.success;
    pm.response.to.be.ok;     
});


pm.test("Status code is 302 Moved Temporarily", function () {     
    pm.response.to.have.status(302);
    pm.response.to.be.redirection
});

pm.test("Status code is 400 Bad Request", function () {     
    pm.response.to.have.status(400);     
    pm.response.to.be.clientError;
    pm.response.to.be.badRequest;     
});

pm.test("Status code is 401 Unauthorized", function () {     
    pm.response.to.have.status(401); 
    pm.response.to.be.clientError;    
    pm.response.to.be.unauthorized;
     
});

pm.test("Status code is 404 Not Found", function () {     
    pm.response.to.have.status(404);     
    pm.response.to.be.clientError;
    pm.response.to.be.notFound;     
});

pm.test("Status code is 500 Internal Server Error", function () {
    pm.response.to.have.status(500);
    pm.response.to.be.serverError;
    pm.response.to.have.status("Internal Server Error");
});
```

### Response Header Checks
```javascript
pm.test("Correct Headers Found", function () {
    pm.expect(pm.response.headers.get('Content-Type')).to.eql('application/json')
    pm.response.to.have.header("Date")===(new Date().toISOString());
    pm.response.to.have.header("Content-Length");
  
});
```

### Clear Environment Data
```javascript
pm.environment.clear();
pm.globals.clear();
```



### Data Type

```javascript
    pm.response.json().modelList.forEach(result => {
        pm.expect(result).to.be.a('object').and.have.keys(listKey);
    });
expect( '1' ).to.be.a( 'string' );
expect( 1 ).to.be.a( 'number' );
expect( true ).to.be.a( 'boolean' );
expect( {} ).to.be.an( 'object' );
expect( null ).to.be.a( 'null' );
expect( undefined ).to.be.a( 'undefined' );
expect( null ).to.be.a( 'null' );
expect( [] ).to.be.an( 'array' );
expect( 0/0 ).to.be.a( 'number' );
```
### Compare
```javascript
var o = {};
 
// x is truthy iff !!x is true.
expect( 'John' ).to.be.ok;
expect( true ).to.be.ok;
expect( o ).to.be.ok;
expect( 1 ).to.be.ok;
expect( 0 ).to.be.not.ok;

// y is falsy iff !!x is false.     
expect( null ).to.be.not.ok;
expect( o.member ).to.be.not.ok;
expect( "" ).to.be.not.ok;  
```
http://www.zsoltnagy.eu/writing-automated-tests-with-mocha-and-chai/


### satisfy
```javascript
expect(1).to.satisfy(function(num) { return num > 0; });

yourVariable.should.satisfy(function (num) {
    if ((num === 4) || (num === 5)) {
        return true;
    } else {
        return false;
    }
});


// delete all products, need token with admin role to complete this operation
pm.test("response is ok and should delete all products", function() {
pm.expect(pm.response.code).to.satisfy(function (status) {
       if ((status === 204) || (status === 404)) {
           return true;
       } else {
           return false;
       }
    });
});

```
### With in or oneOf
```javascript
expect(7).to.be.within(5,10);
expect(1).to.be.oneOf([1, 2, 3]);
expect(1).to.not.be.oneOf([2, 3, 4]);
```	
