
# Awesome JSON
* https://github.com/burningtree/awesome-json

# Online JSON Tools 
* https://onlinejsontools.com/ - Online json tools world's simplest json utilities
* http://jsonpath.com/ - JSONPath Online Evaluator
* http://jsoneditoronline.org/ - JSON tree stucture
* https://codebeautify.org/jsonviewer - JSON tree stucture
* https://jsonlint.com/
* https://codebeautify.org/json-tools - JSON Tools
* https://reviews.thewindowsclub.com/online-json-tools
* https://www.freeformatter.com/ - Free Online Tools For Developers
* https://www.freeformatter.com/json-escape.html - JSON Escape - 
* https://www.csvjson.com/csv2json - Online tool to convert your CSV or TSV formatted data to JSON.
* https://www.json-generator.com/ - JSON Genertor
* https://www.cleancss.com/json-minify/
* https://json-to-js.com/ - Convert JSON to JavaScript object

# Online Schema JSON Tools
* https://www.jsonschema.net/ - Create schema for JSON
* https://www.jsonschemavalidator.net/ - An online, interactive JSON Schema validator. 
* https://easy-json-schema.github.io/ - 
* https://json-schema-validator.herokuapp.com/
* https://www.liquid-technologies.com/online-json-to-schema-converter

JSON Data - A Name and a Value

```json
-- Data is in name/value pairs
{ "name":"John" }

{name: "John", age: 31, city: "New York"};
```

JSON Values
In JSON, values must be one of the following data types:

## JSON data types
a string
a number
an object (JSON object)
an array
a boolean
null

```json

{"employees":[
    { "firstName":"John", "lastName":"Doe" },
    { "firstName":"Anna", "lastName":"Smith" },
    { "firstName":"Peter", "lastName":"Jones" }
]}

JSON Arrays
{
"employees":[ "John", "Anna", "Peter" ]
}

JSON Booleans
{ "sale":true }

myObj = { "name":"John", "age":30, "car":null };


{
"name":"John",
"age":30,
"cars":[ "Ford", "BMW", "Fiat" ]
}

x = myObj.cars[0];
```


```json
//Empty Collection Set
{};

//Single string/value pair
{"abc":"123"};

//Multiple string/value pairs
{"captainsLog":"starDate 9522.6","message":"I've never trusted Klingons, and I never will."};

Valid Numerical Values
-0.01 //valid use of 0's
00.1 //superfluous 0 produces a SyntaxError
1/3 //fraction form
.3333333333333333 //decimal form
1.2e-1 //scientific notation
```


```json
Examples of JSON Text Containing a Variety of Valid JSON Values
// JSON text of an array with primitives
[
null, true, 8
]

// JSON text of an object with two members
{
"first": "Ben"
,
"last": "Smith"
,
}

// JSON text of an array with nested composites
[
{ "abc": "123" },
[ "0"
, 1, 2, 3, 4, 100 ]
]

//JSON text of an object with nested composites
{
"object": {
"array": [true]
}
}
```


A	valid	JSON	document	can	be	either	of	the	following: An	Object	surrounded	by	curly	braces,	{	and	}
An	Array	enclosed	by	brackets,	[	and	]


![](https://www.w3resource.com/w3r_images/json-introduction.png)


```json
{
	"string": "Hello World",
	"number": 123,
	"boolean": true,
	"color": "#82b92c",
	"null": null,
	"array": [
		1,
		2,
		3
	],
	"object": {
		"a": "b",
		"c": "d",
		"e": "f"
	},
	
	"winners":[{
   "winnerId":23,
   "numbers":[2,45,34,23,3,5]
 },{
   "winnerId":54,
   "numbers":[52,3,12,11,18,22]
 }]
	
	
}


{
	"id": "0001",
	"type": "donut",
	"name": "Cake",
	"ppu": 0.55,
	"batters":
		{
			"batter":
				[
					{ "id": "1001", "type": "Regular" },
					{ "id": "1002", "type": "Chocolate" },
					{ "id": "1003", "type": "Blueberry" },
					{ "id": "1004", "type": "Devil's Food" }
				]
		},
	"topping":
		[
			{ "id": "5001", "type": "None" },
			{ "id": "5002", "type": "Glazed" },
			{ "id": "5005", "type": "Sugar" },
			{ "id": "5007", "type": "Powdered Sugar" },
			{ "id": "5006", "type": "Chocolate with Sprinkles" },
			{ "id": "5003", "type": "Chocolate" },
			{ "id": "5004", "type": "Maple" }
		]
}



{ "name"   : "Alice Brown",
  "sku"    : "54321",
  "price"  : 199.95,
  "shipTo" : { "name" : "Bob Brown",
               "address" : "456 Oak Lane",
               "city" : "Pretendville",
               "state" : "HI",
               "zip"   : "98999" },
  "billTo" : { "name" : "Alice Brown",
               "address" : "456 Oak Lane",
               "city" : "Pretendville",
               "state" : "HI",
               "zip"   : "98999" }
}



{
    "firstName": "Grace",
    "lastName": "Hopper",
    "age": 107,
    "address": {
        "streetAddress": "21 2nd Street",
        "city": "New York",
        "state": "NY",
        "postalCode": 10021
    },
    "phoneNumbers": [
        {
            "type": "home",
            "number": "212-555-1234"
        },
        {
            "type": "mobile",
            "number": "646-555-4567"
        }
    ]
}
```
