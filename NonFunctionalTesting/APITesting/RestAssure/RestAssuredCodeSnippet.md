Soap vs Rest

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
	given().get("www.google.com).then().statusCode(200);
	given().get("www.google.com).then().statusCode(200).log().all();
	
	given().get("http://services.groupkt.com/country/get/iso2code/IN").then().body("RestResponse.result.name", equalTo("United States of America"));
	given().get("http://services.groupkt.com/country/get/all").then().body("RestResponse.result.name", hasItems("Argentina", "Australia"));
	
	given().
		param("key1", "value").
		header("head", "value").
		queryParam("df", "dfd").
		formParam("df", "dfd").
		param("df", "dfd") - it automatically detedct and convert QuertParam for GET and POST it will tread as formParam
		
	
	when().
		get("http://services.groupkt.com/country/get/iso2code/IN").
	then().
		.statusCode(200).log().all();
		
		
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
	
	
	
