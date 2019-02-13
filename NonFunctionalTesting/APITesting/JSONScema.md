
https://json-editor.tangramjs.com/editor.html#/
https://json-schema.org/implementations.html

# JSON Schema Validator
https://github.com/everit-org/json-schema

https://www.baeldung.com/introduction-to-json-schema-in-java

# Getting Started Step-By-Step
* http://json-schema.org/learn/getting-started-step-by-step.html

## Tools
* http://jsonvalidate.com/
https://jsonformatter.org/
https://www.jsonschemavalidator.net/
https://json-schema-validator.herokuapp.com/

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/product.schema.json",
  "title": "Product",
  "description": "A product from Acme's catalog",
  "type": "object",
  "properties": {
    "productId": {
      "description": "The unique identifier for a product",
      "type": "integer"
    },
    "productName": {
      "description": "Name of the product",
      "type": "string"
    },
    "price": {
      "description": "The price of the product",
      "type": "number",
      "exclusiveMinimum": 0
    },
	"latitude": {
      "type": "number",
      "minimum": -90,
      "maximum": 90
    },
	"warehouseLocation": {
      "description": "Coordinates of the warehouse where the product is located.",
      "$ref": "https://example.com/geographical-location.schema.json"
    },
	"dimensions": {
      "type": "object",
      "properties": {
        "length": {
          "type": "number"
        },
        "width": {
          "type": "number"
        },
        "height": {
          "type": "number"
        }
      },
      "required": [ "length", "width", "height" ]
    },
	"tags": {
      "description": "Tags for the product",
      "type": "array",
      "items": {
        "type": "string"
      },
      "minItems": 1,
      "uniqueItems": true
    },
    "dimensions": {
      "type": "object",
      "properties": {
        "length": {
          "type": "number"
        },
        "width": {
          "type": "number"
        },
        "height": {
          "type": "number"
        }
      },
      "required": [ "length", "width", "height" ]
    }
  },
  "required": [ "productId", "productName", "price" ]
}
```
