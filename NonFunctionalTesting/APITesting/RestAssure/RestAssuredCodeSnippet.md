# REST Code Snippet

# Dependency [More](https://github.com/rest-assured/rest-assured/wiki/GettingStarted)
* REST Assured - io.rest-assured -> rest-assured
* JsonPath - io.rest-assured->json-path
* JSON Schema Validation - io.rest-assured ->json-schema-validator

# Static imports
* io.restassured.RestAssured.*
* io.restassured.matcher.RestAssuredMatchers.*
* org.hamcrest.Matchers.*
* io.restassured.module.jsv.JsonSchemaValidator.*



# URL
* https://github.com/rest-assured/rest-assured/tree/master/examples
* https://github.com/rest-assured/rest-assured/tree/master/examples/rest-assured-itest-java/src/test/java/io/restassured/itest/java
* https://www.programcreek.com/java-api-examples/?ClassName=RestAssured&action=search&submit=Search
* http://www.javased.com/?api=com.jayway.restassured.RestAssured
* https://static.javadoc.io/com.jayway.restassured/rest-assured/1.2.3/com/jayway/restassured/RestAssured.html
* https://github.com/adriangonciarz/rest-assured-example



Use this
	https://mvnrepository.com/artifact/io.rest-assured/rest-assured/3.2.0
	<!-- https://mvnrepository.com/artifact/io.rest-assured/rest-assured -->
	<dependency>
		<groupId>io.rest-assured</groupId>
		<artifactId>rest-assured</artifactId>
		<version>3.0.0</version>
		<scope>test</scope>
	</dependency>

Not Jayway - Don't use this 
	https://mvnrepository.com/artifact/com.jayway.restassured/rest-assured
	
Some Dependency
	json-path
	jsoan-schema-validator
	xml-path
	testng
	java-hamcrest
	
bdd style code
	given().when().then()

There are 3 type of Request parameter
	queryParam
	formParam
	pathParam
	

   

@Test
public void TestStatusCode()
{
	given().get("www.google.com").then().statusCode(200);
}

# Log

