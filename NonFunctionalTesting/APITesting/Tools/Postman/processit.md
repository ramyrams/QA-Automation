
Sessions in Postman - https://drive.google.com/file/d/1s8Emp-XowrOGZUYoBm2xIWOQP7JBLOvh/view
Working with Sessions in Postman - https://www.youtube.com/watch?v=JcSZtVwH69w
Sessions - https://learning.getpostman.com/docs/postman/environments_and_globals/sessions



Postman Examples
https://documenter.getpostman.com/view/220187/postman-bdd-examples/6Z3uY71?version=latest#intro


### Working with a Response Data
//JSON Response
var response = pm.response.json();
//Text Response
var response = pm.response.text()
//XML Response
var jsonObject = xml2Json(responseBody);
//Choosing First Response from array of JSON
var userdata= pm.response.json()[0];



    var jsonData = pm.response.json();
    pm.expect(response.id).to.be.a(‘number’);
    pm.expect(response.name).to.be.a(‘string’);
    pm.expect(response.isDeleted).to.be.a(‘boolean’);
}




### Data variables in requests
https://blog.getpostman.com/wp-content/uploads/2016/06/Screen-Shot-2016-06-25-at-14.47.47-1024x347.png


### Data variables in pre-request and test scripts
https://blog.getpostman.com/wp-content/uploads/2016/06/Screen-Shot-2016-06-25-at-14.48.35-1024x413.png

### Workflows
The third-level folders are for more complicated tests that span multiple API calls. For example, your API might have a checkout flow that involves separate calls to create an order from a shopping cart, enter the shipping address, select the shipment method, and submit the payment information. In this case, you’d create a “workflow” folder named something like “Checkout” that contains the three requests.

https://blog.getpostman.com/wp-content/uploads/2017/07/nested-folders-1024x756.png


Using CSV and JSON data files in the Postman Collection Runner - https://blog.getpostman.com/2014/10/28/using-csv-and-json-files-in-the-postman-collection-runner/
In-App Postman Bootcamp Lessons - https://blog.getpostman.com/2019/01/11/in-app-postman-lessons/


Top Tutorials To Learn POSTMAN For REST API Testing
https://medium.com/quick-code/top-tutorials-to-learn-postman-for-rest-api-testing-3bdf9788e0ba

Capture Network Traffic by setting up Proxies
Learn how to do multi-part File Uploads
Perform data driven testing (create 1000 students with a click of a button)
Learn how to send SOAP Requests using Postman
Integrate Postman with Newman & Jenkins
Different types of Authentication (BASIC,OAuth 1.0,OAuth 2.0)
Scripting in Postman


https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/surveymonkey_script.png
https://blog.getpostman.com/2018/06/05/airtable-to-surveymonkey/


Looping through a data file in the Postman Collection Runner
https://blog.getpostman.com/2018/04/11/looping-through-a-data-file-in-the-postman-collection-runner/


Turn your Postman Collection into models with Quicktype.io
https://blog.getpostman.com/2018/04/05/turn-your-postman-collection-into-models-with-quicktype-io/

How to make money using Postman: chaining requests
https://blog.getpostman.com/2018/03/19/how-to-make-money-using-postman-chaining-requests/

Branching and looping
https://blog.getpostman.com/wp-content/uploads/2018/03/Screen-Shot-2018-03-06-at-4.10.47-PM-1024x419.png

10 tips for working with Postman variables
https://blog.getpostman.com/2017/12/29/10-tips-for-working-with-postman-variables/

Postman makes SOAP requests too
https://blog.getpostman.com/2017/11/18/postman-makes-soap-requests-too/

Using a Postman monitor to water my plants ?
https://blog.getpostman.com/2017/11/08/using-a-postman-monitor-to-water-my-plants/


Postman makes authorization stronger and easier
https://blog.getpostman.com/2017/11/04/postman-makes-authorization-stronger-and-easier/

Writing tests in Postman
https://blog.getpostman.com/2017/10/25/writing-tests-in-postman/

API testing tips from a Postman professional
https://blog.getpostman.com/2017/07/28/api-testing-tips-from-a-postman-professional/

Client proxy settings in Postman
https://blog.getpostman.com/2017/09/29/client-proxy-settings-in-postman/

Send asynchronous requests with Postman’s PM API
https://blog.getpostman.com/2017/10/03/send-asynchronous-requests-with-postmans-pm-api/

Write to your local file system using a Postman Collection
https://blog.getpostman.com/2017/09/01/write-to-your-local-file-system-using-a-postman-collection/


Check for broken links on your website using a Postman Collection
https://blog.getpostman.com/2017/06/23/check-for-broken-links-on-your-website-using-a-postman-collection/


Version Control in Postman
https://blog.getpostman.com/2017/06/20/version-control-in-postman/

Descriptions for request attributes in Postman
https://blog.getpostman.com/2017/06/03/descriptions-for-request-attributes-in-postman/

