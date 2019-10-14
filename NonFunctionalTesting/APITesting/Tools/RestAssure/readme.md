REST APIs have four types of parameters:

Header parameters: Parameters included in the request header, usually related to authorization.
Path parameters: Parameters within the path of the endpoint, before the query string (?). These are usually set off within curly braces.
Query string parameters: Parameters in the query string of the endpoint, after the ?.
Request body parameters: Parameters included in the request body. Usually submitted as JSON.


Path parameters
For example, in the following endpoint, {user} and {bicycleId} are required path parameters:
/service/myresource/user/{user}/bicycles/{bicycleId}

Query string parameters
Query string parameters appear after a question mark (?) in the endpoint. The question mark followed by the parameters and their values is referred to as the “query string.” In the query string, each parameter is listed one right after the other with an ampersand (&) separating them. The order of the query string parameters does not matter.

/surfreport/{beachId}?days=3&units=metric&time=1400

# Request body parameters

{
"days": 2,
"units": "imperial",
"time": 1433524597
}


https://idratherbewriting.com/learnapidoc/images/sendgridresponseexample1.png
https://idratherbewriting.com/learnapidoc/images/sendgridresponseexample2.png


https://idratherbewriting.com/learnapidoc/images/bitlyresponsedoc.png
https://idratherbewriting.com/learnapidoc/images/myobjsondoc.png
https://developer.ibm.com/recipes/wp-content/uploads/sites/41/2018/06/Framework.png

Step by step
https://restservicestesting.blogspot.com/


https://github.com/vikramvi/RESTful-api-automation

https://github.com/siva-thota/Rest_Assured/blob/master/REST-assured/src/test/java/com/steps/JasonValidationSteps.java

Cucumber
https://github.com/siva-thota/Rest_Assured/tree/master/REST-assured


Quick start - http://toolsqa.com/rest-assured/rest-api-test-using-rest-assured/

https://github.com/rest-assured/rest-assured/wiki/Usage

https://github.com/pranitha-mandadi/restAssuredMaven/blob/master/src/test/java/com/test/restAssured/BaseTest.java
https://github.com/askeledz/rest-automation/blob/master/RESTtest_core/src/main/java/com/rest/autotests/core/util/Config.java

good night
https://github.com/askeledz/rest-automation

Wiremock
https://github.com/kendo1234/restassured/tree/master/src/test/java

https://github.com/pazjing/rest-assured/tree/master/src/test/java/com/api/rest/api/restassuredhelper

https://github.com/rushi2828/RestAssuredTests/blob/master/src/test/java/SampleTestBDD/GETMethodsTests.java


https://github.com/lastdil/rest-assured/blob/master/src/test/java/authTest.java

https://github.com/Srilathaky/Rest_Assured/tree/master/src/test/java/confirmation_testsuit

Good One
https://github.com/icedme666/ApiAuto



Response Time Validation Rest Assured
https://www.youtube.com/watch?v=wdec1cAA4x4


https://semaphoreci.com/community/tutorials/testing-rest-endpoints-using-rest-assured

https://www.youtube.com/watch?v=AbJrfP4ziIk&list=PLEiBaBxmVLi-hoi61aX-2agQb8EXSCT5f

http://rest-assured.io/
Testing and validating REST services in Java is harder than in dynamic languages such as Ruby and Groovy. REST Assured brings the simplicity of using these languages into the Java domain. For example if your HTTP server returns the following JSON at “http://localhost:8080/lotto/{id}”:


rest-assured https://github.com/rest-assured/rest-assured
Java DSL for easy testing of REST services

# Good One
https://github.com/lamchakchan/RestAssured.Net


# Samples
https://github.com/swtestacademy/RestAssuredExample
https://github.com/lroslonek/RestAssuredExample
https://github.com/artemave/REST-assured-example
https://github.com/badrisugavanam/RestAssuredProject
https://github.com/cheungkayip/Cucumber-RestAssured
https://github.com/spaciulis/rest_api_test_example
https://github.com/roydekleijn/example-java-rest-assured
https://github.com/mrsmoo/RestAssuredExample
https://github.com/DavidRichard2016/SampleRestAssured
https://github.com/vikramvi/RESTful-api-automation
https://github.com/go2guy/RestAssured
https://github.com/RyanBard/rest-assured-example
https://github.com/jni-/rpn-calculator-cucumber
https://github.com/justinjoseph89/RestAssuredExample
https://github.com/moolya-testing/Automation-Java
https://github.com/the-creative-tester/rest-assured-api-testing-example
https://github.com/kollurupawankumar/RESTfulExampleTest
https://github.com/s1ider/rest-assured-example
https://github.com/britka/rest-assured-example
https://github.com/emersonluiz/start-rest-assured


https://github.com/testvagrant/RESTTests_RestAssured/tree/master/src/test/java

https://github.com/s1ider/rest-assured-example/blob/master/src/test/java/AnotherRestResource/CRUD.java

https://github.com/s1ider/rest-assured-example/blob/master/src/test/java/FreeGeoIP/GetInfoByHostname.java





https://github.com/lroslonek/RestAssuredExample/blob/master/src/test/java/service/RestService.java

https://github.com/CourseRepository/WebServiceTestingusingRestAssured
 https://github.com/LaxminarayanJena/RestAssured/tree/master/src/test/java
https://github.com/hariprasadms/katalon-with-rest-assured

https://github.com/TechieTester/RestAssuredFundamentals/tree/master/src/test/java

https://github.com/pavankovurru/API_Automation_Framework

https://github.com/lroslonek/RestAssuredExample/blob/master/src/test/java/testflow/DefaultRestTest.java
https://github.com/lroslonek/RestAssuredExample/blob/master/src/test/java/testflow/TestDetectiveBlogTest.java

https://github.com/adriangonciarz/rest-assured-example/blob/master/src/main/java/TestBase.java

https://github.com/britka/rest-assured-example/blob/master/src/test/java/org/brit/tests/PetClassWithRequestSpec.java
https://github.com/britka/rest-assured-example/blob/master/src/test/java/org/brit/tests/PetTestSerializeDeserialize.java
https://github.com/britka/rest-assured-example/blob/master/src/test/java/org/brit/tests/PetTests.java

https://github.com/britka/rest-assured-example/blob/master/src/test/java/org/brit/tests/PetTestsUsingLittleLibrary.java

https://github.com/cassiomolin/tasks-rest-api/blob/master/src/test/java/com/cassiomolin/example/task/api/TaskResourceTest.java

Base Test
https://github.com/Fruzenshtein/rest-automation/blob/master/src/test/java/fruz/udemy/test/LandLordTest.java
https://github.com/Fruzenshtein/rest-automation/blob/master/src/test/java/fruz/udemy/test/ApartmentTest.java


https://github.com/the-creative-tester/rest-assured-api-testing-example

https://github.com/globant-ankita/RestAssuredAPIFramework/tree/master/src/test/java/tests

https://github.com/vanlaars/RestAssured/tree/master/rest/src/test/java/assured/rest


https://github.com/gauravkarvir/cucumber_testng_java


https://github.com/artemave/REST-assured


https://github.com/basdijkstra/rest-assured-workshop/blob/master/src/test/java/answers/RestAssuredAnswers1Test.java