given().
	get("www.google.com).
then().
	statusCode(200).
	log().all();

when().
	get("http://services.groupkt.com/country/get/iso2code/IN").
then().
	.statusCode(200).
	log().all();

	
	
given().
	get("http://services.groupkt.com/country/get/iso2code/IN").
then().
	body("RestResponse.result.name", equalTo("United States of America"));
	
	
given().
	get("http://services.groupkt.com/country/get/all").
then().
body("RestResponse.result.name", hasItems("Argentina", "Australia"));
	
given().
param("key1", "value").
header("head", "value").
queryParam("df", "dfd").
formParam("df", "dfd").
param("df", "dfd") - it automatically detedct and convert QuertParam for GET and POST it will tread as formParam
		
	
	RestAssured
		.given()
			.baseUri("http://" + si.getIp() + ":" + si.getPort())
		.when()
			.get("/greeting")
		.then()
			.assertThat()
			.statusCode(200)
			.and()
			.body("greeting", equalTo("Hello Dockerunit!!!"));
			
			

RestAssured.baseURI = "http://localhost";
RestAssured.port = config.getInteger("server.port");
RestAssured.enableLoggingOfRequestAndResponseIfValidationFails();
this.baseURI = conf.getString("server.baseURI");
this.port = conf.getInt("server.port");
this.timeout = conf.getInt("service.api.timeout");
RestAssured.registerParser(Params.MIME_TYPE_TEXT_PLAIN, Parser.JSON);
RestAssured.config = new RestAssuredConfig().encoderConfig(encoderConfig().defaultContentCharset("UTF-8").encodeContentTypeAs("application-json", ContentType.JSON));
RestAssured.registerParser("text/plain", Parser.TEXT);
RestAssured.defaultParser = Parser.JSON;
	
			
@Test
public void testIllegalMethodTypes() {	
	JsonPath response = RestAssured.given().when().delete(RESTAURANT_API).then().statusCode(405).extract().jsonPath();
	Assert.assertEquals("Request method 'DELETE' not supported", response.getString("message"));
	Assert.assertEquals("Method Not Allowed", response.getString("error"));

	response = RestAssured.given().when().put(RESTAURANT_API).then().statusCode(405).extract().jsonPath();
	Assert.assertEquals("Request method 'PUT' not supported", response.getString("message"));
	Assert.assertEquals("Method Not Allowed", response.getString("error"));

	response = RestAssured.given().when().post(RESTAURANT_API).then().statusCode(405).extract().jsonPath();
	Assert.assertEquals("Request method 'POST' not supported", response.getString("message"));
	Assert.assertEquals("Method Not Allowed", response.getString("error"));

	response = RestAssured.given().when().patch(RESTAURANT_API).then().statusCode(405).extract().jsonPath();
	Assert.assertEquals("Request method 'PATCH' not supported", response.getString("message"));
	Assert.assertEquals("Method Not Allowed", response.getString("error"));
}



		
		
	given().
		pathParam("type", "json").
		pathParam(section",domains").
	when().
		post("http://www.test.com/test/{type}/{section}).
		then().statusCode(200);
		
	* get() can be in both given or when ()
	
	//set cookie in request
	given().cookie("name","ddd).
	
	given().
		param("key1", "value").
		header("head", "value").
	when().
		get("http://services.groupkt.com/country/get/iso2code/IN").
	then().
		.statusCode(200).log().all();
		
	string res = get("http://services.groupkt.com/country/get/iso2code/IN").asString();
	System.out.println(res);
	
	asInputStream();
	asByteArray();
	
	string href = 
	when.
		get("http://jsonplaceholder.typicode.com/photos/1").
	then().
		contentType(ContentType.JSON).
		body("albumid", equal(1)).
		extract().
			path("url");
			
			
	//Same as abouve		
	string href = when.get("http://jsonplaceholder.typicode.com/photos/1").path("url");
	
	//Same as abouve
	string href = when.get("http://jsonplaceholder.typicode.com/photos/1")andReturn().jsonPath().getString("url");
		
	System.out.Println(href);
	
	when().get(href).then().statusCode(200);
	
	
	Response res = when.get("http://jsonplaceholder.typicode.com/photos/1").then().extract().respnse();
	System.out.println(res.contentType());
	System.out.println(res.statusCode());
	
	//schema-validator
	when.get("http://jsonplaceholder.typicode.com/photos/1").then().assertThat().body(matchesJsonSchemaInClassparth("scema.json");
	
	
	//groovy 
	body(RestResponse.result.alpha3_code*.length().sum()", greaterThan(10));
	
	String res = get("http://services.groupkt.com/country/get/all").asString();
	List<string> ls = from(res).getList("RestResponse.Result.findAll {it.name.length > 40}.name");
	sop(ls);
	
	
}


XML Based

given().get("http://www.thomas-bayer.com/sqlrest/CUSTOMER/10/").then().body("CUSTOMER.ID", equalTo("10"));

given().get("http://www.thomas-bayer.com/sqlrest/CUSTOMER/10/").then().
	body("CUSTOMER.ID", equalTo("10")).
	body("CUSTOMER.FIRSTNAME", equalTo("Sue")).
	body("CUSTOMER.LASTNAME", equalTo("Fuller"));
	
	given().get("http://www.thomas-bayer.com/sqlrest/CUSTOMER/10/").then().
	body("CUSTOMER.text()", equalTo("10SueFuller125 Upland Pl.Dallas"));

	given().get("http://www.thomas-bayer.com/sqlrest/CUSTOMER/10/").then().body(hasXPath("/CUSTOMER/FIRSTNAME", containsString("Sue"));

	
	given().get("http://www.thomas-bayer.com/sqlrest/INVOICE/").then().body(hasXPath("/INVOICEList/INVOICE[text()='40']"));
	
	

Root Setting

given().
		get("http://services.groupkt.com/country/get/iso2code/IN").
	then().
		root("RestResponse.result")
		body("name", is("italy")).
		body("alpha2_code", is("IT")).
		detachroot("result")
		body("result.alpha3_code", is("ITA"));
		

		
		
//Response Verifiction
given)(.get("www.rams").then().assertThat().statusCode(200).log().all();
given)(.get("www.rams").then().assertThat().statusLine("HTTP/1.1 200 OK);
given)(.get("www.rams").then().assertThat().statusLine(containsString("OK"));

given)(.get("www.rams").then().assertThat().header("x-powered-by", "Express");
given)(.get("www.rams").then().assertThat().headers("x-powered-by", "Express", "ContentType", containsString("json"));

given)(.get("www.rams").then().assertThat().contentType(contentType.JSON);
long to = given().get("http://services.groupkt.com/country/get/iso2code/IN").time();
long to = given().get("http://services.groupkt.com/country/get/iso2code/IN").inTime(TimeUnit.MILLISECONDS);
long to = given().get("http://services.groupkt.com/country/get/iso2code/IN").time(lessThan(400L));


# COnfigure
@BeforeSuite(alwaysRun=true)
	public void Config(){
	RestAssured.baseURI = "Www.google.com"
	RestAssured.port = 8080;
	RestAssured.basePath = "/test"
}

public interface EndPoints{
string GET_EMPLOYEE = "/employee.getExmploee";
}

given().get(Endpoints.GET_EMPLOYEE).


REST API Code


public void getHealthcheckPing() {
        when().get("/ping").
        then().body(containsString("pong!"));
}


    @Test
    public void shouldUploadNewFile() {
        ValidatableResponse response = given()
                .multiPart("file", new File("C:\\1\\RA\\rest-assured\\src\\test\\data\\gomer.png"), "image/png")
                .baseUri(uri)
                .log().all()
                .when()
                .post("/file/upload")
                .then()
                .body("status", equalTo("OK"))
                .log().all();
        String filename = response.extract().path("filename");
        System.out.println(filename);
    }
	
	

@Test
	public void getPlaceAPI() {
		// BaseURL or Host
		RestAssured.baseURI = ReusableMethods.readPropertiesFile("baseUrlApi");
		given().param("location", "-33.8670522,151.1957362").param("radius", "1500")
				.param("key", ReusableMethods.readPropertiesFile("Key")).when().get(ResourceFile.GetLocationApi())
				.then().assertThat().statusCode(200).and().contentType(ContentType.JSON).and()
				.body("results[0].place_id", equalTo("ChIJP3Sa8ziYEmsRUKgyFmh9AQM")).and()
				.header("Server", "scaffolding on HTTPServer2");

	}

	
	@Test
	public void AddandDeletePlace() {

		// Task 1- Grab the response
		RestAssured.baseURI = ReusableMethods.readPropertiesFile("baseUrlApi");
		Response res = given().queryParam("key", ReusableMethods.readPropertiesFile("Key"))
				.body(PayLoad.createLocationApi()).when().post(ResourceFile.createLocationApi()).then().assertThat()
				.statusCode(200).and().contentType(ContentType.JSON).and().body("status", equalTo("OK")).extract()
				.response();

		// Task 2- Grab the Place ID from response
        String responseString = res.asString();
		System.out.println(responseString);
		JsonPath js = new JsonPath(responseString);
		String placeid = js.get("place_id");
		System.out.println(placeid);

		// Task 3 place this place id in the Delete request
		given().queryParam("key", ReusableMethods.readPropertiesFile("Key"))
				.body("{" + "\"place_id\": \"" + placeid + "\"" + "}").when().post(ResourceFile.deleteLocationApi())
				.then().assertThat().statusCode(200).and().contentType(ContentType.JSON).and()
				.body("status", equalTo("OK"));

	}
	

public class CreateCustomerPostCall {

	@Test
	public void createCustomerTest() {
		// 1. define the base url:
		RestAssured.baseURI = "http://restapi.demoqa.com/customer";

		// 2. define the http request:
		RequestSpecification httpRequest = RestAssured.given();

		// 3. create a json object with all the fields:
		org.json.simple.JSONObject requestJson = new org.json.simple.JSONObject();
		requestJson.put("FirstName", "Michael1");
		requestJson.put("LastName", "Peter1");
		requestJson.put("UserName", "micpeter1");
		requestJson.put("Password", "mich1231");
		requestJson.put("Email", "mich@gmail1.com");

		// 4. add header:
		httpRequest.header("Content-Type", "application/json");

		// 5. add the json payload to the body of the request:
		httpRequest.body(requestJson.toJSONString());

		// 6. post the request and get the response:
		Response response = httpRequest.post("/register");

		// 7. get the response body:
		String responseBody = response.getBody().asString();
		System.out.println("Response Body is: " + responseBody);

		// 8. get the status code and validate it:
		int statusCode = response.getStatusCode();
		System.out.println("the status code is: " + statusCode);

		Assert.assertEquals(statusCode, 201);

		System.out.println("the status line is: " + response.getStatusLine());

		// 9. get the headers:
		Headers headers = response.getHeaders();
		System.out.println(headers);

		String contentType = response.getHeader("Content-Type");
		System.out.println("the value of content-type header is: " + contentType);

		String contentLength = response.getHeader("Content-Length");
		System.out.println("the value of Content-Length header is: " + contentLength);
		
		

	}

	
	
	
	@Test
	public void createCustomerTest() {
		// 1. define the base url:
		RestAssured.baseURI = "http://restapi.demoqa.com/customer";

		// 2. define the http request:
		RequestSpecification httpRequest = RestAssured.given();

		// 3. create a json object with all the fields:
		org.json.simple.JSONObject requestJson = new org.json.simple.JSONObject();
		requestJson.put("FirstName", "Michael13");
		requestJson.put("LastName", "Peter1312");
		requestJson.put("UserName", "micpeter1132");
		requestJson.put("Password", "mich1231132");
		requestJson.put("Email", "mich@gmail2311.com");

		// 4. add header:
		httpRequest.header("Content-Type", "application/json");

		// 5. add the json payload to the body of the request:
		httpRequest.body(requestJson.toJSONString());

		// 6. post the request and get the response:
		Response response = httpRequest.post("/register");

		// 7. get the response body:
		String responseBody = response.getBody().asString();
		System.out.println("Response Body is: " + responseBody);

		// Deserialization the response into CustomerResponse class:
		if (response.statusCode() == 201) {
			CustomerResponseSuccess customerResponse = response.as(CustomerResponseSuccess.class);

			System.out.println(customerResponse.SuccessCode);
			System.out.println(customerResponse.Message);

			Assert.assertEquals("OPERATION_SUCCESS", customerResponse.SuccessCode);
			Assert.assertEquals("Operation completed successfully", customerResponse.Message);
		} 
		else if (response.statusCode() == 200) {
			CustomerResponseFailure customerResponse = response.as(CustomerResponseFailure.class);

			System.out.println(customerResponse.FaultId);
			System.out.println(customerResponse.fault);

			Assert.assertEquals("User already exists", customerResponse.FaultId);
			Assert.assertEquals("FAULT_USER_ALREADY_EXISTS", customerResponse.fault);
		}

	}
	
	
	
	
	@Test
	public void getWeatherDetailsWithCorrectCityNameTest(){
		
		//1. define the base url
		//http://restapi.demoqa.com/utilities/weather/city
		RestAssured.baseURI = "http://restapi.demoqa.com/utilities/weather/city";
		
		//2. define the http request:
		RequestSpecification httpRequest = RestAssured.given();
		
		//3. make a request/execute the request:
		Response response = httpRequest.request(Method.GET, "/Pune");
		
		//4. get the response body:
		String responseBody = response.getBody().asString();
		System.out.println("Response Body is: "+ responseBody);
		//validate city name or validate the key or value
		Assert.assertEquals(responseBody.contains("Pune"), true);
		
		//5. get the status code and validate it:
		int statusCode = response.getStatusCode();
		System.out.println("the status code is: "+ statusCode);
		
		Assert.assertEquals(statusCode, 200);
		
		System.out.println("the status line is: "+ response.getStatusLine());
		
		//6. get the headers:
		Headers headers = response.getHeaders();
		System.out.println(headers);
		
		String contentType = response.getHeader("Content-Type");
		System.out.println("the value of content-type header is: "+ contentType);
		
		String contentLength = response.getHeader("Content-Length");
		System.out.println("the value of Content-Length header is: "+ contentLength);

		//get the key value by using JsonPath:
		JsonPath jsonPathValue = response.jsonPath();
		String city = jsonPathValue.get("City");
		System.out.println("the value of city is: "+ city);
		
		String temp = jsonPathValue.get("Temperature");
		System.out.println("the value of Temperature is: "+ temp);

		String Humidity = jsonPathValue.get("Humidity");
		System.out.println("the value of Humidity is: "+ Humidity);

		String WeatherDescription = jsonPathValue.get("WeatherDescription");
		System.out.println("the value of WeatherDescription is: "+ WeatherDescription);

		String WindSpeed = jsonPathValue.get("WindSpeed");
		System.out.println("the value of WindSpeed is: "+ WindSpeed);

		String WindDirectionDegree = jsonPathValue.get("WindDirectionDegree");
		System.out.println("the value of WindDirectionDegree is: "+ WindDirectionDegree);

		
		
	}
	
	
	@Test
	public void getWeatherDetailsWithInCorrectCityNameTest(){
		
		//1. define the base url
		//http://restapi.demoqa.com/utilities/weather/city
		RestAssured.baseURI = "http://restapi.demoqa.com/utilities/weather/city";
		
		//2. define the http request:
		RequestSpecification httpRequest = RestAssured.given();
		
		//3. make a request/execute the request:
		Response response = httpRequest.request(Method.GET, "/test123");
		
		//4. get the response body:
		String responseBody = response.getBody().asString();
		System.out.println("Respjnse Body is: "+ responseBody);
		//validate city name or validate the key or value
		Assert.assertEquals(responseBody.contains("internal error"), true);
		
		//5. get the status code and validate it:
		int statusCode = response.getStatusCode();
		System.out.println("the status code is: "+ statusCode);
		
		Assert.assertEquals(statusCode, 400);
	
	}
	
	
	



RestAssured.baseURI = "http://myhost.org";
RestAssured.basePath = "/resource";
RestAssured.port = getApplicationPort(applicationName);
RestAssured.config().redirect(RedirectConfig.redirectConfig().followRedirects(false));
RestAssured.enableLoggingOfRequestAndResponseIfValidationFails();
RestAssured.reset();
RestAssured.port = 80;
RestAssured.authentication = basic("username", "password");
RestAssured.rootPath = "store.book";
 
 
JsonPath response = RestAssured.given().when().delete(TYPE_API).then().statusCode(405).extract().jsonPath();
Assert.assertEquals("Request method 'DELETE' not supported", response.getString("message"));
Assert.assertEquals("Method Not Allowed", response.getString("error"));
	

String port = System.getProperty("server.port");
RestAssured.port = (port == null) ? 8082 : Integer.valueOf(port);


@BeforeClass
public static void startApp() {

    RestAssured.config = RestAssured.config().sessionConfig(new SessionConfig().sessionIdName("APPSESSIONID"));
    RestAssured.enableLoggingOfRequestAndResponseIfValidationFails();
    RestAssured.port = 9090;

    Thread thread = new Thread(() -> {
        try {
            JettyApp.main(new String[]{Integer.toString(RestAssured.port)});
        } catch (Exception e) {
            e.printStackTrace();
        }
    });
    thread.start();
    // give the app time to spin up
    try {
        Thread.sleep(3000);
    } catch (InterruptedException ex) {
        Thread.currentThread().interrupt();
    }

}
 
 
  restAssured.given().get("/base/data").andReturn();
  


**Given**= a context or Getting a system in a particular state
**When**= something happens or Poke it
**Then**=we expect some outcome or examine the new state

@Test
public void testGetSingleUserProgrammatic() {
  Response res = get("/service/single-user");
  assertEquals(200, res.getStatusCode());
  String json = res.asString();
  JsonPath jp = new JsonPath(json);
  assertEquals("test@hascode.com", jp.get("email"));
  assertEquals("Tim", jp.get("firstName"));
  assertEquals("Testerman", jp.get("lastName"));
  assertEquals("1", jp.get("id"));
}

@Test
public void testFindUsingGroovyClosure() {
  String json = get("/service/persons/json").asString();
  JsonPath jp = new JsonPath(json);
  jp.setRoot("person");
  Map person = jp.get("find {e -> e.email =~ /test@/}");
  assertEquals("test@hascode.com", person.get("email"));
  assertEquals("Tim", person.get("firstName"));
  assertEquals("Testerman", person.get("lastName"));
}


@Test
public void testGetSingleUserAsXml() {
  expect().
    statusCode(200).
    body(
      "user.email", equalTo("test@hascode.com"),
      "user.firstName", equalTo("Tim"),
      "user.lastName", equalTo("Testerman"),
      "user.id", equalTo("1")).
    when().
    get("/service/single-user/xml");
}


@Test
public void testGetSingleUserAgainstSchema() {
  InputStream xsd = getClass().getResourceAsStream("/user.xsd");
  assertNotNull(xsd);
  expect().
  statusCode(200).
  body(
    matchesXsd(xsd)).
  when().
  get("/service/single-user/xml");
}


@Test
public void testCreateuser() {
  final String email = "test@hascode.com";
  final String firstName = "Tim";
  final String lastName = "Tester";
 
  given().
    parameters(
      "email", email,
      "firstName", firstName,
      "lastName", lastName).
  expect().
    body("email", equalTo(email)).
    body("firstName", equalTo(firstName)).
    body("lastName", equalTo(lastName)).
  when().
  get("/service/user/create");
}


@Test
public void testAuthenticationWorking() {
  // we're not authenticated, service returns "401 Unauthorized"
  expect().
    statusCode(401).
  when().
  get("/service/secure/person");
 
  // with authentication it is working
  expect().
    statusCode(200).
  when().
    with().
      authentication().basic("admin", "admin").
  get("/service/secure/person");
}


@Test
public void testSetRequestHeaders() {
  expect().
    body(equalTo("TEST")).
  when().
    with().
    header("myparam", "TEST").
  get("/service/header/print");
 
  expect().
    body(equalTo("foo")).
  when().
    with().
    header("myparam", "foo").
  get("/service/header/print");
}


@Test
public void testReturnedHeaders() {
  expect().
    headers("customHeader1", "foo", "anotherHeader", "bar").
  when().
  get("/service/header/multiple");
}


@Test
public void testAccessSecuredByCookie() {
  expect().
    statusCode(403).
  when().
  get("/service/access/cookie-token-secured");
 
  given().
    cookie("authtoken", "abcdef").
  expect().
    statusCode(200).
  when().
  get("/service/access/cookie-token-secured");
}


@Test
public void testModifyCookie() {
  expect().
    cookie("userName", equalTo("Ted")).
  when().
    with().param("name", "Ted").
  get("/service/cookie/modify");
 
  expect().
    cookie("userName", equalTo("Bill")).
  when().
    with().param("name", "Bill").
  get("/service/cookie/modify");
}


@Test
public void testFileUpload() {
  final File file = new File(getClass().getClassLoader()
      .getResource("test.txt").getFile());
  assertNotNull(file);
  assertTrue(file.canRead());
  given().
    multiPart(file).
  expect().
    body(equalTo("This is an uploaded test file.")).
  when().
  post("/service/file/upload");
}



@Test
public void testSpecReuse() {
  ResponseSpecBuilder builder = new ResponseSpecBuilder();
  builder.expectStatusCode(200);
  builder.expectBody("email", equalTo("test@hascode.com"));
  builder.expectBody("firstName", equalTo("Tim"));
  builder.expectBody("lastName", equalTo("Testerman"));
  builder.expectBody("id", equalTo("1"));
  ResponseSpecification responseSpec = builder.build();
 
  // now we're able to use this specification for this test
  expect().
    spec(responseSpec).
  when().
  get("/service/single-user");
 
  // now re-use for another test that returns similar data .. you may
  // extend the specification with further tests as you wish
  final String email = "test@hascode.com";
  final String firstName = "Tim";
  final String lastName = "Testerman";
 
  expect().
    spec(responseSpec).
  when().
    with().
    parameters(
      "email", email,
      "firstName", firstName,
      "lastName",lastName).
  get("/service/user/create");
}


@Before
 public void setUp(){
 RestAssured.basePath = "yourbasepath";
RestAssured.port = config.getInteger("server.port");
 }


@Test
public void testStatusPage()
{
  expect()
     .statusCode(200)
     .log().ifError()
  .when()
     .get("/status/server");
}


req.given().when().get().then().log().ifValidationFails().statusCode(200);

https://stackoverflow.com/questions/32182479/rest-assured-size-of-json-response?rq=1

Scem Validation
https://github.com/rest-assured/rest-assured/blob/master/examples/rest-assured-itest-java/src/test/java/io/restassured/itest/java/JsonSchemaValidationITest.java


https://github.com/rest-assured/rest-assured/tree/master/examples/rest-assured-itest-java/src/test/java/io/restassured/itest/java


# Auth - https://github.com/rest-assured/rest-assured/blob/master/examples/rest-assured-itest-java/src/test/java/io/restassured/itest/java/AuthenticationITest.java

	@Test
    public void basicAuthentication() throws Exception {
        given().auth().basic("jetty", "jetty").expect().statusCode(200).when().get("/secured/hello");
    }


    @Test
    public void explicitExcludeOfBasicAuthenticationWhenUsingDefault() throws Exception {
        authentication = basic("jetty", "jetty");
        try {
            given().auth().none().and().expect().statusCode(401).when().get("/secured/hello");
        } finally {
            RestAssured.reset();
        }
    }


    @Test
    public void supportsPreemptiveBasicAuthentication() throws Exception {
        given().auth().preemptive().basic("jetty", "jetty").expect().statusCode(200).when().get("/secured/hello");
    }

    @Test
    public void supportsExpectingStatusCodeWhenPreemptiveBasicAuthenticationError() throws Exception {
        given().auth().preemptive().basic("jetty", "bad password").expect().statusCode(401).when().get("/secured/hello");
    }

	

expect().statusCode(HttpStatus.SC_OK)
    .given()
    .parameters("user", user, "password", URL)
    .cookie("cookie_name", "cookie_value")
    .post("/someURL");
	

@Test
public void loginAndLogout(){
    final String login = randomLogin();
    // First post to login()
    given()
    .queryParam("login", login)
    .queryParam("password", randomPassword())
    .when().post("/login/");    

    // Second post to logout() with an assert
    expect().statusCode(200)
    .given()
    .when().post("/logout/");   
}


## Getting and parsing a response body:

// Example with JsonPath
String json = get("/lotto").asString()
List<String> winnderIds = from(json).get("lotto.winners.winnerId");
    
// Example with XmlPath
String xml = post("/shopping").andReturn().body().asString()
Node category = from(xml).get("shopping.category[0]");



package com.googlerestapi.com.rest;

import org.testng.Assert;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;
import com.jayway.jsonpath.JsonPath;
import com.jayway.restassured.RestAssured;
import com.jayway.restassured.response.Response;
import com.jayway.restassured.specification.RequestSpecification;

import static com.jayway.restassured.RestAssured.*;

public class NewTest {
 

	 @BeforeClass
	  public void setBaseUri () {

	    RestAssured.baseURI = "https://maps.googleapis.com";
	  }

	 
	 @Test
     public void makeSureThatGoogleIsUp() {
         given().when().get("http://www.google.com").then().statusCode(200);
     }
	 
	 /*

	 @Test public void
	    extract_response_as_string_works() {
	        String body = get("https://reqres.in/api/users/2").then().assertThat().contentType().and().extract().body().asString();

	       System.out.println(body);
	    }
*/
	 
	 public void DisplayAllNodesInWeatherAPI()
	 {
	  RestAssured.baseURI = "http://restapi.demoqa.com/utilities/weather/city";
	  RequestSpecification httpRequest = RestAssured.given();
	  Response response = httpRequest.get("/Hyderabad");
	  
	  // First get the JsonPath object instance from the Response interface
	  JsonPath jsonPathEvaluator = response.jsonPath();
	  
	  // Let us print the city variable to see what we got
	  System.out.println("City received from Response " + jsonPathEvaluator.get("City"));
	  
	  // Print the temperature node
	  System.out.println("Temperature received from Response " + jsonPathEvaluator.get("Temperature"));
	  
	  // Print the humidity node
	  System.out.println("Humidity received from Response " + jsonPathEvaluator.get("Humidity"));
	  
	  // Print weather description
	  System.out.println("Weather description received from Response " + jsonPathEvaluator.get("Weather"));
	  
	  // Print Wind Speed
	  System.out.println("City received from Response " + jsonPathEvaluator.get("WindSpeed"));
	  
	  // Print Wind Direction Degree
	  System.out.println("City received from Response " + jsonPathEvaluator.get("WindDirectionDegree"));
	 }
	 
	 /*
	 @Test
	    public void aCarGoesIntoTheGarage() {
	        Map<String,String> car = new HashMap<>();
	        car.put("plateNumber", "xyx1111");
	        car.put("brand", "audi");
	        car.put("colour", "red");

	        given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .statusCode(200);
	    }
	 
	 
	 @Test
	    public void basicPingTest() {
	        given().when().get("/garage").then().statusCode(200);
	    }
	 
	 
	   @Test
	    public void invalidParkingSpace() {
	        given().when().get("/garage/slots/999")
	            .then().statusCode(404);
	    }
	   
	   @Test
	    public void verifyNameOfGarage() {
	        given().when().get("/garage").then()
	            .body(containsString("Acme garage"));
	    }
	   
	   
	   @Test
	    public void verifyNameStructured() {
	        given().when().get("/garage").then()
	            .body("name",equalTo("Acme garage"));
	    }
	   
	   
	   @Test
	    public void verifySlotsOfGarage() {
	        given().when().get("/garage").then().
	            body("info.slots",equalTo(150))
	                .body("info.status",equalTo("open"));
	    }
	   
	   
	   @Test
	    public void verifyTopLevelURL() {
	        given().when().get("/garage").then()
	        .body("name",equalTo("Acme garage"))
	        .body("info.slots",equalTo(150))
	        .body("info.status",equalTo("open"))
	        .statusCode(200);
	    }
	   
	   
	   @Test
	    public void aCarGoesIntoTheGarage() {
	        Map<String,String> car = new HashMap<>();
	        car.put("plateNumber", "xyx1111");
	        car.put("brand", "audi");
	        car.put("colour", "red");

	        given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .statusCode(200);
	    }
	   
	   
	   @Test
	    public void aCarGoesIntoTheGarageStructured() {
	        Map<String,String> car = new HashMap<>();
	        car.put("plateNumber", "xyx1111");
	        car.put("brand", "audi");
	        car.put("colour", "red");

	        given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .body("empty",equalTo(false))
	        .body("position",lessThan(150));
	    }
	   
	   
	   @Test
	    public void aCarObjectGoesIntoTheGarage() {
	        Car car = new Car();
	        car.setPlateNumber("xyx1111");
	        car.setBrand("audi");
	        car.setColour("red");

	        given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .body("empty",equalTo(false))
	        .body("position",lessThan(150));
	    }
	   
	   
	   @Test
	    public void aCarIsRegisteredInTheGarage() {
	        Car car = new Car();
	        car.setPlateNumber("xyx1111");
	        car.setBrand("audi");
	        car.setColour("red");

	        Slot slot = given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots")
	        .as(Slot.class);

	        assertFalse(slot.isEmpty());
	        assertTrue(slot.getPosition() < 150);

	    }
	   
	   
	   @Test
	    public void aCarLeaves() {
	        given().pathParam("slotID", 27)
	        .when().delete("/garage/slots/{slotID}")
	        .then().statusCode(200);

	    }
	   
	   
	   @Test
	    public void aCarEntersAndThenLeaves() {
	        Car car = new Car();
	        car.setPlateNumber("xyx1111");
	        car.setBrand("audi");
	        car.setColour("red");

	        int positionTakenInGarage = given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .body("empty",equalTo(false))
	        .extract().path("position");

	        given().pathParam("slotID", positionTakenInGarage)
	        .when().delete("/garage/slots/{slotID}").then()
	        .statusCode(200);

	    }
	   
	   
	 @Test
	  public void testStatusCode () {
	    
	    Response res = 
	    given ()
	    .param ("query", "restaurants in mumbai")
	    .param ("key", "Xyz")
	    .when()
	    .get ("/maps/api/place/textsearch/json");

	    Assert.assertEquals (res.statusCode (), 200);
	  }

	@Test
	public void testStatusCodeRestAssured () {

	given ().param ("query", "restaurants in mumbai")
	        .param ("key", "Xyz")
	        .when()
	        .get ("/maps/api/place/textsearch/json")
	        .then ()
	        .assertThat ().statusCode (200);

	}*/

	
  
}


package com.googlerestapi.com.rest;

import org.testng.Assert;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;

import com.jayway.restassured.RestAssured;
import com.jayway.restassured.response.Response;

import static com.jayway.restassured.RestAssured.*;

public class NewTest {
 

	 @BeforeClass
	  public void setBaseUri () {

	    RestAssured.baseURI = "https://maps.googleapis.com";
	  }

	 
	 @Test
     public void makeSureThatGoogleIsUp() {
         given().when().get("http://www.google.com").then().statusCode(200);
     }
	 
	 @Test
	    public void aCarGoesIntoTheGarage() {
	        Map<String,String> car = new HashMap<>();
	        car.put("plateNumber", "xyx1111");
	        car.put("brand", "audi");
	        car.put("colour", "red");

	        given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .statusCode(200);
	    }
	 
	 
	 @Test
	    public void basicPingTest() {
	        given().when().get("/garage").then().statusCode(200);
	    }
	 
	 
	   @Test
	    public void invalidParkingSpace() {
	        given().when().get("/garage/slots/999")
	            .then().statusCode(404);
	    }
	   
	   @Test
	    public void verifyNameOfGarage() {
	        given().when().get("/garage").then()
	            .body(containsString("Acme garage"));
	    }
	   
	   
	   @Test
	    public void verifyNameStructured() {
	        given().when().get("/garage").then()
	            .body("name",equalTo("Acme garage"));
	    }
	   
	   
	   @Test
	    public void verifySlotsOfGarage() {
	        given().when().get("/garage").then().
	            body("info.slots",equalTo(150))
	                .body("info.status",equalTo("open"));
	    }
	   
	   
	   @Test
	    public void verifyTopLevelURL() {
	        given().when().get("/garage").then()
	        .body("name",equalTo("Acme garage"))
	        .body("info.slots",equalTo(150))
	        .body("info.status",equalTo("open"))
	        .statusCode(200);
	    }
	   
	   
	   @Test
	    public void aCarGoesIntoTheGarage() {
	        Map<String,String> car = new HashMap<>();
	        car.put("plateNumber", "xyx1111");
	        car.put("brand", "audi");
	        car.put("colour", "red");

	        given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .statusCode(200);
	    }
	   
	   
	   @Test
	    public void aCarGoesIntoTheGarageStructured() {
	        Map<String,String> car = new HashMap<>();
	        car.put("plateNumber", "xyx1111");
	        car.put("brand", "audi");
	        car.put("colour", "red");

	        given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .body("empty",equalTo(false))
	        .body("position",lessThan(150));
	    }
	   
	   
	   @Test
	    public void aCarObjectGoesIntoTheGarage() {
	        Car car = new Car();
	        car.setPlateNumber("xyx1111");
	        car.setBrand("audi");
	        car.setColour("red");

	        given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .body("empty",equalTo(false))
	        .body("position",lessThan(150));
	    }
	   
	   
	   @Test
	    public void aCarIsRegisteredInTheGarage() {
	        Car car = new Car();
	        car.setPlateNumber("xyx1111");
	        car.setBrand("audi");
	        car.setColour("red");

	        Slot slot = given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots")
	        .as(Slot.class);

	        assertFalse(slot.isEmpty());
	        assertTrue(slot.getPosition() < 150);

	    }
	   
	   
	   @Test
	    public void aCarLeaves() {
	        given().pathParam("slotID", 27)
	        .when().delete("/garage/slots/{slotID}")
	        .then().statusCode(200);

	    }
	   
	   
	   @Test
	    public void aCarEntersAndThenLeaves() {
	        Car car = new Car();
	        car.setPlateNumber("xyx1111");
	        car.setBrand("audi");
	        car.setColour("red");

	        int positionTakenInGarage = given()
	        .contentType("application/json")
	        .body(car)
	        .when().post("/garage/slots").then()
	        .body("empty",equalTo(false))
	        .extract().path("position");

	        given().pathParam("slotID", positionTakenInGarage)
	        .when().delete("/garage/slots/{slotID}").then()
	        .statusCode(200);

	    }
	   
	   
	 @Test
	  public void testStatusCode () {
	    
	    Response res = 
	    given ()
	    .param ("query", "restaurants in mumbai")
	    .param ("key", "Xyz")
	    .when()
	    .get ("/maps/api/place/textsearch/json");

	    Assert.assertEquals (res.statusCode (), 200);
	  }

	@Test
	public void testStatusCodeRestAssured () {

	given ().param ("query", "restaurants in mumbai")
	        .param ("key", "Xyz")
	        .when()
	        .get ("/maps/api/place/textsearch/json")
	        .then ()
	        .assertThat ().statusCode (200);

	}

	
  
}




//You don't have to extract the response to validate this. You can just do like this:
given().
       header("authToken",userToken).
when().
       get("/students").
then().
       contentType(ContentType.JSON).
       body("list.size()", is(5));

//But if you want to extract it from the response you can as well:

Response response = 
given().
       header("authToken",userToken).
when().
       get("/students").
then().
       contentType(ContentType.JSON).
extract().
       response(); 
int sizeOfList = response.body().path("list.size()");


//If you're only interested in the size of the list and nothing else you can do like this:
int sizeOfList = 
given().
       header("authToken",userToken).
when().
       get("/students").
then().
       contentType(ContentType.JSON).
extract().
       path("list.size()"); 
	   

@Test
public void testStatusPage()
{
  expect()
     .statusCode(200)
     .log().ifError()
  .when()
     .get("/status/server");
}

given()
   .auth().basic("user","name23")
.expect()
   .statusCode(401)
.when()
   .get("/rest/status"); 
   

@Before
public void setUp() {
   RestAssured.authentication = basic("rhqadmin","rhqadmin");
}



AlertDefinition alertDefinition = new AlertDefinition(….);
Header acceptJson = new Header("Accept", "application/json")
 
AlertDefinition result =
given()
   .contentType(ContentType.JSON)
   .header(acceptJson)
   .body(alertDefinition)
   .log().everything()
   .queryParam("resourceId", 10001)
.expect()
   .statusCode(201)
   .log().ifError()
.when()
   .post("/alert/definitions")
.as(AlertDefinition.class);



// Do an OPTIONS call to the remote and then translate into JsonPath
JsonPath jsonPath =
    given()
      .header("Accept",APPLICATION_JSON)
    .options("http://localhost:8080/metrics/vendor")
      .extract().body().jsonPath();
 
// Now find the buffer direct pool
Map<String,String> aMap = jsonPath.getMap("find {it.name == 'BufferPool_used_memory_direct'}");
// And make sure its display name is correct
assert directPool.get("displayName").equals("BufferPool_used_memory_direct");


when()
   .get("http://localhost:8080/metrics/base")
.then()
   .header("ETag",notNullValue())
   .body("scheduleId", hasItem( numericScheduleId)) 
   .body(containsString("total-started-thread-count"));
      
   Response temp =RestAssured.get("https://samples.openweathermap.org/data/2.5/weather?q=London,uk&appid=b6907d289e10d714a6e88b30761fae22");		
String Sessionid =temp.getSessionId();
System.out.println("Session ID "+Sessionid);
System.out.println("Body :: "+temp.body());		
System.out.println("Body XML Path :: "+temp.body().xmlPath());
System.out.println("getSessionId "+temp.getSessionId());
System.out.println("getStatusLine "+temp.getStatusLine());
System.out.println("Time "+temp.getTime());
System.out.println("getContentType "+temp.getContentType());
System.out.println("detailedCookies "+temp.detailedCookies());
System.out.println("contentType "+temp.contentType());
System.out.println("getTimeIn "+temp.getTimeIn(TimeUnit.MILLISECONDS));


ResponseBody<?>  temp = RestAssured.get(
				"https://samples.openweathermap.org/data/2.5/weather?q=London,uk&appid=b6907d289e10d714a6e88b30761fae22").getBody();
		JsonPath  path = temp.jsonPath();
		System.out.println("Json Path od Response : "+path);
		System.out.println(temp);
		
		
String text = RestAssured.get("http://restcountries.eu/rest/v1").asString();
System.out.println(text);


RestAssured.baseURI= "https://developers.zomato.com/api/v2.1/";
Header someHeader = new Header("user-key","a9a8b860396953c3de905e9ad8283dff");
System.out.println(RestAssured.given().header(someHeader).when().get("cuisines?city_id=5").getStatusCode());
Response request = RestAssured.given().header(someHeader).when().get("cuisines?city_id=5");
System.out.println(request.body().asString());
System.out.println(request.contentType());
System.out.println(request.getSessionId());
System.out.println(request.getStatusLine());
System.out.println(request.getTime());
System.out.println(request.cookies());
System.out.println(request.getHeaders());


RestAssured.baseURI= "https://developers.zomato.com/api/v2.1/";
Response repvalue = RestAssured.given().header("user-key","a9a8b860396953c3de905e9ad8283dff").when().get("cities?q=jhansi");
System.out.println(repvalue.body());
System.out.println(repvalue.getBody().asString());
System.out.println("City ID :: "+repvalue.body().jsonPath().get("location_suggestions.id"));
		
		
		
RequestSpecification request = given();
request.header("Content-Type", "application/json");

JSONObject json = new JSONObject();
json.put("author", "Abhishek 06");
json.put("created", "2018-08-20T15:08:07.200");
json.put("message", "Hello WebServices Programming6");

request.body(json.toJSONString());
Response response = request.post("http://localhost:8080/messenger3/webapi/messages");
int statusCode = response.getStatusCode();
System.out.println("Status code after msg creation is " + statusCode);
Assert.assertEquals(statusCode, 201);
		

@Test
	public void verifyDeleteRequest() {

		RequestSpecification request = given();
		// request.header("Content-Type","application/json");
		Response response = request.delete("http://localhost:8080/messenger3/webapi/messages/6");
		int statusCode = response.getStatusCode();
		System.out.println("Status code is " + statusCode);
		// Assert.assertEquals(statusCode, 200);

	}

public static String getLoginSessionID() throws IOException{
		log.info("Inside  getLoginSessionID() method");
		
		String loginPayload = PayloadParser.generatePayloadString("JIRALogin.json");
		String endPointURI = URL.getEndPoint("rest/auth/1/session");
		Response loginResponse = RESTCalls.POSTRequest(endPointURI, loginPayload);
		String sessionID = TestUtils.extractJSONResponseValue(loginResponse, "session.value");
		
		log.info("Current JIRA JSessionID = " + sessionID);
		
		return sessionID;
	}


	
	public static Response GETRequest(String URI){
		RequestSpecification requestSpecs = RestAssured.given().contentType(ContentType.JSON);
		Response response = requestSpecs.get(URI); 
		
		log.info("Inside GETRequest call");
		log.debug(requestSpecs.log().all());
		
		return response;
	}
	
	
	
		
