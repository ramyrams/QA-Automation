```javascript
/**************************************************************************************************
** POST Method - Common for any API -> Basic validation
***************************************************************************************************/


var messageTitle = 'GetSourceSystemLkp Successfull';
var responseKeys = ['message', 'hasError', 'errorMessage', 'statusCode', 'errorLogID', 'model', 'modelList'];
var modelKeys = ['sourceSystemID', 'sourceSystemName', 'recCreatedBy', 'recUpdatedBy']
var SQL = "SELECT * FROM [Import].[RoleLkp] WHERE RoleID = ";

/*----------------------------------------------------
Common for any API -> Basic validation
----------------------------------------------------*/

//Common Test:1->Basic Test: Is URL up and running
pm.test("Verify the API endpoint is up and running: " + pm.environment.get('APIURL') + pm.request.url.getPath(), function(){
	// info, success, redirection, clientError,  serverError, are other variants
	pm.response.to.be.ok;
	
	pm.response.to.have.status(200);
});

//Common Test:2->Basic Test: is there any error in the response 
pm.test("Verify the response doesn't have any error", function () { 
	pm.response.to.not.be.error; 
	pm.response.to.not.have.jsonBody("error"); 
});

//Common Test:3->Basic Test: response should have more than 0
pm.test("Verify the response has more than 0 rows, Verify the response body is in JSON format", function () { 
	console.log(pm.response.json().length)
	// this assertion also checks if a body  exists, so the above check is not needed
	pm.response.to.be.withBody;
	
	 // assert that the response has a valid JSON body
	pm.response.to.be.json; 

	pm.response.to.have.jsonBody(); 
});    

//Common Test:4->Header Test: Response should have Content-Type header and it should be application/json; charset=utf-8
pm.test("Verify the value of Response header of Content-Type is application/json; charset=utf-8", function () { 
   pm.response.to.be.header("Content-Type", 'application/json; charset=utf-8');
});

//Common Test:5->Performance Test: response should received within 5 seconds
pm.test("Verify the response returns in less than 2 sec", function(){
	pm.expect(pm.response.responseTime).to.be.below(2000);
});


/**************************************************************************************************
** POST Method - Common for any end point -> Common verification for all the API in a given project
***************************************************************************************************/

/*---------------------------------------------------------------------------------
Common for any end point -> Common verification for all the API in a given project
-----------------------------------------------------------------------------------*/

//Data Stucture Test1: The columns should be exist, is all the column exists as per the model 
pm.test("Verify the response JSON body contains expected data column as per the schema", function () {
     var responseParentJSON = pm.response.json();
     pm.expect(responseParentJSON).to.have.all.keys(responseKeys);
     
})


/*----------------------------------------------------
Response body validatation
----------------------------------------------------*/
pm.test("Verify the reponse message has GetDepartmentType Successfull", function(){
    pm.expect(pm.response.json().message).to.eql(messageTitle);
});

pm.test("Verify the reponse message hasError is false", function(){
    pm.expect(pm.response.json().hasError).to.eql(false);
});

pm.test("Verify the reponse message errorMessage is null", function(){
    pm.expect(pm.response.json().errorMessage).to.eql(null);
});

pm.test("Verify the reponse message statusCode is 201", function(){
    pm.expect(pm.response.json().statusCode).to.eql(201);
});

pm.test("Verify the reponse message errorLogID is 0", function(){
    pm.expect(pm.response.json().errorLogID).to.eql(0);
});

//Data Stucture Test1: model should have response model
pm.test("Verify the response JSON body contains data", function () {
    pm.expect(pm.response.json().model).to.be.an('object');
})

pm.test("Verify the reponse message modelList is null", function(){
    pm.expect(pm.response.json().modelList).to.eql(null);
});



/**************************************************************************************************
** POST Method - Specific for endpoint
***************************************************************************************************/
//Data Stucture Test1: The columns should be exist, is all the column exists as per the schema 
pm.test("Verify the response JSON body contains expected data column as per the schema", function () {
     var responseListJSON = pm.response.json().model;
    pm.expect(responseListJSON).to.have.all.keys(modelKeys);
})


/*----------------------------------------------------
Data type validation
----------------------------------------------------*/
pm.test("Verify the reponse data type", function(){
    var responseJSON = pm.response.json().model;
    pm.expect(responseJSON.departmentID).to.be.an('number');
	pm.expect(responseJSON.businessEntityID).to.be.an('number');
	pm.expect(responseJSON.sourceSystemID).to.be.an('number');
	pm.expect(responseJSON.sourceSystemName).to.be.an('string');
	pm.expect(responseJSON.organizationID).to.be.an('number');
	pm.expect(responseJSON.departmentName).to.be.an('string');
	pm.expect(responseJSON.recCreatedBy).to.be.an('string');
});


//Data Stucture Test1: The generated ID should be greater than 0
pm.test("Verify the response JSON body contains the newly created the ID", function () {
    pm.expect(pm.response.json().model.organizationID).to.be.greaterThan(0);
	pm.environment.set('new_RoleID', pm.response.json().model.roleId);
})

//Data value Test1: Is the request body coming back with response body with ID
pm.test("Verify the response body resource object match with the request object value, New ID:", function(){
    var newrolename = pm.environment.get('new_RoleName');
    
    var responseJSON = pm.response.json().model;
    pm.expect( responseJSON.roleName).to.eql(newrolename);
    pm.expect(responseJSON.sourceSystemID).to.eql(Number(pm.environment.get('hc_sourceSystemID')));
    pm.expect( responseJSON.recCreatedBy).to.eql('APITester');
});

pm.test("Run manually  - SQL DB", function () {
    console.log(SQL + pm.response.json().model.organizationID + "\n\r" + SQL1 + pm.response.json().model.organizationID);
})



/**************************************************************************************************
** POST Method - Specific for endpoint - Negative Testing
***************************************************************************************************/

/*----------------------------------------------------------------------------------------
-- Error Pattern 1
/*--------------------------------------------------------------------------------------*/

var expectedErrMsg = "Error converting value {null} to type 'System.Int32'. Path 'sourceSystemID', line 3, position 26.";
var responseKeys = ['errors', 'title', 'status', 'traceId'];

//Data Stucture Test1: The columns should be exist, is all the column exists as per the model 
pm.test("Verify the response JSON body contains the expected error model", function () {
     var responseParentJSON = pm.response.json();
     pm.expect(responseParentJSON).to.have.all.keys(responseKeys);
});

pm.test("Verify the reponse message has title: One or more validation errors occurred.", function(){
    pm.expect(pm.response.json().title).to.eql('One or more validation errors occurred.');
});

pm.test("Verify the reponse message has status: 400", function(){
    pm.expect(pm.response.json().status).to.eql(400);
});

pm.test("Verify the reponse message has traceId length > 0", function(){
    pm.expect(pm.response.json().traceId.length).to.be.greaterThan(0);
});

pm.test("Verify the reponse message should have the expected error message", function(){
    pm.expect(pm.response.json().errors.sourceSystemID[0]).to.eql(expectedErrMsg);
	
	//Child object check
	pm.expect(pm.response.json().errors["Roles[0].Category"][0]).to.eql(expectedErrMsg);
});



/*----------------------------------------------------------------------------------------
-- Error Pattern 2
/*--------------------------------------------------------------------------------------*/
var expectedErrTitle = "Update Department threw error";
var expectedErrMsg = "Violation of PRIMARY KEY constraint 'PK_Department'. Cannot insert duplicate key in object 'Organization.Department'. The duplicate key value is (1030, New Test API7).";
var responseKeys = ['message', 'hasError', 'errorMessage', 'statusCode', 'errorLogID', 'model', 'modelList'];

//Data Stucture Test1: The columns should be exist, is all the column exists as per the model 
pm.test("Verify the response JSON body contains the expected error model", function () {
     var responseParentJSON = pm.response.json();
     pm.expect(responseParentJSON).to.have.all.keys(responseKeys);
});

pm.test("Verify the reponse message has title: One or more validation errors occurred.", function(){
    pm.expect(pm.response.json().message).to.eql(expectedErrTitle);
});

pm.test("Verify the reponse message has hasError:true", function(){
    pm.expect(pm.response.json().hasError).to.eql(true);
});

pm.test("Verify the reponse message has expected error message in errorMessage", function(){
    pm.expect(pm.response.json().errorMessage).to.eql(expectedErrMsg);
});

pm.test("Verify the reponse message has statusCode: 500", function(){
    pm.expect(pm.response.json().statusCode).to.eql(500);
});

pm.test("Verify the reponse message should have  errorLogID with ID", function(){
    pm.expect(pm.response.json().errorLogID).to.be.greaterThan(0);
});




/*----------------------------------------------------------------------------------------
-- Error Pattern 2 - Already existt data test
/*--------------------------------------------------------------------------------------*/


var expectedErrTitle = "Department already exists";
var expectedErrorMessage = "Department already exists";


//Data Stucture Test1: The columns should be exist, is all the column exists as per the model 
pm.test("Verify the response JSON body contains the expected error model", function () {
     var responseParentJSON = pm.response.json();
     pm.expect(responseParentJSON).to.have.all.keys('message', 'hasError', 'errorMessage', 'statusCode', 'errorLogID', 'model', 'modelList');
});

pm.test("Verify the reponse message has message with the expected error title", function(){
    pm.expect(pm.response.json().message).to.eql(expectedErrTitle);
});

pm.test("Verify the reponse message has hasError to be true", function(){
    pm.expect(pm.response.json().hasError).to.eql(true);
});

pm.test("Verify the reponse message has errorMessage with the expected error message", function(){
    pm.expect(pm.response.json().errorMessage).to.eql(expectedErrorMessage);
});

pm.test("Verify the reponse message has statusCode: 202", function(){
    pm.expect(pm.response.json().statusCode).to.eql(202);
});

pm.test("Verify the reponse message should have  errorLogID with ID", function(){
    pm.expect(pm.response.json().errorLogID).to.be.greaterThan(0);
});




```
