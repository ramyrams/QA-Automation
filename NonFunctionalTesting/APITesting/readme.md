# API Tesing

![1](https://www.lambdatest.com/blog/wp-content/uploads/2018/04/Blog.jpg)

Below are the skills a Team/Team Members needs to have to succeed with API Testing.
* Have Curiosity to Learn and Research.
* Able to understand Business Requirements with Functional Requirements
* Able to Collaborate and Communicate with Developers
* Able to Read the API Documentation if readily available (or) Find them Online.
* Testing Skills and Mindset how to Test with various conditions (rationally/logically).
* Able to Plan the testing activity and Inform the relevant stakeholders (internal/external) about how the testing will be approached and Ask for feedback.
* Have knowledge on SQL and Able to perform Queries (simple) to validate the information.
* Have knowledge on How HTTP Works.
* Have Knowledge about JSON and XML. (Basics)
* Have Knowledge on REST vs SOAP. and Find out what APIs we are going to Test. 
* Have Knowledge on API Testing Tools. Example - SOAP UI, POSTMAN, SWAGGER
* Ablility to decide what tools we could use for API Testing.
* Have Knowledge to use Web Developer Tools.
* Additional: Have Knowledge on Fiddler, Charles, Fiddler.
* From Danny Dainton: We should have Knowledge on Scripting. (Javascript) for Writing Tests on Postman.
* From Yogitha (Ex-Colleague in Unilog): We should have knowledge on Groovy Scripts.
* Having Knowledge about API Security. Security of APIs is essential.
* Mentoring/Teaching the team/stakeholders on How the testing has been performed. (Remember: Not everyone will be able to know How testing is done)
* Bonus: Be Open to Read/Learn about APIs Online/Books and how others are performing API Testing.


HTTP
JSON
JSON Schema
API Testing
Katalon



* **Test Coverage:** Dynamically analyze how well your API tests match your API functionality and ensure that you are testing the most important aspects from your stakeholders' viewpoints. 
* **Multi-environment Support:** SoapUI Pro lets you quickly change your test setup depending on the target environment.
* **Test Debugging:** Improve your test quality and follow test flows step-by-step with our test debugging. The debugging interface simplifies test flow, variables, properties, requests, context and more—making test creation and improvement more streamlined.
* **Complex Scenarios:** Perform and validate a login procedure while testing your enterprise messaging and capture client-server SOAP traffic. That's just one use case that SoapUI Pro can support, proving that our tool can handle the complexities of an enterprise architecture.
* **Drag and Drop Test Creation:** Enhance your productivity with a code-free test environment. Create and run even the most complex test scenarios with drag and drop actions.


### What must be checked when performing API testing?
* Accuracy of data
* Schema validation
* HTTP status codes
* Data type, validations, order and completeness
* Authorization checks
* Implementation of response timeout
* Error codes in case API returns, and
* Non-functional testing like performance and security testing

### What is the best approach method to perform API testing?
* Defining the correct input parameters
* Verifying the calls of the mixture of two or more added value parameters
* Defining the basic functionality and scope of the API program
* Writing appropriate API test cases and making use of testing techniques such as equivalence class, boundary value, etc. to check the operability
* Testing case execution
* Comparing the test result with the expected result
* Verifying the API behavior under conditions such as connection to files and so on.



# Part 1: API tests
* When some people talk about “units tests” for an API, they are likely referring to a test of a single HTTP API request. Similar to how software unit tests are written to assess the smallest unit of functionality, you can think of an API test like a unit test.
* With this type of testing, you may or may not have access to the underlying code. However, you can validate that an API behaves as expected from the user’s perspective.

![1](https://miro.medium.com/max/378/1*FHN_cVlqnsoZasl9pqtabg.png)

## Examples of API tests
* **Status:** the correct response code was returned
* **Performance:** the response was returned within a certain time
* **Syntax:** the content type of the returned content was as expected
* **Syntax:** the server accepts correct input
* **Error handling:** the server rejects incorrect input
* **Error handling:** excluding a required parameter results in an error
* **Error handling:** submitting incorrect data types results in an error
* **Error detection:** negative testing to identify exceptions and race conditions
* **Schema:** the response payload conforms to an expected structure or format
* **Functional:** the server returns a predictable value based on the input condition
* **Functional:** the request predictably modifies a resource
* **Security checks:** SQL injections do not result in data leakage


# Part 2: Integration tests
* Integration tests are built across multiple units to verify that components are working together as expected. This can encompass two or more individual components, or endpoints. Integration tests can include internal services, third-party services, and other external dependencies.

![1](https://miro.medium.com/max/444/1*FvQk3ioQfoRd6f_2_1sDLA.png)


# Setup and teardown
* Sometimes your test cases require some initial groundwork to prepare your test environment. Perhaps you’re generating new users, creating authentication tokens, or simply initializing variables.
* After your tests run, you may need to clean up the test conditions, so that you’re not littering new users, records, and other side effects throughout your test environment.

![1](https://miro.medium.com/max/2256/1*2tytTigCQZlib4Nu_uFxIQ.png)

# Scenario tests

* Make sure your application is robust and stable across a spectrum of scenarios. Testing both expected and unexpected use cases is critical to a good user experience. Visualize the user’s workflow and think about how they interact with the application.
* Write and run your API tests in a sequence that mirrors a typical user workflow, commonly identified in the user story business requirements. Testers should also identify test cases for atypical user behaviors.
![1](https://miro.medium.com/max/528/1*9Muh0JIuuctdpsNOIgFGGw.png)


# Mocking dependencies
* If your test case involves shared or production resources, some teams will use mock services. Mocking the actual service allows you to rely on a predictable response so you can isolate the component under test when debugging issues.
* You can also use mocks to simulate error conditions or rare instances that might be difficult or problematic to set up in a production environment.

![1](https://miro.medium.com/max/408/1*jBMZGDntY-Y3tJHNY9GQSQ.png)


# Contract testing
* As organizations continue to transition to a microservices architecture, teams become increasingly dependent on internal services. An API-first approach assumes the design and development of an application programming interface (API) comes before the implementation.
* Consumer-Driven Contract Testing (CDC Testing) ensures that your service doesn’t break when a service that you rely on is updated. This type of contract testing requires the consumer of the service to define the format of the expected responses, including any validation tests. The provider must pass these tests before releasing any updates to the service.

![1](https://miro.medium.com/max/2256/1*i4K7dWsxZ4jfpebHtmJQIg.png)


# Regression testing
* Run initial smoke tests to verify that your build is stable enough to proceed with more rigorous, regression testing.
* Regression tests can be either unit tests, integration tests, or both. Run your entire test suite after a patch, upgrade, or bug fix. Even if you’re working on a part of the code that you don’t believe impacts a previous patch, you should run your regression tests to ensure that new functionality doesn’t break something that was previously working.



* **Useful:** Is the API useful from an end user’s point of view?
* **Usable: **Can the API be quickly used by a developer and provide easy-to-use functionality?
* **Desirable:** Is the functionality provided by the API something that generates desire in developers and end users?
* **Findable:** Can the API documentation be found easily, and can developers start using it immediately?
* **Accessible:** Can the API provide functionality for end users who have technical constraints/limitations in consuming it?
* **Credible:** Is the data provided by the API trustworthy?
* **Valuable:** Does the API contribute to the company’s bottom line and improve customer satisfaction?

* **URL Structure:** How should a URL format for a given resource look like, what should be the path, query parameters, etc.
* **Request methods:** Define a list of request method and define when to use which request method. This will make sure that request methods have the same behavior across your APIs.
* **Request/Response Headers:** List of headers that should be used with the API while requesting to service and responding back.
* **Response status codes:** Create a list of allowed status codes for your API and clearly set the guidelines on when to use a specific status code.
* **Errors:** Design a common error response format that all other developers can use. A good error response should let a developer recognize, diagnose and recover from errors.
* **Versioning: **Establish guidelines on how to version an API and points to keep in mind while versioning an API.
* **Filtering/Pagination/Sorting:** How to support filtering and pagination in your APIs which returns a collection of data, what should the response JSON look like with filtered/paginated/sorted result.




https://www.slideshare.net/TechWellPresentations/automate-rest-services-testing-with-restassured

http://www.tjmaher.com/2018/11/jason-ioannides-api-testing-from-entry.html

Jason Ioannides, API Testing: From Entry Level to a PhD in 40 mins

https://dzone.com/articles/effective-practices-for-api-test-automation
https://dzone.com/articles/things-you-need-to-know-about-api-testing
https://dzone.com/articles/10-api-testing-tips-for-beginners-soap-amp-rest

https://dzone.com/articles/how-to-create-top-quality-rest-apis

https://dzone.com/articles/things-you-need-to-know-about-api-testing


A collective list of public JSON APIs for use in web development.
https://github.com/toddmotto/public-apis

https://fakejson.com/
http://www.omdbapi.com/
https://resttesttest.com/



https://github.com/signalfx/swagger-cli-client/blob/master/example/petstore-schema.json


Examples of assertions that is possible in SoapUI are:

Schema Compliance
Simple Contains
Simple Not Contains
SOAP Fault
Not SOAP Fault
SOAP Response
Response SLA
XPath Match
XQuery Match
Script Assertion
WS-Security Status
WS-Addressing Response Assertion
WS-Addressing Request Assertion

https://www.katalon.com/resources-center/blog/web-api-testing-interview-questions/

![1](https://d1f5pmhur9pirz.cloudfront.net/wp-content/uploads/2017/08/API-Login-2.png
![1](https://d1f5pmhur9pirz.cloudfront.net/wp-content/uploads/2017/08/api-13.png

![1](https://www.soapui.org/soapui/media/images/stories/newfunctesting/func_test_image1_new.png)
![1](https://www.soapui.org/soapui/media/images/stories/newfunctesting/feature-focus_2.png)
![1](https://www.soapui.org/soapui/media/images/stories/newfunctesting/func_test_4_new.png)
![1](https://www.soapui.org/soapui/media/images/stories/newfunctesting/func_test_5_new.png)
![1](https://www.soapui.org/soapui/media/images/stories/newfunctesting/func_test_6_new.png)
![1](https://www.soapui.org/soapui/media/images/stories/newfunctesting/func_test_7_new.png)
![1](https://www.soapui.org/soapui/media/images/stories/newfunctesting/func_test_8_new.png)


API limits

https://developers.rebrandly.com/docs/api-custom-url-shortener


https://discourse-cdn-sjc2.com/standard10/uploads/ministryoftesting/original/2X/4/4aa5f0038416f22d3137cde5959f8da181e0b758.png

Discussion 
https://club.ministryoftesting.com/c/30-days-of-testing/30-days-of-api-testing


* [vREST Cookbook](https://docs.optimizory.com/display/vrest/vREST+Cookbook)


# Writing your first test case
![1](https://docs.optimizory.com/download/attachments/10326993/configure-base-url.png)			
![1](https://docs.optimizory.com/download/attachments/10326993/add-contact-api-form.png)				
![1](https://docs.optimizory.com/download/attachments/10326993/add-contact-api-details.png)			
![1](https://docs.optimizory.com/download/attachments/10326993/add-contact-request-params.png)		
![1](https://docs.optimizory.com/download/attachments/10326993/add-contact-raw-body.png)				
![1](https://docs.optimizory.com/download/attachments/10326993/add-contact-request-headers.png)		
![1](https://docs.optimizory.com/download/attachments/10326993/add-contact-response-validation.png)	
![1](https://docs.optimizory.com/download/attachments/10326993/add-contact-assertions.png)			
![1](https://docs.optimizory.com/download/attachments/10326993/dv-assertion-failed-empty-body.png)	
![1](https://docs.optimizory.com/download/attachments/10326993/tc-failed-dynamic-props.png)			
![1](https://docs.optimizory.com/download/attachments/10326993/testsuite.png)							
![1](https://docs.optimizory.com/download/attachments/10327036/tc-environment-switcher.png)
![1](https://docs.optimizory.com/download/attachments/10326995/assertions.png)	

https://docs.optimizory.com/download/attachments/11141404/write-tcs.png?version=1&modificationDate=1450876476700&api=v2

https://docs.optimizory.com/download/attachments/10327081/trd-filter-testrun.png?version=1&modificationDate=1470119160499&api=v2
https://docs.optimizory.com/download/attachments/10327081/trd-choose-tc.png?version=2&modificationDate=1470119380331&api=v2
https://docs.optimizory.com/download/attachments/10327081/trd-expand-tc.png?version=1&modificationDate=1470119523870&api=v2
https://docs.optimizory.com/download/attachments/10327081/trd-debug-tc.png?version=1&modificationDate=1470119600119&api=v2
https://docs.optimizory.com/download/attachments/11141404/write-tcs.png?version=1&modificationDate=1450876476700&api=v2

# JSON Response Validation Scenarios
Let us see, how various types of responses can be validated in vREST.

My API returns the static response.
I just want to validate the schema of my response, not the actual content.
My API returns some dynamic properties like _id, createdOn etc. and I want to ignore them during response validation.
My API returns a very large response and I am interested in validating only a small part of my API response.
My API returns some response in which some part of the response can be obtained from the responses of previous test cases.
My API returns dynamic response and none of the above fit to my needs.


Below are the skills a Team/Team Members needs to have to succeed with API Testing.

* Have Curiosity to Learn and Research.
* Able to understand Business Requirements with Functional Requirements
* Able to Collaborate and Communicate with Developers
* Able to Read the API Documentation if readily available (or) Find them Online.
* Testing Skills and Mindset how to Test with various conditions (rationally/logically).
* Able to Plan the testing activity and Inform the relevant stakeholders (internal/external) about how the testing will be approached and Ask for feedback.
* Have knowledge on SQL and Able to perform Queries (simple) to validate the information.
* Have knowledge on How HTTP Works.
* Have Knowledge about JSON and XML. (Basics)
* Have Knowledge on REST vs SOAP. and Find out what APIs we are going to Test. 
* Have Knowledge on API Testing Tools. Example - SOAP UI, POSTMAN, SWAGGER
* Ablility to decide what tools we could use for API Testing.
* Have Knowledge to use Web Developer Tools.
* Additional: Have Knowledge on Fiddler, Charles, Fiddler.
* From Danny Dainton: We should have Knowledge on Scripting. (Javascript) for Writing Tests on Postman.
* From Yogitha (Ex-Colleague in Unilog): We should have knowledge on Groovy Scripts.
* Having Knowledge about API Security. Security of APIs is essential.
* Mentoring/Teaching the team/stakeholders on How the testing has been performed. (Remember: Not everyone will be able to know How testing is done)
* Bonus: Be Open to Read/Learn about APIs Online/Books and how others are performing API Testing.

# Types of assertions
* Status code
* JSON path data
* JSON validation
* XPath XML data (XML/HTML)
* Response header
* Response time
* Response text
* HTML validation
* Link checker

* ![1](https://cdn2.hubspot.net/hubfs/208250/Blog_Images/api10.png)
* ![1](https://assertible.com/images/feature-test-assertions.png)
* ![1](https://assertible.com/images/user-guide-assertions-1.png)
* ![1](https://assertible.com/images/user-guide-tests-4.png)


* ![1](https://s3-us-west-2.amazonaws.com/assertible/blog/assertible-slack-test-run-integration.png)
* ![1](https://s3-us-west-2.amazonaws.com/assertible/blog/assertible-github-status-check.png)

* ![1](https://assertible.com/images/feature-test-assertions.png)
* ![1](https://s3-us-west-2.amazonaws.com/assertible/blog/assertible-json-schema-assertion-form.png)

* ![1](http://i1.wp.com/blog.restlet.com/wp-content/uploads/2016/04/DHC-assertions-02-XPath.png)
* ![1](http://i1.wp.com/blog.restlet.com/wp-content/uploads/2016/04/DHC-assertion-01-JSON-Path.png)

* ![1](https://public.steelkiwi.com/media/filer_public/95/71/9571c223-e99c-4166-a62d-b60587847e3e/api_testing_useful_tools_postman_tutorial_and_hints_image_6.png)
* ![1](https://public.steelkiwi.com/media/filer_public/bb/b3/bbb31b29-f9f2-4a1e-8d84-a4adec7ae86f/api_testing_useful_tools_postman_tutorial_and_hints_image_7.png)
* ![1](https://public.steelkiwi.com/media/filer_public/f4/00/f40020c0-8ed6-46b9-8c74-2c9b7f2dc44e/api_testing_useful_tools_postman_tutorial_and_hints_image_3.png)



# API Testing Business
https://assertible.com/plans


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

# Types of API Testing
Integration testing, security testing, performance testing, usability testing are some of the terms that you might be aware of as you’re here. Well, API testing provides shade to all the terms under a single umbrella. Let me put it that way, when you perform API testing you make sure that your API passes the following tests.

1. Functional Testing: To make sure that all the API endpoints are up and working and doing what exactly they are supposed to so.

2. Reliability Testing: Making sure that the API works in case of connecting it to various devices and don’t just get disconnected any time.

3. Load Testing: When various servers sends request to an API, it is necessary to make sure that the API responds to all of them.

4. Stress Testing: When more than set number of requests is received by the API how does it behaves? Does it send some message? Works as intended. Mandatory to check.

5. Security Testing: While giving authentication, it is important to make sure that no security breaches happen in between. No more than required data is shared. Have appropriate authentications, permissions, and access controls.

6. Integration Testing: All the APIs connected to each other communicate properly. And addition of features in the API do not cause addition of some bugs in other API modules.

7. Usability Testing: The API is functional and on the top of it, user-friendly.

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

Why is API testing important?
All forms of software is essential to identify bugs and inconsistencies both when you are releasing a product and as you make sure it continues to work when it’s out in the wild. It’s very clear that the risk of putting a bad and especially insecure product on the market is greater than the cost to test it.

Here are just some of the examples of common security tests that your API could be vulnerable to:

The API is what gives the value to the application. It’s what makes our phones “smart” and it’s what streamlines business processes. If any API doesn’t work efficiently and effectively, it will never be adopted, regardless if it is a free and open API or one that you charge per call or group of calls. What’s worse, if an API breaks because errors weren’t detected, it could not only break a single application but a chain of business processes hinged to it.



Tests will surely vary but here are common API test examples:
* Checking API return values based on the input condition.
* Verifying if the API doesn’t return anything at all or the wrong results.
* Verifying if the API triggers some other event or calls another API.
* Verifying if the API is updating any data structures.


Where can API testing can be automated?
* API functional testing.
* Creating loads of dynamic data to throw into your API testing.
* Repeated test design.
* Analyzing your functional test coverage to know what you're missing.
* Ad-hoc testing.
* Using the command-line to hook your tests to your build system.
* Flipping between multiple environments quickly, including development, testing, and staging environments.
* Testing protocols in a single, unified framework.
* Using multiple data sets at the same time to cover different test scenarios.
* As with all automation, speeding up the overall testing process.
* Error testing, where you throw forced errors at the API to understand how it will react.
* Testing in multiple languages.

What are some API Testing best practices?
* You’ve created your own API testing plan. Now it’s good to have a list of rules of thumb to follow in order to help make the test as successful as possible:
* Test first for the typical or ordinary results, for what happens consistently and what doesn’t.
* Add stress to the system through a series of API load tests. 
* Test for failure. Keep working and working until you get a Fail output, making sure the API fails consistently and gracefully.
* Group test cases by test category.
* Parameters selection should be explicitly mentioned in the test case itself.
* Prioritize API function calls so that it will be easy for testers to test in a timely fashion.
* Limit the tests from as many variables as possible by keeping it as isolated as possible.
* Automate API documentation creation with a standard like Swagger, but then run through the tests, making sure the documentation makes sense for all levels of user experience.
* Throw anything you can at the API to test for how it handles unforeseen problems and loads.
* Perform well-planned call sequencing.
* Later on, get creative! For complete test coverage, create test cases for all possible API input combinations.
* Reuse your tests to monitor your APIs in Production.
* Automate whatever you can.
* But trust your instincts if something seems off!


Choosing an API Monitoring Tool
Similar to web monitoring, API monitoring provides crucial performance data from which developers and operations teams alike can use to improve user experience. There are a variety of tools available, but selecting an API Monitoring solution that can provide actionable data is essential, not only to increase your ROI, but to get genuinely useful performance data. When choosing a solution, it’s good to keep these functionalities in mind:

* Intuitive – You won’t use a tool you don’t understand. You especially won’t be able to take full advantage of the functionalities if you don’t like the tool. Finding an API monitoring tool that is easy to use and instinctual will reduce your ramp up time as well as increase the probability of your reliance on this tool.  
* Reuse – Find a tool that lets you use what you’ve got. Reuse scripts from the tools your API developers and testers use to avoid doing the same tasks twice.
* Run Options – Keeping your API monitors on a schedule that fits your needs is essential. Making sure you can run monitors in intervals of your preference or set blackout periods can be especially helpful when trying to gage performance over time. Almost just as important is the ability to run a monitor on demand – as either a test or a real run.
* Sequencing and Assertions – Accuracy is key. APIs transactions that require sequential functionalities should be able to be monitored, so you receive monitoring data that takes into account the big picture functionalities with the detailed step validations. While it’s imperative to understand the speed and availability of your API, functional correctness is even more important. If your API is returning the wrong data, you’ve fallen into the trap of the illusion of availability, where your customers encounter a broken system and you’re blissfully unaware. Making sure you can add assertions and validate the data the API returns is an essential functionality for an API monitoring tool.  
* Consumable and Shareable – A tool that can communicate data easily, swiftly, and clearly is vital to any operation. API performance is no exception. Selecting a tool that aggregates data and visualizes the data properly can help provide instant actionable insights for you to share with your teams to reduce your MTTR (mean-time-to-resolution).
* Adaptable – Tool stacks can include all sorts of software. Make sure you have a tool that is adaptable and flexible, so it can fit into your stack, whatever your preferences may be.
* Alerts – You have to actually know when something is wrong in order to fix it. Find a tool that prioritizes this, and you will be good to go!


How to test an API


Because APIs lack an interface, instead of typing in keystroke inputs and recording the outputs (black-box testing), an application must be used to send calls to the API to generate an output. APIs can be tested directly or as part of an integrated system, and often cover areas of functionality, security, performance, and reliability.

This can be automated using an API testing tool or by manually writing code to drive the API. Some key considerations in API Testing include:

* Setting Up an API Test Environment: Depending on your infrastructure for the app under test, you may need to configure the database and server for your application. However, in most cases, you only need to know where and how to address the application components and install your test tools.
* API Test Tools: There are many API test tools. As with any tool type, there are commercial and open source options. Commercial tools are often divided into free (lower level of functionality) or professional versions that you must purchase.
* API Protocols: REST and SOAP are the most common protocols that developers use to develop their APIs. Sometimes, developers may use a custom implementation of these protocols which may have special message handling requirements and parameter settings that you’ll need to be aware of.
* API Performance: At XBOSoft, we use JMeter to conduct our API testing because it has a significant advantage in that API tests can easily be converted to performance tests. We also use a variety of other commercial and open source tools depending on the client’s software.
* Parameter Setup: Testers must be knowledgeable of business rules associated with a product because some rules may have a different API implementation, thereby requiring different sequencing and parameters.Understanding the product’s business rules with the parameters and expected inputs/outputs is the key to all API testing. Because of this, we always first design manual test case/suites according to the product usage.


API Testing Services
API testing services form a critical component of our comprehensive software testing services. These are:

* API Automated Testing
Using API testing to prevent functional defects prevent up to 10 GUI defects later in the development cycle.
* API Performance Testing
If the product is sluggish, users will look for alternatives. Make sure that your application’s components integrate and function well under load before the UI is factored in.
* API Security Testing
Make sure the products’ “doors & windows” are locked. Don’t let non-authenticated entry into you and your users application usage records and data.


# API Testing Methodology
In that time, we have developed a systematic approach that ensures the key aspects of an overall test program are addressed. Our typical API Testing model is multi-phased. This allows for short-term engagements (Phases 1-3) where the testing baseline, strategy, development and execution are established whereby the client can then take over on-going responsibility for the associated testing. Phases 4 & 5 are part of longer-term partnerships where XBOSoft manages and executes the testing effort.

Phase 1 – Test Plan Development. Deliverables include:
* Test plan with an appropriate strategy to deal with client’s needs including individual API testing, smoke testing and full regression testing.
* Recommendations on most appropriate test environment configuration to accomplish testing manual methods or via automated testing.

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

# Six Steps for Better Apps: Testing Basics
## Create an API Testing Environment
* All API testing starts the same way: creating the right environment. Best bet? Use a test server configured with an API service. While it’s possible to set up the same in-house, a reputable API testing company can get testing off the ground immediately.

##Choose API Testing Tools
* Testing apps requires tools — some of the best open-source options include REST-assured for HTTP-based REST services and Postman for exploratory testing. Paid options are also available for more heavy-duty tasks.

##Pick API Protocols
* REST and SOAP are the most common options for API testing. REST is lightweight and supports a wide variety of data formats, while SOAP includes native retry logic for failed communications.

##Measure API Performance
* Next up? Measuring performance. Why? Because without performance data, it’s impossible to know if testing has the desired effect. Tools such as JMeter make it easy to convert API tests into performance metrics.

##Establish API Parameters
* To achieve ideal API testing output, testers must understand both specific business requirements and expected inputs and outputs — testing offers no benefit if parameters don’t match realistic outcomes. Before running any large-scale API test, establish basic parameters. If you’re using a third-party API testing service, make sure they design manual test cases and suites based on current product usage.

##Leverage Test Automation
* Manual testing is an effective way to target specific concerns or usage issues. Yet given the massive reach of apps across mobile devices, desktops and IoT offerings, it’s now critical to leverage automated API testing, performance testing and security testing to identify functional defects, latency and potential security risks.

http://www.3pillarglobal.com/wp-content/uploads/2016/02/jmeter_3.png

http://validata-software.com/images/blog/wp-content/uploads/2017/09/selenium1-1.jpg
https://dzone.com/articles/10-effective-ways-for-successful-api-testing
We  need to impliment in APi Framework
https://smartbear.com/product/ready-api/overview/
https://assertible.com/blog/7-http-methods-every-web-developer-should-know-and-how-to-test-them
https://smartbear.com/product/ready-api/soapui/overview/
https://www.melioratestlab.com/wp-content/uploads/2017/02/vaat2.png
https://www.slideshare.net/EuroSTARConference/bj-rollison-slides
https://www.slideshare.net/SmartBear_Software/evaluating-and-testing-web-apis
https://cdn-images-1.medium.com/max/1600/0*MpGv5o8Ic-VAL11A.

https://www.infoq.com/articles/gui-automation-patterns


# Test Scenarios:
https://optimusinfo-wpengine.netdna-ssl.com/wp-content/uploads/2014/11/Picture3b.png
http://i2.wp.com/www.testautomationguru.com/wp-content/uploads/2017/03/rest005.png?zoom=1.25&resize=659%2C259

# Data-Driven Testing:
http://i0.wp.com/www.testautomationguru.com/wp-content/uploads/2017/03/rest004.png?w=1111

# PERFORMANCE TESTING OF A RESTFUL API USING JMETER
https://www.3pillarglobal.com/insights/performance-testing-of-a-restful-api-using-jmeter


https://github.com/shieldfy/API-Security-Checklist
https://github.com/s0wr0b1ndef/API-Security-Checklist
https://github.com/mbabazadeh/API-Security-Checklist
https://github.com/npanigrahy/API-Security-Guidelines
