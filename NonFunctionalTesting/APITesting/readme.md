# API Testing

# Here are some of the most common reasons people test their APIs:
Make sure it does what it’s supposed to do
Make sure it can handle the load
Find all the way users can mess things up
Make sure your APIs work across devices, browsers, and operating systems
It can be costly not to

# What You Need To Start API Testing
Who is your target audience? Who is your API consumer?
What environment/s should the API typically be used?
What aspects are you testing?
What problems are we testing for?
What are your priorities to test?
What is supposed to happen in normal circumstances?
What could potentially happen in abnormal circumstances?
What is defined as a Pass or a Fail? What data is the desired output? What is the chain of events?
What other APIs could this API interact with?
Who on your team is in charge of testing what?

# What Types of API Testing Can I Do?
Functionality testing — the API works and does exactly what it’s supposed to do.
Reliability testing — the API can be consistently connected to and lead to consistent results
Load testing — the API can handle a large amount of calls
Creativity testing — the API can handle being used in different ways.
Security testing — the API has defined security requirements including authentication, permissions and access controls. See some API security tips for protecting vital data
Proficiency testing — the API increases what developers are able to do.
API documentation testing — also called discovery testing, the API documentation easily guides the user.
Negative Testing — checking for every kind of wrong input the user can possibly supply 

# API test examples,
Checking API return values based on the input condition
Verifying if the API doesn’t return anything at all or the wrong results
Verifying if the API triggers some other event or calls another API
Verifying if the API is updating any data structures.

# API Testing Best Practices
Test for the typical or expected results first
Add stress to the system through a series of API load tests
Test for failure. Make sure you understand how your API will fail. Just make sure the API fails consistently and gracefully
Group test cases by test category
Prioritize API function calls so that it will be easy for testers to test quickly and easily
Limit the tests from as many variables as possible by keeping it as isolated as possible
See how it handles unforeseen problems and loads by throwing as much as you can at it
Perform well-planned call sequencing
For complete test coverage, create test cases for all possible API input combinations
Automate wherever you can


# Why API testing frameworks are necessary

# Types of API testing frameworks

Functionality: Does the API work?
Reliability: Can users connect to the API and achieve consistent results?
Load: Does the API load appropriately?
Usability: Is the API easy to work with?
Documentation: Are there documents that guide the user into the purpose of the API and how to use it?

# API TestServer Features
https://smartbear.com/product/ready-api/testserver/features/

# Tools


API TESTING TOOLS: THE ULTIMATE GUIDE 
https://octoperf.com/blog/2018/03/22/api-testing-tools/



14 Open Source API Testing Tools For REST & SOAP Services
https://www.joecolantonio.com/2017/05/16/12-open-source-api-testing-tools-rest-soap-services/

# Finding the right API testing tool
Design and test Mule apps and APIs, graphically or in XML, all within Anypoint Studio
Integrate testing into your existing CI/CD process more easily
Minimize manual work with auto-generated tests and coverage reports
Leverage local DB/FTP/mail servers to make testing more portable through the CI process


* Definition Languages
  * WSDL
  * XSD
  * WADL
  * JSON Schema
  * Swagger
  * OData Definition
* Transport Protocols
  * HTTP(s)
  * JMS
  * Rabbit MQ
  * TIBCO EMS
  * AMQP (Advanced Message Queueing Protocol)
  * IBM MQ
  * NET TCP
  * OData Standard Protocol
* Message Formats
  * XML
  * JSON
  * Text
  * URL Encoded Parameters
* Standards
  * SOAP
  * REST
  * ISO 20022
  * FIXML
  * SWIFT
* Authentication:
  * Basic Authentication
  * Kerberos
  * SPNEGO
  * NTLM


# API testing Checklists

1. HTTP Validations:
* While testing an API, HTTP methods like GET, HEAD, PUT, DELETE etc. are idempotent methods
* Validate user authentication, trying to access an API using HTTP authentication header
* Verifying various error/authentication codes, to ensure validation of a response. Some of the validation codes include 404 (server not found), 201 (request fulfilled), 204 (no content) and so on
* 4xx vs 5xx errors are worth mentioning as they help to reflect client side and server side errors respectively.
* To ensure best network performance, HTTP compression mechanisms should be applied to API’s being tested. (HTTP compression is a technique to facilitate efficient bandwidth between client and the server)

2. API Validations:
* An API must ideally support format conversion, say, JSON to XML or vice versa
* Check with API version number to verify whether that specific version is compatible with the device being used
* An API must be strong enough to handle bulk operations, therefore it is necessary to build an API in such a manner
* Pagination is an important factor that helps to reduce unnecessary computations at the server, as pagination indexes a document in pages
* An API must efficiently handle errors that arise during an application's duration of operation.

3.Content:
* Type of contents such as +JSON, JSON HAL and XTML, should be included while testing an API, is an important aspect from an API testing perspective.
* While taking RESTful API's into consideration, a feature named HATEOAS, an acronym for Hypermedia as the Engine of Application State, is a REST constraint provides an effective way for a client to interact with any network application.
* An API's date and time must adhere to the time zone specifications meant for a particular locale

https://dzone.com/articles/what-is-api-testing-and-are-you-doing-it-right

## Contract Tests
An API represents a contract between 2 or more applications. The contract describes how to interact with the interface, what services are available, and how to invoke them. This contract is important because it serves as the basis for the communication. If there's something wrong with the contract, nothing else really matters.

* The service contract is written according to specifications.
* A message request and response are semantically correct (schema validation).
* The endpoint is valid (HTTP, MQ/JMS Topic/Queue, etc).
* The service contract hasn't changed.

## Component Tests
Component tests are like unit tests for the API - you want to take the individual methods available in the API and test each one of them in isolation. You create these tests by making a test step for each method or resource that is available in the service contract.


* The request payload is well-formed (schema validation).
* The response payload is well-formed (schema validation).
* The response status is as expected (200 OK, SQL result set returned, or even an error if that's what you're going for).
* The response error payloads contain the correct error messages.
* The response matches the expected baseline. This can take two forms:
1. Regression/diff - the response payload looks exactly the same from call to call (a top-down approach where you essentially take a snapshot of the response and verify it every time). This can also be a great catalyst to identify API change (more about that later).
2. Assertion - the individual elements in the response match your expectations (this is a more surgical, bottom-up approach targeted at a specific value in the response).
* The service responds within an expected timeframe.


## Scenario Tests
Scenario testing tends to be what most people think about when they think about API testing. In this testing technique, you assemble the individual component tests into a sequence, much like the example I described above for the Amazon service.

There are two great techniques for obtaining the sequence:
* Review the user story to identify the individual API calls that are being made.
* Exercise the UI and capture the traffic being made to the underlying APIs.



https://www.soapui.org/learn/functional-testing/api-testing-101.html

https://www.guru99.com/testing-rest-api-manually.html

https://github.com/shieldfy/API-Security-Checklist
https://mathieu.fenniak.net/the-api-checklist/
https://dzone.com/articles/what-is-api-testing-and-are-you-doing-it-right
