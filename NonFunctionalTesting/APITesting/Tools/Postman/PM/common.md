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

```javascript
function getPath(url) {
    var pathRegex = /.+?\:\/\/.+?(\/.+?)(?:#|\?|$)/;
    var result = url.match(pathRegex);
    return result && result.length > 1 ? result[1] : ''; 
}
 
function getQueryString(url) {
    var arrSplit = url.split('?');
    return arrSplit.length > 1 ? url.substring(url.indexOf('?')+1) : ''; 
}
 
function getAuthHeader(httpMethod, requestUrl, requestBody) {
    var CLIENT_KEY = 'api_key';
    var SECRET_KEY = 'api_secret';
    var AUTH_TYPE = 'HMAC-SHA256';
    var requestPath = getPath(requestUrl);
    var queryString = getQueryString(requestUrl);
    if (httpMethod == 'GET' || !requestBody || !requestBody.length) {
        requestBody = ''; 
    }
    
    var hashedPayload = CryptoJS.enc.Hex.stringify(CryptoJS.SHA256(requestBody));
    var timestamp = new Date().toISOString().split('.')[0];
    var requestData = [httpMethod, requestPath, queryString, timestamp, hashedPayload].join(" ");
    var hashedRequestData = CryptoJS.enc.Hex.stringify(CryptoJS.SHA256(requestData));
    var hmacDigest = CryptoJS.enc.Hex.stringify(CryptoJS.HmacSHA256(hashedRequestData, SECRET_KEY));
    var authHeader = AUTH_TYPE + ', ' + timestamp + ", " + CLIENT_KEY + ', ' + hmacDigest;
    return authHeader;
}
 
postman.setEnvironmentVariable('hmacAuthHeader', getAuthHeader(request['method'], request['url'], request['data']));
```

```javascript
******Encode*****

var val = "To be Encoded";
var arr = CryptoJS.enc.Utf8.parse(ban);
var base64 = CryptoJS.enc.Base64.stringify(arr);
pm.environment.set("To be used in Parameter", base64);


******Decode*****

var en-text = CryptoJS.enc.Base64.parse(base64);
var de-text = en-text.toString(CryptoJS.enc.Utf8);
pm.environment.set("To be used in Parameter", de-text);
```



//refresh token script
```javascript
pm.sendRequest({
    url: pm.environment.get('keycloakHost')+"/auth/realms/"+pm.environment.get('realm')+"/protocol/openid-connect/token",
    method: 'POST',
    header: {
       'Content-Type': "application/x-www-form-urlencoded"
    },
    body: {
        mode: 'urlencoded',
        urlencoded: [
            {key: "client_id", value: pm.environment.get('client_id'), disabled: false, description: {content:"", type:"text/plain"}},
            {key: "client_secret", value: pm.environment.get('client_secret') , disabled: false, description: {content:"", type:"text/plain"}},
            {key: "grant_type", value: "refresh_token" , disabled: false, description: {content:"", type:"text/plain"}},
            {key: "refresh_token", value: pm.environment.get('refresh_token') , disabled: false, description: {content:"", type:"text/plain"}}
        ]
    },
}, function (err, res) {
    postman.setEnvironmentVariable('access_token', res.json().access_token)
    postman.setEnvironmentVariable('refresh_token', res.json().refresh_token)
});
```


```javascript
//save token to enviroment variable (first login)
var jsonData = JSON.parse(responseBody)
postman.setEnvironmentVariable('access_token', jsonData.access_token)
postman.setEnvironmentVariable('refresh_token', jsonData.refresh_token)



// Extract x-auth-token and set as environment variable.
var headers = pm.response.headers.all()
for (var i = 0; i < headers.length; i++) {
    if (headers[i].key == 'x-auth-token') {
        pm.environment.set("x-auth-token", headers[i].value);
    }
}
```