Mock responses in Postman by using Examples
https://blog.getpostman.com/2017/05/17/mock-responses-in-postman-by-using-examples/

Autocomplete and Tooltips for Variables are Here
https://blog.getpostman.com/2017/03/07/autocomplete-and-tooltips-for-variables-are-here/


Introducing the New Data Editor
https://blog.getpostman.com/2017/02/28/introducing-the-new-data-editor/


Postman’s New Collection Runner
https://blog.getpostman.com/2016/11/22/postmans-new-collection-runner/

Postman Console
https://blog.getpostman.com/2016/08/26/the-postman-console/

Conditional Workflows in Postman
https://blog.getpostman.com/2016/03/23/conditional-workflows-in-postman/

Introducing Postman Collection Format Schema
https://blog.getpostman.com/2015/07/02/introducing-postman-collection-format-schema/

Inspecting Postman Requests
https://blog.getpostman.com/2015/06/13/debugging-postman-requests/

Setting up multi region API tests in Postman
https://blog.getpostman.com/2017/08/17/setting-up-multi-region-api-tests-in-postman/


How to write automated tests for APIs with Postman

https://blog.getpostman.com/2014/03/07/writing-automated-tests-for-apis-using-postman/
https://blog.getpostman.com/2014/04/17/how-to-write-automated-tests-for-apis-with-postman-part-2/
https://blog.getpostman.com/2014/05/09/writing-automated-tests-with-postman-part-3/


Using variables inside Postman and Collection Runner
https://blog.getpostman.com/2014/02/20/using-variables-inside-postman-and-collection-runner/

Troubleshooting Self-signed SSL Certificate Issues and More in Postman
https://blog.getpostman.com/2019/07/17/self-signed-ssl-certificate-troubleshooting/

Extracting data from responses and chaining requests
https://blog.getpostman.com/2014/01/27/extracting-data-from-responses-and-chaining-requests/

### Capture the request you want to test
https://res.cloudinary.com/practicaldev/image/fetch/s--yB_HgpdW--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/lzjx9hsbyjkomj30g2my.PNG



https://github.com/DevMountain/endpoint-testing-afternoon




https://miro.medium.com/max/2128/1*486RglVX9kPEfrSv2UOeug.png


The workflow:
* First makes the API call to GET the list of approved food for Cooper from the database.
* Then it creates an entry for each day, 3 times a day, 7 days a week
* All 3 meals in a single day have to be unique.
* If the API call fails, poor Cooper goes hungry 😟


https://miro.medium.com/max/658/1*Alhn3IUJDYwqfc4haVlteg.png

Cooper's Meal Plan - Postman
https://documenter.getpostman.com/view/583/coopers-meal-plan/4u2?version=latest

Conditional Workflows in Postman - https://blog.getpostman.com/2016/03/23/conditional-workflows-in-postman/



### Workflows
switch(pm.environment.get("PROFILE_set1")) {
    case 1:
        postman.setNextRequest("PROF_02 - Verify  the profile details");
        break;
    case 2:
        postman.setNextRequest("PROF_04 - Verify  update profile without firstname");
        break;
    case 3:
        postman.setNextRequest("PROF_05 - Verify update profile only with firstname");
        break;
    case 4:
        postman.setNextRequest("PROF_06 - Verify update profile only with phone");
        break;
    case 5:
        postman.setNextRequest("PROF_07 - Verify update profile only with last name");
        break;
    case 6:
        postman.setNextRequest("[Pre-condition] Logout - Profile");
        break;
}

### How to sort array in postman?

var tests = eval(pm.environment.get("tests")),
    body1 = {
        "arr": [
            1,
            2,
            3
        ]
    },
    body2 = {
        "arr": [
            2,
            1,
            3
        ]
    };


function checkArr(body1, body2) {
  let arr1 = body1.arr.sort(), //javascript has this in-built for arrays
    arr2 = body2.arr.sort();

  pm.expect(arr1).to.eql(arr2);
}




# How to send a request inside Tests?

pm.test("Child category is also deleted", (done) => {
    pm.sendRequest({
        url:  "url", 
        method: 'GET',
        header: {
            'content-type': 'application/json',
            'Authorization': "Bearer " + pm.environment.get("accessToken"),
            'Accept': "*/*"
        },
    }, (err, res) => {
        pm.expect(res.code).to.equal(404);
        done();
    });
});


pm.test("Order Details are Present", () => {
    let jsonData = pm.response.json()
    pm.expect(jsonData.items).to.be.an("array");
    pm.expect(jsonData.items[0]).to.have.keys('oID','oInvoiceNo','OrderBlocks').and.be.an("object");
    pm.expect(jsonData.items[0].OrderBlocks).to.be.an("array");
    pm.expect(jsonData.items[0].OrderBlocks[0]).to.have.keys('olLine','olProductCode').and.be.an("object");
});

