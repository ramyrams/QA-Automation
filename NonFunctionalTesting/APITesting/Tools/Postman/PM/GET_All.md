var messageTitle = 'GetSourceSystemLkp Successfull';
var responseBodyKeys = ['message', 'hasError', 'errorMessage', 'statusCode', 'errorLogID', 'model', 'modelList'];
var modelKeys = ['sourceSystemID', 'sourceSystemName', 'recCreatedBy', 'recUpdatedBy']
var expectedListKeysCount = 6;
var noOfExpectedRowsCount = 6;
var listofCategory = ['Active Directory', 'Corporate', 'PMC', null]

/*----------------------------------------------------
Created By: <Developer Name>
Created on: <Created on Date>
----------------------------------------------------*/


/****************************************************************************************
** GET Method - Common for any API
*****************************************************************************************/

/*----------------------------------------------------
Common for any API -> Basic validation
----------------------------------------------------*/

//Common Test:1->Basic Test: Is URL up and running
pm.test("Verify  endpoint is up and running", function(){
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
	console.log(pm.response.json().modelList.length);
	// this assertion also checks if a body  exists, so the above check is not needed
	pm.response.to.be.withBody;
	
	 // assert that the response has a valid JSON body
	pm.response.to.be.json; 

	pm.expect(pm.response.json().modelList.length).to.be.above(0);
	
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
** GET Method - Common for any end point -> Common verification for all the API in a given project
***************************************************************************************************/

/*---------------------------------------------------------------------------------
Common for any end point -> Common verification for all the API in a given project
-----------------------------------------------------------------------------------*/

//Data Stucture Test1: The given keys should be exist in the main model of the response body 
pm.test("Verify the response JSON body contains expected data model keys", function () {
     var responseParentJSON = pm.response.json();
     pm.expect(responseParentJSON).to.have.all.keys(responseBodyKeys);
});


/*------------------------------------------------------------------------------
Response body key/value validation 
--------------------------------------------------------------------------------*/
pm.test("Verify the reponse message has expected message title", function(){
    pm.expect(pm.response.json().message).to.eql(messageTitle);
});

pm.test("Verify the reponse message hasError is false", function(){
    pm.expect(pm.response.json().hasError).to.eql(false);
});

pm.test("Verify the reponse message errorMessage is null", function(){
    pm.expect(pm.response.json().errorMessage).to.eql(null);
});

pm.test("Verify the reponse message statusCode is 200", function(){
    pm.expect(pm.response.json().statusCode).to.eql(200);
});

pm.test("Verify the reponse message errorLogID is 0", function(){
    pm.expect(pm.response.json().errorLogID).to.eql(0);
});

pm.test("Verify the reponse message model is null", function(){
    pm.expect(pm.response.json().model).to.eql(null);
});


//Data Stucture Test1: Is the modelList has any data
pm.test("Verify the response JSON body contains modelList with rows more than 0", function () {
    pm.expect(pm.response.json().modelList.length).to.be.above(0);
})



/**************************************************************************************************
** GET Method - Specific for endpoint
***************************************************************************************************/
//Data Stucture Test1: The given keys should be exist in the model list of the response body , is all the column exists as per the schema 
pm.test("Verify the response JSON body contains expected data column as per the schema", function () {
    var responseListJSON = pm.response.json().modelList;
    pm.expect(responseListJSON[0]).to.have.all.keys(modelKeys);
});

//It should fail if any unexpected keys in the payload
pm.test("Verify the response JSON body contains expected key count in the model list", function(){
    var responseJSON = pm.response.json().modelList;
    pm.expect(Object.keys(responseJSON[0])).to.have.lengthOf(expectedListKeysCount);
});

/*----------------------------------------------------
Data type validation of all the model list rows
----------------------------------------------------*/
pm.test("Verify the reponse data type", function(){

    var responseJSON = pm.response.json().modelList;
	
    for(i=0; i< responseJSON.length;i++){
        /*console.log(responseJSON[i].organizationTypeID);*/
            
        pm.expect(responseJSON[i].departmentID).to.be.an('number');

		pm.expect(responseJSON[i].sourceSystemName).to.be.an('string');

		pm.expect(responseJSON[i].Descr).to.satisfy(function(s){
              return s === null || typeof s == 'string' || s === undefined || s === "" || s.length === 0
        });
		
	}
});


/*----------------------------------------------------
Data type validation
----------------------------------------------------*/
//Data value Test1: Make sure the respond body cotains same number of rows in DB
pm.test("Verify the respond body count match with expected row count", function(){
    var responseJSON = pm.response.json().modelList;
    pm.expect(responseJSON.length).to.eql(noOfExpectedRowsCount);
});



/*----------------------------------------------------
Data value validation
----------------------------------------------------*/

//Data value Test1: Print number of rows returned
pm.test("Verify the value of each column for the departmentID ID=2", function(){
    var responseJSON = pm.response.json().modelList;

	var extractedJSON = _.find(responseJSON, function(o) { return o.departmentID == 1; });


    pm.expect(extractedJSON.sourceSystemID).to.eql(2);
    pm.expect(extractedJSON.sourceSystemName).to.eql('Paylocity 45777');

});



//Data length Test2: the category data value should match the lookup
pm.test("Verify the category value is matches within the lookup", function(){
    var responseJSON = pm.response.json().modelList;
    for(i=0; i< responseJSON.length;i++){
        console.log(responseJSON[i].category);
        pm.expect(responseJSON[i].category).to.be.oneOf(['Active Directory', 'Corporate', 'PMC']);
    }
});


----------------------------------------------



/*----------------------------------------------------
Data length validation
----------------------------------------------------*/
//Data length Test1: the data matches the minium length of data for all the rows
pm.test("Verify the data matches the minium length of data", function(){

    var responseJSON = pm.response.json();
    for(i=0; i< pm.response.json().length;i++){

        pm.expect(responseJSON[i].category.length).to.be.greaterThan(2);
    }
});


//Data Stucture Test1: The columns should be exist, is all the column exists as per the model 
pm.test("Testing...", function () {

    console.log(pm.info.requestName);
});

