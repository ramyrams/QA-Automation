 # Extracting a JSON Response with Rest-Assured
 
 Response res  = given ().param ("query", "Churchgate Station")
     .param ("key", "Xyz")
     .when()
     .get ("/maps/api/place/textsearch/json")
     .then()
     .contentType(ContentType.JSON)
     .extract().response();


     System.out.println (res.asString ());

	 RestAssured.baseURI = "https://maps.googleapis.com"; 
 Response res  =given ().param ("query", "Churchgate Station")
    .param ("key", "Xyz")
    .when()
    .get ("/maps/api/place/textsearch/json").
    .then()
    .contentType(ContentType.JSON)
    .extract().
    .path ("results[0].formatted_address");
    
    Assert.assertEquals (res, "Maharshi Karve Rd, Churchgate, Mumbai, Maharashtra 400020");
  
# Logging in Rest Assured ( Request Logging ) - Part 1

* **log().all() :** By adding log().all() to the request you’ll receive detailed information what the client sends to the server i.e. all the request specification details like parameters, header and body.
* **log().params() :** By adding log().params() to the request you'll receive information about what the client sends in the request parameters.
* **log().body() :** By adding log().body() to the request you'll receive information about what the client sends in the request body.
* **log().headers() :** By adding log().headers() to the request you'll receive information about what the client sends in the request headers.
* **log().cookies() :** By adding log().cookies() to the request you'll receive information about what the client sends in the request cookies.
* **log().method() :** By adding log().method() to the request you'll receive information about what the client sends in the request method.
* **log().path() :** By adding log().path() to the request you'll receive information about what the client sends in the request path.
* **log().body() :** By adding log().body() to the response you'll receive information about what the server sends in the response body. It will log the response even if error has occured.
* **log().all().ifError() :** By adding log().ifError().body() to the response you'll receive information about what the sever sends in the response body only if error occurs.
* **log().status() :** By adding log().status() to the response you'll receive information about what the sever sends as the status.
* **log().headers() :** By adding log().headers() to the response you'll receive information about what headers the server send.
* **log().cookies() :** By adding log().cookies() to the response you'll receive information about cookies.
* **log().ifStatusCodeIsEqualTo(status code) :** By adding log().ifStatusCodeIsEqualTo(status code) to the response you can configure to log the response only if status code matches some value.
* **log().ifStatusCodeMatches(matcher) :** By adding     log().ifStatusCodeMatches(matcher) to the response you can configure to log the response only if status code matches the value supplied by Hamcrest matcher.
* **log().ifValidationFails() :** By adding log().ifValidationFails() to the response you can configure to log the response only if the added validation to response fails like ContentType returned is xml instead of JSON.
* **RestAssured.enableLoggingOfRequestAndResponseIfValidationFails() :** By adding above method in beforeClass you can enable logs for both Request and Response if the validation fails. It will act as a shortcut for multiple tests.
* **given().config(RestAssured.config().logConfig (LogConfig.logConfig ().enableLoggingOfRequestAndResponseIfValidationFails (LogDetail.HEADERS))) :** By adding above method you can configure to log both request and response if the validation fails, where HEADERS can be replaced with ALL, body, Cookies, Method, Params, Status and Uri. In this case it will log only headers. 


given()
         .param ("query", "Churchgate Station")
         .param ("key","XYZ" )
         .when ()
         .get ("/maps/api/place/textsearch/json")
         .then ()
         .log ().ifError ().assertThat ().statusCode (200);
		 
		 
