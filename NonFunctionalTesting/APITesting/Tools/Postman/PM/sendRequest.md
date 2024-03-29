
# sendRequest - raw
```javascript
pm.sendRequest({
    url: 'https://postman-echo.com/post',
    method: 'POST',
     header: {
        'Accept': 'application/json',
        'Content-Type': 'application/x-www-form-urlencoded',
        'Authorization': 'Basic Abcdefghijk=='
    },
    body: {
        mode: 'raw',
        raw: JSON.stringify(
            { 
                key: "this is json" 
                
            }
        )
    }
}, function (err, res) {
    pm.expect(err).to.not.be.ok;
    pm.expect(res).to.have.property('code', 200);
    pm.expect(res).to.have.property('status', 'OK');
    pm.globals.set("token", res.json().access_token);
    pm.environment.set("authorization", "Bearer " + res.json().token);
    console.log(res);
});
```


### sendRequest - urlencoded 
```javascript
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
```
  
### sendRequest - raw - 'application/json'
```javascript
  const echoPostRequest = {
  url: 'https://<my url>.auth0.com/oauth/token',
  method: 'POST',
  header: 'Content-Type:application/json',
  body: {
    mode: 'application/json',
    raw: JSON.stringify(
        {
        	client_id:'<your client ID>',
        	client_secret:'<your client secret>',
        	audience:'<my audience>',
        	grant_type:'client_credentials'
        })
  }
};
```
  
### sendRequest - formdata 
```javascript
pm.sendRequest({
    url: 'https://login.microsoftonline.com/' + tenant + '/oauth2/token',
    method: 'POST',
    header: {
        'Content-Type': 'multipart/form-data',
          },
      body: {
          mode: 'formdata',
          formdata: [
            {key: "client_id", value: client_id},
            {key: "client_secret", value: client_sercret},
            {key: "resource", value: "https://management.azure.com/"},
            {key: "grant_type", value: "client_credentials"},
            
        ]
      }
},  function(err, response) {
  const jsonResponse = response.json();
  pm.environment.set("access_token", jsonResponse.access_token);
});
```


# Automating Web API Authorization in Postman

```javascript
var expiresOn = pm.variables.get('ExpiresOn');
if (!expiresOn || new Date(expiresOn) <= new Date()) {
    var clientId = '51f81489-12ee-4a9e-aaae-a2591f45987d';

    var resource = pm.variables.get('URL');
    var username = pm.variables.get('Username');
    var password = pm.variables.get('Password');

    var request = {
        url: 'https://login.windows.net/common/oauth2/token',
        method: 'POST',
        header: 'Content-Type:application/x-www-form-urlencoded',
        body: {
            mode: 'application/json',
            raw: 'grant_type=password&client_id=' + clientId + '&resource=' + resource + '&username=' + username + '&password=' + password
        }
    };

    pm.sendRequest(request, function (err, res) {
        if (res !== null) {
            var json = res.json();
            pm.environment.set('Access_Token', json.access_token)

            var expiresOn = new Date(0);
            expiresOn.setUTCSeconds(json.expires_on);
            pm.environment.set('ExpiresOn', expiresOn);
        }
    });
}
```



// example with a plain string URL
```javascript
pm.sendRequest('https://postman-echo.com/get', function (err, res) {
    if (err) {
        console.log(err);
    } else {
        pm.environment.set("variable_key", "new_value");
    }
});
```




```javascript

pm.sendRequest({
    url: 'https://postman-echo.com/post',
    method: 'POST',
     header: {
        'Accept': 'application/json',
        'Content-Type': 'application/x-www-form-urlencoded',
        'Authorization': 'Basic Abcdefghijk=='
    },
    body: {
        mode: 'raw',
        raw: JSON.stringify(
            { 
                key: "this is json" 
                
            }
        )
    }
}, function (err, res) {
    pm.expect(err).to.not.be.ok;
    pm.expect(res).to.have.property('code', 200);
    pm.expect(res).to.have.property('status', 'OK');
    pm.globals.set("token", res.json().access_token);
    pm.environment.set("authorization", "Bearer " + res.json().token);
    console.log(res);
});

```
