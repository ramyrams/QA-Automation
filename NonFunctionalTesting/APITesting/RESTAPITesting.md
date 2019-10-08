

1. For manual testing of REST APIs through a testing tool like (Poster), tester must have
a) list of API URLs to test,
b) list of all params required in JSON request
c) list of mandatory params in JSON request
d) list of error/success codes and messages
2. for automation testing, a framework that has these functionalities
a) it makes a cURL call for an API
b) validation on error codes and messages
c) writes Pass/Fail on a text or excel file
d) read input values for params in API requests from text or excel file
3. for performance testing using Siege Home or Apache JMeter - Apache JMeter™
a) how many concurrent connections server can take before it fails
b) concurrent loads in batches like 25, 100, 200, 500 and so on
c) expected response time for all user loads
d) expected throughput for all user loads
e) expected qps - queries per second


Schema validation. Making sure all the objects are there as expected.
Data type validation. Confirming the data connected with the payload’s objects are accurate (a URL is properly formatted for example).
Business logic testing. An example of this would be a retail API. While every product might have a size, the sizes of shoes verse pants are very different.
Positive and Negative testing. Making sure that if you make a bad request, it responds as expected. In API fortress, for example, you can create a single test that has different assertions for a status code 200 verse a 403.
Integration testing. This is when you go beyond just testing an endpoint, but connecting those endpoints in a test that resembles a user flow. Search -> Product Details -> Add to Cart. That whole flow randomized and tested against in one test. Data and problems can occur between the endpoints, and a simple endpoint test will not catch it.

First & foremost, test for the functionality – the basic request-response is working consistently.
Group Test cases by Test category.
For complete Test coverage, create test cases for all possible API input combinations.
Test for failure and invalid parameters for how it handles unforeseen problems and loads making sure the API fails gracefully.
Add stress to the system through a series of API load tests.
Parameters selection should be explicitly mentioned in the Test case itself.
Prioritize API function calls so that it will be easy for testers to test in a timely fashion.
Automate API documentation creation with a standard like Swagger, but then run through the tests, making sure the documentation makes sense for all levels of user experience.
Automate whatever you can.
