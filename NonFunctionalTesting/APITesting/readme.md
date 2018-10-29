

* ![1](https://d585tldpucybw.cloudfront.net/sfimages/default-source/productsimages/teststudio/apis/codessly-test-your-apis.png)
* ![1](https://d585tldpucybw.cloudfront.net/sfimages/default-source/productsimages/teststudio/apis/verify-api-calls.jpg)
* ![1](https://d585tldpucybw.cloudfront.net/sfimages/default-source/productsimages/teststudio/apis/build-dynamic-tests.jpg)
* ![1](https://d585tldpucybw.cloudfront.net/sfimages/default-source/productsimages/teststudio/apis/test-api-calls.jpg)
* ![1](https://d585tldpucybw.cloudfront.net/sfimages/default-source/default-album/fiddler-integration.png)


https://www.blazemeter.com/blog/functional-api-testing-how-to-do-it-right
http://www.tothenew.com/blog/api-testing-using-rest-client/
https://www.neotys.com/insights/api-testing

https://www.ca.com/en/blog-agile-requirements-designer/mbt-blog-series-api-testing-techniques-you-must-try-today.html

How to GET a Cup of Coffee
https://www.infoq.com/articles/webber-rest-workflow/
https://www.softwaretestingmaterial.com/api-testing/

https://katrinatester.blogspot.com/2015/09/api-web-services-microservices-testing.html


API, Web Services & Microservices Testing Pathway
https://katrinatester.blogspot.com/2015/09/api-web-services-microservices-testing.html

# API Testing


The Three Levels of API Testing
 

“APIs, by their nature as being over-the-wire [or network protocol], allow for testing at a variety of levels: behavioral, contractual, and solution-oriented," Breaks down API testing into three essential aspects:

 * **Behavioral API testing** ensures that it delivers expected behavior and handles unexpected behavior properly. This is the lowest, most internal value. Behavioral testing ensures that the REST API delivers on the expected behavior and handles unexpected behavior properly. Does the code work?
* **Contractual API testing** ensures that what is specified by the definition is what has actually been shipped via code. This falls at the middle level of needs. Contractual testing ensures that what is specified by the definition is what has actually been shipped via code. Does the API contract continue to function as we have defined it? With the right inputs? Outputs? Data formats?
* **Solution-oriented API testing** ensures that the API as a whole supports the intended use cases that it was designed to solve. This falls as the highest, mostly external value. Solution-oriented testing ensures that the API as a whole supports the intended use cases that it was designed to solve. Does the API solve real problems that our customers have? Does it do something that people actually care about?



# Here are some of the most common reasons people test their APIs:
* Make sure it does what it’s supposed to do
* Make sure it can handle the load
* Find all the way users can mess things up
* Make sure your APIs work across devices, browsers, and operating systems
* It can be costly not to

# What You Need To Start API Testing
* Who is your target audience? Who is your API consumer?
* What environment/s should the API typically be used?
* What aspects are you testing?
* What problems are we testing for?
* What are your priorities to test?
* What is supposed to happen in normal circumstances?
* What could potentially happen in abnormal circumstances?
* What is defined as a Pass or a Fail? What data is the desired output? What is the chain of events?
* What other APIs could this API interact with?
* Who on your team is in charge of testing what?

# What Types of API Testing Can I Do?
* Functionality testing — the API works and does exactly what it’s supposed to do.
* Reliability testing — the API can be consistently connected to and lead to consistent results
* Load testing — the API can handle a large amount of calls
* Creativity testing — the API can handle being used in different ways.
* Security testing — the API has defined security requirements including authentication, permissions and access controls. See some API security tips for protecting vital data
* Proficiency testing — the API increases what developers are able to do.
* API documentation testing — also called discovery testing, the API documentation easily guides the user.
* Negative Testing — checking for every kind of wrong input the user can possibly supply 

# API test examples,
* Checking API return values based on the input condition
* Verifying if the API doesn’t return anything at all or the wrong results
* Verifying if the API triggers some other event or calls another API
* Verifying if the API is updating any data structures.

# API Testing Best Practices
* Test for the typical or expected results first
* Add stress to the system through a series of API load tests
* Test for failure. Make sure you understand how your API will fail. Just make sure the API fails consistently and gracefully
* Group test cases by test category
* Prioritize API function calls so that it will be easy for testers to test quickly and easily
* Limit the tests from as many variables as possible by keeping it as isolated as possible
* See how it handles unforeseen problems and loads by throwing as much as you can at it
* Perform well-planned call sequencing
* For complete test coverage, create test cases for all possible API input combinations
* Automate wherever you can


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

# Performance Tests
Performance testing is usually relegated to the end of the testing process, in a performance-specific test environment. This is because performance testing solutions tend to be expensive, require specialized skill sets, and require specific hardware and environments. This is a big problem because APIs have service level agreements (SLAs) that must be met in order to release an application. If you wait until the very last moment to do your performance testing, failures to meet the SLAs can cause huge release delays.

Doing performance testing earlier in the process allows you to discover performance-related issues before you run your full regression cycle. If you followed the testing process up to this point, this is actually going to be pretty easy because you have all of the underlying test cases you need in order to do performance testing. You can simply take your scenario tests, load them up into your performance testing tool, and run them with a higher number of users. If these tests fail, you can trace the failure back to the individual user story and have a better level of understanding for what will be affected. Managers can then use this understanding to make a go or no go decision about releasing the application.

Security Tests
Security testing is important to all stakeholders in your organization. If a security vulnerability is exposed and exploited, it can lead to significant reputation loss and financial penalties. Much like a user can accidentally use your APIs in ways you wouldn’t expect, a user can also intentionally try to exploit your APIs. A hacker can get a hold of your API, discover vulnerabilities, and take advantage of them.

To safeguard against this type of behavior, you need to build test cases that attempt to perform these types of malicious attacks. You can leverage your existing test cases to do so, because a scenario test can provide the attack vector into the application. You can then re-use this attack vector to launch your penetration attacks. A good example of this is combining different types of parameter fuzzing or SQL injection attacks with your scenario tests. That way, any changes that propagate through the application will be picked up by your security tests. To learn more about API security testing, check out my colleague’s helpful blog post.

# Omni-Channel Tests
Because of the multiple interfaces that applications interact with (mobile, web, APIs, databases…), you will run into gaps in test coverage if you test any one of these in isolation, missing the subtleties of the complex interactions between these interfaces.

Omni-channel tests comprehensively cover the application’s many interfaces to ensure thorough test coverage, by interweaving API and database tests into the validation of mobile and web UI interactions. This means taking a test that is exercising one of the interfaces and coordinating it with another – executing your UI tests such as Web (Selenium) or Mobile (Appium) and interlacing them with any of your API or database tests, exchanging data points from the system through the test execution. With effective omni-channel testing, you can create stable, reusable test cases that can be easily automated. 


https://www.soapui.org/learn/functional-testing/api-testing-101.html

https://www.guru99.com/testing-rest-api-manually.html
https://www.stickyminds.com/article/methods-and-tools-data-driven-api-testing
https://nordicapis.com/9-types-of-tests-to-perform-on-your-apis/

http://uploads.pnsqc.org/2015/papers/t-062_Asha_paper.pdf
https://www.interrait.com/sites/default/files/docs/WhitePaper_API%20Testing.pdf

https://smartbear.com/SmartBear/media/ebooks/REST-101.pdf
https://www.ontestautomation.com/wp-content/uploads/2014/07/api_test_scenarios.png

https://github.com/shieldfy/API-Security-Checklist
https://mathieu.fenniak.net/the-api-checklist/
https://dzone.com/articles/what-is-api-testing-and-are-you-doing-it-right

https://www.katalon.com/resources-center/blog/web-api-testing-interview-questions/
# API Testing Methodology

Phase 1 – Test Plan Development. Deliverables include:
* Test plan with an appropriate strategy to deal with client’s needs including individual API testing, smoke testing and full regression * testing.
Recommendations on most appropriate test environment configuration to accomplish testing manual methods or via automated testing.

Phase 2 – Test Script Development and Execution. Deliverables include:
* Fully functioning Test Suites prioritized to client requirements.
* Source code matching test cases, incorporated into the Test Suite with suites structured according to Phase 1.
* Complete documentation, including source code and details on environment configurations and settings.

Phase 3 – Report Generation and Analysis. Deliverables include:
* Root Cause Analysis, highlighting trends with potential causes and providing actionable recommendations.
* Determination of current health of the application and identification of critical application problem areas.
* Detailed failure report, including a complete set of test results in appropriate format (e.g., graph; tabulated data) for either further analysis or presentation to management.

Phase 4 – Script Maintenance and Requirements Management. Deliverables include:
* Ensure newly introduced script compatibility (scalability) with existing script framework.
* Provide recommendations on critical application areas and functions needing API performance and security testing.

Phase 5 – Customization
* Legacy API Script Review for coverage and functionality.
* Specific test tools to evaluate APIs.
* Specific test frameworks.
* Specific programming language.
* IDE integration with various version control tools.
* Integration with Continuous Integration tool.
* Integration or Migration to other platform or environment.


# Test cases for this would be

Register user : Happy path ( everything right )
Register user : without username value
Register user : without email value
Register user : without password value
Register user : without username field
Register user : without email field
Register user : without password field
Register user : username with short length
Register user : password with short length
Register user : invalid email
Register user : incorrect email
Register user : already used email
Register user : with wrong method like PUT instead of POST
Register user : without request body


1. Accuracy of data 
2. Schema validation
3. HTTP status codes
4. Data type, validations, order and completeness 
5. Authorization checks 
6. Implementation of response timeout
7. Error codes in case API returns, and 
8. Non-functional testing like performance and security testing 

https://assertible.com/blog/7-http-methods-every-web-developer-should-know-and-how-to-test-them
https://blog.aspiresys.com/testing/overcoming-test-coverage-challenges-in-api-testing/
https://smartbear.com/SmartBear/media/ebooks/REST-101.pdf
https://www.testingxperts.com/wp-content/uploads/2015/12/API-Web-Services-Testing.png
https://www.oxagile.com/assets/img/aqa-api/diagram-lg.png
https://cdn-images-1.medium.com/max/1600/1*uiWyqqbkgsABSfNjb8KBuw.jpeg
https://assertible.com/blog/4-common-api-errors-how-to-test-them


#What you can test in API testing
* Check if response body contains a string
* Check if response body is equal to a string
* Check for a JSON value
* Content-Type is present
* Response time is less than 200ms
* Status code is 200
* Code name contains a string
* Successful POST request status code
* Use TinyValidator for JSON data
* Decode base64 encoded data
* Send an asynchronous request
* Convert XML body to a JSON object
* JSON Schema Validation
* Error Handling
1. Verify the end point avilability
2. Ensure request parameter exists
3. Ensure response parameter exists
4. Ensure single endpoint works
5. Ensure HTTP methods supported
6. Ensure data validation
7. Ensure error message
8. Ensure functionality by calling multiple end points


Performance Testing
Security Testing
# Test Cases for API Testing:
* **Return value based on input condition:** it is relatively easy to test, as input can be defined and results can be authenticated
* **Does not return anything:** When there is no return value, behavior of API on the system to be checked
* **Trigger some other API/event/interrupt:** If output of an API triggers some event or interrupt, then those events and interrupt listeners should be tracked
* **Update data structure:** Updating data structure will have some outcome or effect on the system, and that should be authenticated
* **Modify certain resources:** If API call modifies some resources then it should be validated by accessing respective resources


API Testng Case Study
https://www.qualitylogic.com/wp-content/uploads/2017/01/QL_CaseStudy_Web-API-Tesing_011617.pdf


https://community.smartbear.com/t5/SoapUI-Open-Source/Building-awesome-frameworks-in-SoapUI/td-p/162206


https://json.org/example.html
https://i.pinimg.com/564x/e2/46/40/e24640ffeb010fa8f9f1c15a560b3991.jpg


API 
https://i.pinimg.com/564x/ac/74/cc/ac74cc86f1a766d93276fc0979549808.jpg
https://www.guru99.com/images/1-2015/api_testing.png



https://assertible.com/blog/testing-and-validating-api-responses-with-json-schema

* Endpoint URL status
* Vaidate JSON Schema
* Are we getting value
* Is functionality works? 
	Orders - (Find item, addtocard, payment, confirmation)

 * Response Data is not structured correctly (JSON or XML)
* Validate the status codes
* validate the error message

Fails to handle error conditions gracefully
Unused flags
Missing or duplicate functionality
Reliability Issues. Difficulty in connecting and getting a response from API.
Security Issues
Multi-threading issues
Performance Issues. API response time is very high.
Improper errors/warning to caller
Incorrect handling of valid argument values
Response Data is not structured correctly (JSON or XML)
Test Case
Verify if API doesn’t return any response
Fails to handle error conditions gracefully
Input Parameter Validations
Sequencing of the calls – an output of one can be input to the other type of conditions
Validation of return codes based on the correctness of the input
Performance of APIs –  Delayed in API Response time


https://public.steelkiwi.com/media/filer_public/f4/00/f40020c0-8ed6-46b9-8c74-2c9b7f2dc44e/api_testing_useful_tools_postman_tutorial_and_hints_image_3.png

https://github.com/alexdeleon/groovy-json-schema/blob/master/src/test/groovy/com/lumata/os/groovy/jsonschema/JsonSchemaTest.groovy

Image
https://qph.fs.quoracdn.net/main-qimg-3eb68dfe4b6b5d74562f36c43898a01f



https://www.soapui.org/soapui/media/images/dojo/scenario_02.png


