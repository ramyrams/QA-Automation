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
