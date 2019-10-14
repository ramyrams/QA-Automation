

```javascript
var Ajv = require('ajv'),
    // Using the Ajv options
    ajv = new Ajv({logger: console, allErrors: true, verbose: true}),
    // Getting the schema that has been saved as a collection level variable - This has been added to the description for easy viewing
    schema = JSON.parse(pm.variables.get("schema"));

// Validate the Schema against the response body
pm.test('Schema is valid', () => {
    pm.expect(ajv.validate(schema, pm.response.json()), JSON.stringify(ajv.errors)).to.be.true;
});
```

### How to validate json schema using avj and postman
```javascript
    var Ajv = require('ajv'),
    ajv = new Ajv({logger: console}),
    schema = {
        "properties": {
            "errors": {
                "type": "boolean"
            }
        }
    };

pm.test('Schema is valid', function() {
    var error = pm.response.json()['errors'];
    pm.expect(ajv.validate(schema, {errors: error})).to.be.true;
});
```



Data:
```javascript
{
    "errors": false
}
```
Result: Pass

Data:
```javascript
{
    "errors": true
}
Result: Pass
```

Data:
```javascript
{
    "errors": 123
}
Result: Fail
```

### An alternate way
```javascript
pm.test('Schema is valid', function() {
   pm.expect(typeof(pm.response.json().errors) === "boolean").to.be.true;
});
```