```javascript
var api_key = "xxxxxxxxx";
var name = "Hammad";
var apiSecret = "xxxxxxxxxxxx";
var request_timestamp = Math.floor( Date.now() / 1000 );

var stringToSign = "/users/create?api_key="+api_key+"&name="+name+"&request_timestamp="+request_timestamp;
console.log(stringToSign)

var hmac = CryptoJS.algo.HMAC.create(CryptoJS.algo.SHA256, apiSecret); 
hmac.update(stringToSign); 
var hash = hmac.finalize().toString(CryptoJS.enc.Hex);
console.log(hash);

pm.environment.set("request_timestamp", request_timestamp);
pm.environment.set("signature", hash);
pm.environment.set("api_key", api_key);
pm.environment.set("name", name);
```


# Exception Handling
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

try {
    
    let response = pm.response.json();
    
    // if state is off, turn on state, otherwise update the effect
    if (!response.state.on.value) {
        console.log("Nanoleaf is off. Set next request to turn on.");
        postman.setNextRequest("Quickstart: Update on/off");
    } else {
        console.log("Nanoleaf is on. Set next request to list effects.");
        postman.setNextRequest("Quickstart: List Effects");
    }
    
}
catch (e) {
    throw (e);
}



pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Set auth token", function () {
    
    if (pm.response.to.have.status(200)) {
        
        // set the auth token as an environment variable
        let token = pm.response.json().auth_token;
        pm.environment.set("authToken", token);
        
    } else {
        
        // log status code and reason, terminate collection run
        console.log('Status code: ', pm.response.code);
        console.log('Reason: ', pm.response.reason);
        postman.setNextRequest(null);
        return -1;
    }
    
});
```

## terminate collection run
```javascript
pm.environment.unset("nextEffect");

postman.setNextRequest(null);



pm.test('the "foo1" cookie has correct value', function () {
    pm.expect(pm.cookies.toObject()).to.have.property('foo1', 'bar1');
});


// additional sanity tests
pm.test("status in response body must match the one in request", function () {
    pm.response.to.have.jsonBody('status', Number(_.get(pm.request, 'url.path[1]')));
});

pm.test("response should take more time than the delay specified", function () {
    pm.expect(pm.response.responseTime).to.be.above(Number(_.get(pm.request, 'url.path[1]')));
});


pm.test('requesting http client should accept compressed response', function () {
    pm.expect(pm.response.json()).to.have.nested.property('headers.accept-encoding')
        .and.to.match(/.*gzip.*/);
});
```

# Regex
```javascript
pm.test("response must return a valid ip address", function () {
    pm.expect(pm.response.json().ip).to
        // a really gnarly regular expression to ensure that ip address is in correct format
        .match(/^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$/);
});

pm.test("Returns 7 char alphanumeric id", function () {
    let jsonData = pm.response.json();
    pm.expect(jsonData.form.someHash).to.match(/^[a-z0-9]{7}$/);
});



var authenticateHeader = postman.getResponseHeader('WWW-Authenticate'),
    realmStart = authenticateHeader.indexOf('"',authenticateHeader.indexOf("realm")) + 1 ,
    realmEnd = authenticateHeader.indexOf('"',realmStart),
    realm = authenticateHeader.slice(realmStart,realmEnd),
    nonceStart = authenticateHeader.indexOf('"',authenticateHeader.indexOf("nonce")) + 1,
    nonceEnd = authenticateHeader.indexOf('"',nonceStart),
    nonce = authenticateHeader.slice(nonceStart,nonceEnd);
```	
	

# Schema Validation
```javascript
var schema = {
  "items": {
    "type": "boolean"
  }
};

var data1 = [true, false];
var data2 = [true, 123];

pm.test('Schema is valid', function() {
  pm.expect(tv4.validate(data1, schema)).to.be.true;
//   pm.expect(tv4.validate(data2, schema)).to.be.true; // this statement would not be true
});
```


	


https://github.com/r1990v/Postman_LearnAPI

https://github.com/avin3sh/postmanHacks/blob/master/cleanFileNames.js
https://github.com/ximik3/postman-signing/blob/master/pre-request_script.js
https://github.com/sureshnath/postman-global-scripts/blob/master/postman-logging-with-level.js
https://github.com/digipolisantwerp/common-api-tests_js

https://github.com/pts-mattdeluco/postman

https://github.com/TAMULib/postman-scripts

https://github.com/Anirban-Talukder/POSTMAN/blob/master/Greenhouse-QA.zip

https://github.com/lposs/postman-scripts
