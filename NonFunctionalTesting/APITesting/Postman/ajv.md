
var Ajv = require('ajv'),
    // Using the Ajv options
    ajv = new Ajv({logger: console, allErrors: true, verbose: true}),
    // Getting the schema that has been saved as a collection level variable - This has been added to the description for easy viewing
    schema = JSON.parse(pm.variables.get("schema"));

// Validate the Schema against the response body
pm.test('Schema is valid', () => {
    pm.expect(ajv.validate(schema, pm.response.json()), JSON.stringify(ajv.errors)).to.be.true;
});
