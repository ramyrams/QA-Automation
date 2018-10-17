# test API with Katalon Studio

# API For Practice
https://reqres.in/
http://jsonpath.com/
https://prnt.sc/


# JSON for Import
https://petstore.swagger.io/v2/swagger.json
https://petstore.swagger.io/
https://petstore.swagger.io/


https://help.testlodge.com/hc/en-us/articles/226734968-API-Test-cases

https://docs.katalon.com/katalon-studio/videos/create_environment_profile.html

Katalon Studio 18 - How to test API with Katalon Studio
https://www.youtube.com/watch?v=Evikp4eQSGs


https://www.youtube.com/watch?v=xBjNhauVDio&list=PLhW3qG5bs-L_D4ZePNNjvmIULuu6mBHbu


https://www.youtube.com/watch?v=0nyUqIrQLBY

https://www.youtube.com/watch?v=aqrxDxumKZQ


# Sample
https://github.com/katalon-studio-samples/jira-api-tests


# Code Snippet
https://forum.katalon.com/discussion/5259/how-to-set-http-header-with-variable

```groovy
TestObjectProperty header4 = new TestObjectProperty("Cookie", ConditionType.EQUALS, "anyCookieHere")

v


println object.get("applications").get(0).get("id")



def responseDataGenres = WS.sendRequest(findTestObject('Object Repository/APIs/_(api)_genres'))
responseText = responseDataGenres.getResponseText()
def parsed = new JsonSlurper().parseText(responseText)
assert parsed.franchises[0].genres*.find { 'comedy' in it.value }.key.size() == 1


import groovy.json.JsonOutput
import groovy.json.JsonSlurper

def text = '''
{"applications":[
{"name":"test123","id":"c1257c5","description":"test","type":"generic","version":"0.1"},
{"name":"Asset_1","id":"a9e0bce","description":"sfsdgdg","type":"generic","version":"0.1"},
{"name":"Asset_2","id":"a9e0cd2","description":"sffgdgf","type":"generic","version":"0.1"}
]
}
'''
println JsonOutput.prettyPrint(text)

def jsonSlurper = new JsonSlurper()
def object = jsonSlurper.parseText(text)
assert object.applications[0].id == 'c1257c5'
assert object.applications[1].id == 'a9e0bce'
assert object.applications[2].id == 'a9e0cd2'


import groovy.json.JsonSlurper

def json = new JsonSlurper().parseText('{"applications":[{"name":"test123","id":"c1257c5","description":"test","type":"generic","version":"0.1"},{"name":"Asset_1","id":"a9e0bce","description":"sfsdgdg","type":"generic","version":"0.1"},{"name":"Asset_2","id":"a9e0cd2","description":"sffgdgf","type":"generic","version":"0.1"}]}')

println(json.applications[1].id)





com.kms.katalon.core.testobject.RequestObject ro = findTestObject('Object Repository/yourRestDefinition')
ro.setRestUrl("whatever you want")

basicaly you can build your own object from scratch ... just check api for RequestObject



response = WS.sendRequest(reqObj)
println response.getHeaderFields()['Set-Cookie']



 def slurper = new groovy.json.JsonSlurper()
 def result = slurper.parseText('{"person":{"name":"Guillaume","age":33,"pets":["dog","cat"]}}')

 assert result.person.name == "Guillaume"
 assert result.person.age == 33
 assert result.person.pets.size() == 2
 assert result.person.pets[0] == "dog"
 assert result.person.pets[1] == "cat"
 
 
 println object.get("applications").get(0).get("id")
 
 
 See the code below:
def data = findTestData("Policy/Member")

def NovaWrapperWebApi = MapWebApiBodyVariables(index)
def response = WS.sendRequest(NovaWrapperWebApi)
def memberIdNumber = findTestData('Policy/Member').getValue('IDNumber', index);
GlobalVariable.result = 'Row number '+index+' '+response.getResponseText()'
System.out.println(GlobalVariable.result)



Curly braces inside URI request
https://forum.katalon.com/discussion/9433/curly-braces-inside-uri-request


Dynamic base URL in Test Object (take it from environment profile)


def responseData = WS.sendRequest(findTestObject('OR/WsObject',[('acctNum'): accountNumber]))



import org.apache.commons.lang.RandomStringUtils

String charset = (('A'..'Z') + ('0'..'9')).join()
Integer length = 9
def randomString = RandomStringUtils.random(length, charset.toCharArray())

println randomString

{
  "key": “${keyValue}”,
  “userName": “dave”,
  “country”: “GB”
}

response = WS.sendRequest(findTestObject('pathInObjectRepository/requestObject',[('keyValue'): randomString]))


r if you want a random int, the below line would give you a int between 999999 and 1000000.

int randomInt = Math.abs(new Random().nextInt()) % 999999 + 1000000




@Keyword
def randomString(int stringLength) {
String charset = (('A'..'Z') + ('0'..'9')).join()
Integer length = stringLength
def randomString = RandomStringUtils.random(length, charset.toCharArray())
return randomString
}





@Keyword
def PATCH(String URL, String Identifier, String JSONBody) {

OkHttpClient client = new OkHttpClient()

MediaType mediaType = MediaType.parse("application/json")

String url = URL + '/' + Identifier

String requestBody = JSONBody

RequestBody body = RequestBody.create(mediaType, requestBody)

Request request = new Request.Builder()
.url(url)
.patch(body)
.addHeader("content-type", "application/json")
.addHeader("cache-control", "no-cache")
.build();

Response response = client.newCall(request).execute()

String responseBodyString = response.body().string()

//Create a new jsonSlurper object to manipulate the response from the API
JsonSlurper jsonSlurper = new JsonSlurper()

//Create a new object which will represent the response data from the API
def responseObject = jsonSlurper.parseText(responseBodyString)

return responseObject

}
}


import org.openqa.selenium.Cookie

Cookie myCookie = new Cookie("TokenNameYouNeedSet", tokenFromFirstRequest)
response = WS.sendRequest(findTestObject(requestObject.getObjectId(),[('COOKIE'): myCookie]))



@BeforeTestCase
def infoBeforeTestCase(TestCaseContext testCaseContext) {
       println testCaseContext.getTestCaseId()
}



WebUI.comment("${this.getTestCaseId()}")




try{
	response = WS.sendRequest(findTestObject('Object Repository/__Sandbox/rObject1'))
} catch (Exception ce){
	println '**********************************'
	println ce
	println '**********************************'
}


response = WS.sendRequest(findTestObject('requestObject',[('variable'): value]))


def token = response.getHeaderFields().token
Cookie myCookie = new Cookie("token", token)
newResponse = WS.sendRequest(findTestObject(ro.getObjectId(),[('COOKIE'): myCookie]))





import groovy.json.JsonSlurper

def slurper = new groovy.json.JsonSlurper()
def jsonDefText = '{ "name": "John", "surname": "Doe", "options" :[{"setOption1":"valOfSetOption1_1", "setOption2":"valOfSetOption2_1","setOption3":"valOfSetOption3_1"},{"setOption1":"valOfSetOption1_2", "setOption2":"valOfSetOption2_2"}]}'  

def jsonVar = slurper.parseText(jsonDefText)

println jsonVar 

assert jsonVar.name == "John"
assert jsonVar.options[0].setOption1 == "valOfSetOption1_1"
assert jsonVar.options[1].setOption2 == "valOfSetOption2_2"
try{
	assert jsonVar.options[1].setOption3 == "valOfSetOption3_2"
} catch (org.codehaus.groovy.runtime.powerassert.PowerAssertionError pae){
	println pae
	println "There is no such element as: jsonVar.options[2].setOption3"
}
jsonVar.options[1].setOption3 = "valOfSetOption3_2"
try{
	assert jsonVar.options[1].setOption3 == "valOfSetOption3_2"
} catch (org.codehaus.groovy.runtime.powerassert.PowerAssertionError pae){
	println pae
	println "There is no such element as: jsonVar.options[2].setOption3"
}



import internal.GlobalVariable
import groovy.json.JsonSlurper

GlobalVariable.yourTokenVar = Token 

def jsonSlurper = new JsonSlurper()
def res = jsonSlurper.parseText(response.getResponseText())
AutToken = res.bearer_token
WS.verifyResponseStatusCode(response, 200)




TestObjectProperty auth = new TestObjectProperty()
auth.setName("Authorization")
auth.setValue("Bearer " + token)
TestObjectProperty content = new TestObjectProperty()
content.setName("Content-Type")
content.setValue("text/xml")
 
def headers = new ArrayList()
headers.add(auth)
headers.add(content)
TestObjectProperty param = new TestObjectProperty()
param.setName("--data")
param.setValue("@/path/to/JUnit_Report.xml")
def params = new ArrayList()
params.add(param)
 
RequestObject reqObj = new RequestObject()
reqObj.setHttpHeaderProperties(headers)
reqObj.setRestRequestMethod('POST')
reqObj.setRestUrl('https://host/api/v1/import/execution/junit?projectKey=XXX')
reqObj.setRestParameters(params)
def getResponse = WSBuiltInKeywords.sendRequest(reqObj)
println(AutToken)
GlobalVariable.AutToken = AutToken



String lines = '{"StudentList": [{"studentId": "1234","name": "abc","state": "S1247","city": "Chennai","zipCode": "686667","createdBy": "test user"},{"studentId": "5679","name": "ced","state": "S1233","city": "Bangalore","zipCode": "560075","createdBy": "test user"},{"studentId": "7899","name": "teud","state": "S1233","city": "Bangalore","zipCode": "560075","createdBy": "test user"}]}'

Map resp = new JsonSlurper().parseText(lines)

ArrayList details = resp.get("StudentList")

for(Map oneStud in details) {
	println oneStud.get("name")
}




https://docs.katalon.com/katalon-studio/tutorials/parse_json_responses.html

def response = WS.sendRequest(findTestObject('REST_CommentDetails')) 
headerFields = response.getHeaderFields()
println headerFields['Set-Cookie']


def a = WS.sendRequest(findTestObject('New_Request_Auth', ['email' : 'sgappfr2@vpmel.fr', 'password' : 'azerty!!']))

request.addProperty('WSS-Password Type', ConditionType.EQUALS, 'PasswordText')


https://mrhaki.blogspot.com/2011/11/grassroots-groovy-reading-json-with.html


'Create a new POST object using builder'
def builder = new RestRequestObjectBuilder()
def reqOrders = builder
	.withRestRequestMethod('POST')
	.withRestUrl('URL')
	.withHttpHeaders([
		new TestObjectProperty('Authorization', ConditionType.EQUALS, parsedUserToken),
		new TestObjectProperty('Content-Type', ConditionType.EQUALS, 'application/json')
	])
	.withRestParameters([
		new TestObjectProperty('service', ConditionType.EQUALS, 'value'),
		new TestObjectProperty('userId', ConditionType.EQUALS, 'value'),
		new TestObjectProperty('currency', ConditionType.EQUALS, 'value'),
		new TestObjectProperty('price', ConditionType.EQUALS, 'value'),
		new TestObjectProperty('amount', ConditionType.EQUALS, 'value'),
		new TestObjectProperty('coins', ConditionType.EQUALS, 'value'),
		new TestObjectProperty('lang', ConditionType.EQUALS, 'EN'),
		new TestObjectProperty('returnPage', ConditionType.EQUALS, 'value')
	])
	.build()
'Send a request'
def respOrders = WSBuiltInKeywords.sendRequest(reqOrders)



RequestObject requestObj = new RequestObject() 
List<TestObjectProperty> headerParameters = new ArrayList() 

//adding the header params
headerParameters.add(new TestObjectProperty('Content-Type', 
ConditionType.EQUALS, 'application/vnd.api+json'))
headerParameters.add(new TestObjectProperty('session_id', ConditionType.EQUALS, 'xxxxx'))

requestObj.setHttpHeaderProperties(headerParameters)
requestObj.setRestUrl("url")
requestObj.setRestRequestMethod("POST")

WS.sendRequest(requestObj) 





import com.kms.katalon.core.testobject.TestObjectProperty

import com.kms.katalon.core.testobject.ConditionType

'Get token'
String token = WebUI.callTestCase(findTestCase('API/Authentication'), [:], FailureHandling.CONTINUE_ON_FAILURE)

'Scope to a project'
RequestObject ScopeToProject = findTestObject('API/ScopeToProject')

'Create new ArrayList'
ArrayList<TestObjectProperty> HTTPHeader = new ArrayList<TestObjectProperty>()

'Send token in HTTP header'
HTTPHeader.add(new TestObjectProperty('X-Auth-Token', ConditionType.EQUALS, token))

'Set that token'
ScopeToProject.setHttpHeaderProperties(HTTPHeader)




https://github.com/alexdeleon/groovy-json-schema




//How to verify Array in Api Resful

def jsonSlurper = new JsonSlurper()
def res = jsonSlurper.parseText(response.getResponseText())
println(res.errors.message[0])



import groovy.json.JsonSlurper 

class Example {
   static void main(String[] args) {
      def jsonSlurper = new JsonSlurper()
      def object = jsonSlurper.parseText('{ "name": "John", "ID" : "1"}') 
		
      println(object.name);
      println(object.ID);
   } 
}


//How to get size of element in API Response

def results = new groovy.json.JsonSlurper().parseText( response.getResponseBodyContent() )
println results.size()

'Get response text'

response = WS.sendRequest(ScopeToProject)

'Verify if scope to project was successfull'
WS.verifyElementPropertyValue(response, 'data.currentProject', 'ab8e52e92deb459596e3911f9f09934c')



import groovy.json.JsonSlurper
responseData = WS.sendRequest(findTestObject("POST RESTFUL"));
responseText = responseData.getResponseText();
def json = new JsonSlurper().parseText(responseText)
println json.results.size();





import com.kms.katalon.core.testobject.RequestObject
import com.kms.katalon.core.webservice.keyword.WSBuiltInKeywords as WS

import groovy.json.JsonSlurper

// create a new instance of JsonSlurper
JsonSlurper parser = new JsonSlurper()

// build first RequestObject
RequestObject ro = new RequestObject("x")
ro.setRestRequestMethod("GET")
ro.setRestUrl("https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/test_data_file.json")

// send request and get response text
def resp = WS.sendRequest(ro).getResponseText()
// parse response text as JSON
def parsedResp = parser.parseText(resp)

// get parameter you need from JSON response - parse it using dot notation
def param = parsedResp.username[0]

// build a second request and pass a param from 1st request
RequestObject ro2 = new RequestObject("y")
ro2.setHttpBody(param)
ro2.setRestUrl("www.yoururl.com")

WS.sendRequest(ro2)





```
