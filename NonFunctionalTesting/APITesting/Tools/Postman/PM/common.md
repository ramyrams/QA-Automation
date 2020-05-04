
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


https://github.com/r1990v/Postman_LearnAPI

https://github.com/avin3sh/postmanHacks/blob/master/cleanFileNames.js
https://github.com/ximik3/postman-signing/blob/master/pre-request_script.js
https://github.com/sureshnath/postman-global-scripts/blob/master/postman-logging-with-level.js
https://github.com/digipolisantwerp/common-api-tests_js

https://github.com/pts-mattdeluco/postman

https://github.com/TAMULib/postman-scripts

https://github.com/Anirban-Talukder/POSTMAN/blob/master/Greenhouse-QA.zip

https://github.com/lposs/postman-scripts
