

# Exception Handling
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


## terminate collection run
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


# Regex
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



	
