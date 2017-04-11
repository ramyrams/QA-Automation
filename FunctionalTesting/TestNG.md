# What are the advantages of TestNG?

* TestNG provides parallel execution of test methods
* It allows to define dependency of one test method over other method
* It allows to assign priority to test methods
* * It allows grouping of test methods into test groups
* It has support for parameterizing test cases using @Parameters annotation
* It allows data driven testing using @DataProvider annotation
* It has different assertions that helps in checking the expected and actual results
* Detailed (HTML) reports


# Annotations in TestNG
* @BeforeTest
* @AfterTest
* @BeforeClass
* @AfterClass
* @BeforeMethod
* @AfterMethod
* @BeforeSuite
* @AfterSuite
* @BeforeGroups
* @AfterGroups
* @Test

# What is the importance of testng.xml file?
* testng.xml file allows to include or exclude the execution of test methods and test groups
* It allows to pass parameters to the test cases
* Allows to add group dependencies
* Allows to add priorities to the test cases
* Allows to configure parallel execution of test cases
* Allows to parameterize the test cases


 ```java
// TestNG Interview Questions
public class ParameterizedTest {
	@Test
	@Parameters("browser")
	public void parameterizedTest(String browser){
		if(browser.equals("firefox")){
			System.out.println("Open Firefox Driver");
		}else if(browser.equals("chrome")){
			System.out.println("Open Chrome Driver");
		}
	}	
}
```

# testng.xml file

 ```xml
<parameter name="browser" value="firefox"/>
 ```
