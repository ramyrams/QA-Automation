# WebUI Documents
https://docs.katalon.com/katalon-studio/docs/webui-accept-alert.html


# Good Samples
https://github.com/katalon-studio-samples/katalon-web-automation/tree/master/Scripts

https://github.com/katalon-studio-samples/katalon-regression-tests/tree/master/Scripts

Excel Data:
https://github.com/nhannguyenth/katalon-excel-keyword/blob/master/ExcelKeywords/Scripts/SampleTestCase/VerifyExcelGetData/Script1552985050482.groovy
https://github.com/nhannguyenth/katalon-excel-keyword/tree/master/ExcelKeywords/Scripts/SampleTestCase/VerifyExcelKeyWords
https://github.com/nhannguyenth/katalon-excel-keyword/tree/master/ExcelKeywords/Scripts



https://github.com/nhannguyenth/katalon-vuejs-modal-keyword



WebUI.verifyCheckpoint(findCheckpoint('Checkpoints/Checkpoint1'), false)



'Input username and password on authentication dialog.'
WebUI.authenticate('http://the-internet.herokuapp.com/basic_auth', 'admin', 'admin', 12)

'Back to previous page after navigating to \'Make Appointment\' page'
WebUI.back()

'Forward to \'Make Appointment\' page'
WebUI.forward()

'Refresh the current web page'
WebUI.refresh()

'Get current page\'s height'
height = WebUI.getPageHeight()


'Get current page\'s width'
width = WebUI.getPageWidth()

'Get current page\'s URL'
url = WebUI.getUrl()


'Get current viewport height'
viewport_height = WebUI.getViewportHeight()

'Get viewport\'s left position'
left_viewport = WebUI.getViewportLeftPosition()

'Get viewport\'s top position'
top_viewport = WebUI.getViewportTopPosition()


'Get current viewport width'
viewport_width = WebUI.getViewportWidth()

'Set viewport size 703x347'
WebUI.setViewPortSize(703, 347)

'Switch to Documentation window'
WebUI.switchToWindowIndex(1)

'Scroll to position (50, 60)'
WebUI.scrollToPosition(50, 60)

'Switch to Documentation window'
WebUI.switchToWindowTitle('Documentation')

'Get index of Documentation window'
index = WebUI.getWindowIndex()


'Switch to Documentation window'
WebUI.switchToWindowIndex(1)

'Get title of Documentation window'
title = WebUI.getWindowTitle()



'Close Documentation window'
WebUI.closeWindowIndex(1)

'Close Documentation window'
WebUI.closeWindowTitle('Documentation')

'Close Documentation window'
WebUI.closeWindowUrl('https://docs.katalon.com')

'Delete all cookies after browser is opened'
WebUI.deleteAllCookies()


'Use Javascript to make an alert'
WebUI.executeJavaScript("alert('This is an alert')", null)

'Return WebElement based on its id:
WebElement element = WebUI.executeJavaScript("return document.getElementById('someId');", null)


'Interact with returned WebElement
WebElement element = WebUiCommonHelper.findWebElement(findTestObject('your/object'),30)
WebUI.executeJavaScript("arguments[0].style.border='3px solid blue'", Arrays.asList(element))


'Click on returned WebElement:
WebElement element = WebUiCommonHelper.findWebElement(findTestObject('your/object'),30)
WebUI.executeJavaScript("arguments[0].click()", Arrays.asList(element))


'Storing the URL in a variable'
def htmlDir = RunConfiguration.getProjectDir() + GlobalVariable.MultiSelection_dropDown_Html_Path


# Calling Test cases
WebUI.callTestCase(findTestCase('Web UI Tests/Advance Tests/Pages/Master Page/Open the Create Issue form'), [:], FailureHandling.STOP_ON_FAILURE)
WebUI.callTestCase(findTestCase('Web UI Tests/Start Web UI Testing'), [:], FailureHandling.STOP_ON_FAILURE)

WebUI.callTestCase(findTestCase('Web UI Tests/Advance Tests/Pages/Login Page/Login with username and encrypted password'), 
    [('username') : GlobalVariable.username, ('encryptedPassword') : GlobalVariable.encrypted_password], FailureHandling.STOP_ON_FAILURE)

def fixed_summary = WebUI.callTestCase(findTestCase('Web UI Tests/Advance Tests/Pages/Create Issue Page/Create a new issue with these information'), 
    [('project') : project, ('issueType') : issueType, ('priority') : priority, ('description') : description, ('summary') : summary], 
    FailureHandling.STOP_ON_FAILURE)

WebUI.callTestCase(findTestCase('Web UI Tests/Advance Tests/Pages/Issue Page/The opening issue displays correct information'), 
    [('issue_summary') : fixed_summary, ('issue_type') : issueType], FailureHandling.STOP_ON_FAILURE)
	
	
WebUI.callTestCase(findTestCase('Web UI Tests/Simple Tests/Login Test/Test data hardcoding examples/Login with username and password specified in the test steps'), 
    [:], FailureHandling.STOP_ON_FAILURE)
	

# DropDown_Handling
'Selecting the option with Value'
WebUI.selectOptionByValue(findTestObject('DropDown/comboBox_Role'), '5', false)

'DeSelecting the option with Value'
WebUI.deselectOptionByValue(findTestObject('DropDown/comboBox_Role'), '5', false)


'Selecting the option with Index'
WebUI.selectOptionByIndex(findTestObject('DropDown/comboBox_Role'), 1)

'DeSelecting the option with Value'
WebUI.deselectOptionByValue(findTestObject('DropDown/comboBox_Role'), '2', false)


'Selecting the option with Label HR'
WebUI.selectOptionByLabel(findTestObject('DropDown/comboBox_Role'), 'HR', false)

'DeSelecting the option with index 1 i.e HR'
WebUI.deselectOptionByIndex(findTestObject('DropDown/comboBox_Role'), 1)

'Select all the Options'
WebUI.selectAllOption(findTestObject('DropDown/comboBox_Role'))

'Deselect all the options'
WebUI.deselectAllOption(findTestObject('DropDown/comboBox_Role'))

'Taking the count of number of Selected Options and Storing it in a variable'
NoOfSelectedOptions = WebUI.getNumberOfSelectedOption(findTestObject('DropDown/comboBox_Role'))

'After Deselect verifying the Number of Selected options with Actual result to Expected'
WebUI.verifyEqual(NoOfSelectedOptions, 0)


'Select All values available in the dropdown by Select All option'
WebUI.selectAllOption(findTestObject('DropDown/comboBox_Role'))

'Capturing the Number of selected Values and storing it in a variable'
SelectedItems = WebUI.getNumberOfTotalOption(findTestObject('DropDown/comboBox_Role'))

println('No of Selected Roles are ' + SelectedItems)

'Verifying the number of Options selected with Expected result'
WebUI.verifyEqual(SelectedItems, 5)



WebUI.setEncryptedText(findTestObject('Page_OrangeHRM/input_Username_txtPassword'), GlobalVariable.password)

'Capturing the Toal Number of  Values in the dropdown and storing it in a variable'
TotalOptions = WebUI.getNumberOfTotalOption(findTestObject('DropDown/comboBox_Role'))

println('No of Roles are :' + TotalOptions)

'Verifying the number of Options in the dropdown with Expected result'
WebUI.verifyEqual(TotalOptions, 5)


'Select the dropdown value by Select option By Label Method'
WebUI.selectOptionByLabel(findTestObject('DropDown/dropdown_Month'), 'Apr', false)

'Verifying the Option is Selected by Label option'
WebUI.verifyOptionSelectedByLabel(findTestObject('DropDown/dropdown_Month'), 'Apr', false, 60)



'Selecting the month from Select By value method'
WebUI.selectOptionByValue(findTestObject('DropDown/dropdown_Month'), '3', false)

'Verifying the Option is Selected by Value option'
WebUI.verifyOptionSelectedByValue(findTestObject('DropDown/dropdown_Month'), '3', false, 60)

'Verifying the option is not Present'
WebUI.verifyOptionNotPresentByLabel(findTestObject('DropDown/dropdown_Month'), 'CEO', false, 50)


'Verifying the option is not present in the dropdown'
WebUI.verifyOptionNotPresentByValue(findTestObject('DropDown/dropdown_Month'), '5', false, 60)


#Accepting the Alert '
WebUI.acceptAlert()

#Dismiss the Alert '
WebUI.dismissAlert()

#Entering a text in alert text box
#Passing the text in the text box in the Alert\r\n'
'Using the current driver Instance'
WebDriver driver = DriverFactory.getWebDriver()
driver.switchTo().alert().sendKeys('Testing')


# Getting a text from alert
WebDriver driver = DriverFactory.getWebDriver()

'Getting the text from the alert and storing it in Variable '
String AlertText = driver.switchTo().alert().getText()

'Verifying the Actual and Expected text from Alert\r\n'
WebUI.verifyEqual(AlertText, 'Please enter your name')


# Upload file by Sendkeys



'Passing the URL of image location'
WebUI.sendKeys(findTestObject('Upload File object/Upload File'), imgDir)

'Capturing the Attribute value and Storing it in a Variable'
FilePath = WebUI.getAttribute(findTestObject('Upload File object/Upload File'), 'value')

'Verifying the Actual path and Expected path of file'
WebUI.verifyMatch(FilePath, 'C:\\fakepath\\Desert.jpg', false)



WebUI.openBrowser('')

WebUI.waitForJQueryLoad(120)

WebUiBuiltInKeywords.click(findTestObject('Landing Page/Button_PopularItem'))

WebUI.openBrowser('https://staging.gramedia.com/')

WebUI.navigateToUrl(' https://tunaiku.com/')

WebUI.maximizeWindow()

 newsBody = WebUI.getText(findTestObject('NewsDetails/newsBody'))

WebUI.comment('new test cases')

WebUI.click(findTestObject('Page_Toko Buku Online Terbesar  Gra/Button_myAccount'))

WebUI.sendKeys(findTestObject('Object Repository/Page_CURA Healthcare Service (1)/input_password', 'blub'))

WebUI.setText(findTestObject('Formulir Pengajuan/Nama Lengkap'), 'Wira Putrawan Pakpahan')

WebUI.selectOptionByValue(findTestObject('Formulir Pengajuan/Kepemilikan Email'), 'Personal', false)

WebUI.selectOptionByLabel(findTestObject('Data Pribadi/Nama Bank'), 'BARCLAYS', false)

WebUI.scrollToElement(findTestObject('Alamat KTP/Label Lengkapi Data'), 0)

WebUI.waitForElementVisible(findTestObject('web ui/Test Objects/Pages/Create Issue Page/elRoot'), GlobalVariable.element_timeout)

WebUI.verifyElementText(findTestObject('web ui/Test Objects/Pages/Create Issue Page/elTitle'), 'Import issues\nCreate issue')

WebUI.waitForElementClickable(findTestObject('web ui/Test Objects/Pages/Create Issue Page/elSummary'), GlobalVariable.element_timeout)
WebUI.waitForElementClickable(findTestObject('web ui/Test Objects/Pages/Master Page/Menu/elCreate'), 0)


WebUI.waitForElementVisible(findTestObject('web ui/Test Objects/Pages/Dashboard Page/elHeader'), GlobalVariable.element_timeout)

WebUI.waitForElementVisible(findTestObject('web ui/Test Objects/Pages/Issue Page/elIssueType'), GlobalVariable.element_timeout)
WebUI.verifyElementText(findTestObject('web ui/Test Objects/Pages/Issue Page/elIssueType'), issue_type)

WebUI.verifyTextPresent('System dashboard', false)

WebUI.delay(2)

WebUI.verifyElementVisible(findTestObject('Landing Page/Verify Landing Page Tunaiku'))
WebUI.verifyElementPresent(findTestObject('CheckoutPage/HasilTitle'), 7)

what is this not_run?
not_run: WebUiBuiltInKeywords.click(findTestObject('CartPage/Button_LanjutkanPmbayaran'))

WebUI.closeBrowser()


println url

WebUI.openBrowser(GlobalVariable.db_connection_string)
println GlobalVariable.db_connection_string




DriverCleanerCollector.getInstance().addDriverCleaner(new com.kms.katalon.core.webui.contribution.WebUiDriverCleaner())
DriverCleanerCollector.getInstance().addDriverCleaner(new com.kms.katalon.core.mobile.contribution.MobileDriverCleaner())
DriverCleanerCollector.getInstance().addDriverCleaner(new com.kms.katalon.core.cucumber.keyword.internal.CucumberDriverCleaner())


RunConfiguration.setExecutionSettingFile('/var/folders/42/25_dz67d0s90tq1kph29hdy00000gp/T/Katalon/Include/features/BDD Cucumber Tests/Web API Tests/Get Issue Tests.feature/20180907_154013/execution.properties')

TestCaseMain.beforeStart()
TestCaseMain.runFeatureFile('Include/features/BDD Cucumber Tests/Web API Tests/Get Issue Tests.feature')




# Declare a custom function and call it

https://github.com/DananDio/KatalonTest/blob/master/Keywords/customKeyword/JavascriptClick.groovy

package customKeyword

public class JavascriptClick {
	
	@Keyword
	def clickUsingJS(TestObject to, int timeout)
	{
	WebDriver driver = DriverFactory.getWebDriver()
	WebElement element = WebUiCommonHelper.findWebElement(to, timeout)
	JavascriptExecutor executor = ((driver) as JavascriptExecutor)
	executor.executeScript('arguments[0].click()', element)
	}
}
	
CustomKeywords.'customKeyword.JavascriptClick.clickUsingJS'(findTestObject('CartPage/Button_Confirm Hapus'), 0)	
	
	
	
while (WebUI.verifyElementPresent(findTestObject('Object Repository/CartPage/Button_Hapus'), 2, FailureHandling.OPTIONAL) == true) {
    CustomKeywords.'customKeyword.JavascriptClick.clickUsingJS'(findTestObject('CartPage/Button_Hapus'), 0)

    CustomKeywords.'customKeyword.JavascriptClick.clickUsingJS'(findTestObject('CartPage/Button_Confirm Hapus'), 0)

    WebUI.delay(2)
}



for (int i = 1; i <= 5; i++) {
    WebUI.waitForPageLoad(3)

    WebUiBuiltInKeywords.click(findTestObject('Landing Page/Button_PopularItem', [('i') : i]))

    WebUI.callTestCase(findTestCase('PDPPage/LoopAddItemCart'), [:], FailureHandling.STOP_ON_FAILURE)

    WebUI.navigateToUrl('https://staging.gramedia.com/')
}




Katalon/Include/config/log.properties
# logging.level.com.kms=TRACE

# logging.level.com.mycompany=DEBUG



# Custom methods for Login and open brower
public class OpenAndMaximizeBrowser {
	
	@Keyword
	public OpenAndMaximizeWindows(String url) {
		
		WebUI.openBrowser(url)
		WebUI.maximizeWindow()
	}
	
	@Keyword
	public loginApp(String username, String password) {
		WebUI.openBrowser("google.ch")
		WebUI.setText(findTestObject("Object Repository/Page_Google/input_q"), username)
		println password
	}

}



class CustomKeywordUtils {
	/**
	 * Refresh browser
	 */
	@Keyword
	def refreshBrowser() {
		KeywordUtil.logInfo("Refreshing")
		WebDriver webDriver = DriverFactory.getWebDriver()
		webDriver.navigate().refresh()
		KeywordUtil.markPassed("Refresh successfully")
	}

	/**
	 * Click element
	 * @param to Katalon test object
	 */
	@Keyword
	def clickElement(TestObject to) {
		try {
			WebElement element = WebUiBuiltInKeywords.findWebElement(to);
			KeywordUtil.logInfo("Clicking element")
			element.click()
			KeywordUtil.markPassed("Element has been clicked")
		} catch (WebElementNotFoundException e) {
			KeywordUtil.markFailed("Element not found")
		} catch (Exception e) {
			KeywordUtil.markFailed("Fail to click on element")
		}
	}

	/**
	 * Click element
	 * @param to Katalon test object
	 */
	@Keyword
	def clickElement(WebElement element) {
		try {
			KeywordUtil.logInfo("Clicking element:"+element.toString())
			element.click()
			KeywordUtil.markPassed("Element has been clicked")
		} catch (WebElementNotFoundException e) {
			KeywordUtil.markFailed("Element not found")
		} catch (Exception e) {
			KeywordUtil.markFailed("Fail to click on element")
		}
	}

	/**
	 * Get all rows of HTML table
	 * @param table Katalon test object represent for HTML table
	 * @param outerTagName outer tag name of TR tag, usually is TBODY
	 * @return All rows inside HTML table
	 */
	@Keyword
	def List<WebElement> getHtmlTableRows(TestObject table, String outerTagName) {
		WebElement mailList = WebUiBuiltInKeywords.findWebElement(table)
		List<WebElement> selectedRows = mailList.findElements(By.xpath("./" + outerTagName + "/tr"))
		return selectedRows
	}

	/**
	 * Get all elements matching xpath
	 * @param xpath - xpath of element to find
	 * @return All elements matching xpath
	 */
	@Keyword
	def List<WebElement> getWebElements(String xpath) {
		WebDriver webDriver = DriverFactory.getWebDriver()
		List<WebElement> selectedRows = webDriver.findElements(By.xpath(xpath))
		KeywordUtil.logInfo("selectedRows:"+selectedRows.size())
		return selectedRows
	}
}



/**
 *
 * @author
 *
 * This is a work-flow test case, which inputs username, password and clicks the login button.
 * The expected result will be on another test case which verifying the login action
 *
 * Given The Jira login page is opening
 * When  I input an account into login form
 * and   I click the Login button
 *
 * @params
 * username: username of the login account
 * encryptedPassword: encrypted password of the login account 
 */
 
 
 
 
 str_mode = WebUI.getText(findTestObject('web ui/Test Objects/Pages/Search Issue Page/Search Navigator/elSearchMode'))

if (str_mode.equalsIgnoreCase('Advanced')) {
	WebUI.click(findTestObject('web ui/Test Objects/Pages/Search Issue Page/Search Navigator/elSearchMode'))
}


# Read test data from the file, 01 - Login with username and password - Custom Input
def dataMap = CustomKeywords.'fileOperation.ReadDataFile.returnDataMap'('TC01', 'Custom-Binding')
WebUI.waitForElementVisible(findTestObject('Test Objects/Pages/Login Page/elHeader'), 60)
WebUI.verifyTextPresent('Log in to your account', false)
WebUI.setText(findTestObject('Test Objects/Pages/Login Page/elUsername'), dataMap['UserName'])



# 02 - Fill Product - Data Iteration
def dataMapList = CustomKeywords.'fileOperation.ReadDataFile.addMapList'('TC01', 'product')

for (var in dataMapList) {
	//For each product line, Add product into shopping
	//TODO: Add Example test case
}


WebUI.switchToWindowIndex(1);
WebUI.switchToWindowIndex(0);


WebUI.getUrl().contains('/login');


Create Random and calling a function 

https://github.com/jcblitz/Katalon-Demo/blob/master/Scripts/Add%20Product%20To%20Cart/Script1550595213427.groovy


https://github.com/Yessybtr/Sample-SignUp-with-Katalon-Studion-/blob/master/Libs/TempTestCase1522455329685.groovy


#Test Listeners
https://github.com/rudreshtrivedi/Katalon-Studio-Advanced/blob/master/Test%20Listeners/TestListener.groovy



https://github.com/abdullahrashid12/KatalonProject/blob/master/Libs/CustomKeywords.groovy
https://github.com/rudreshtrivedi/Katalon-Studio-Advanced/tree/master/Libs

https://github.com/rudreshtrivedi/Katalon-Studio-Advanced/blob/master/Libs/internal/GlobalVariable.groovy
https://github.com/abdullahrashid12/KatalonProject/blob/master/Libs/internal/GlobalVariable.groovy

https://github.com/abdullahrashid12/KatalonProject/blob/master/Keywords/com/jira/components/JSelect.groovy

https://github.com/datquach/katalon-ci-samples/blob/travisci/Keywords/com/example/WebUICustomKeywords.groovy

#Appi tools
https://github.com/katalon-studio-samples/katalon-integration-tests/blob/master/Scripts/Applitools/Research%20Batch/Script1533804009304.groovy
https://github.com/katalon-studio-samples/katalon-integration-tests/blob/master/Keywords/com/katalon/integration/applitools/ApplitoolsProject.groovy

https://github.com/katalon-studio-samples/dynamic-execution
https://github.com/DeepikaParanthaman/Katalon-Training
https://github.com/katalon-studio-samples/katalon-web-automation
https://github.com/executeautomation/KatalonAPITesting
https://github.com/executeautomation?tab=repositories
https://github.com/katalon-studio-samples/katalon-demo-project
https://github.com/katalon-studio-samples/katalon-regression-tests
https://github.com/butdim/unymira_Katalon
https://github.com/katalon-studio-samples/DataDrivenTest
https://github.com/katalon-studio-samples/DragAndDropExample
https://github.com/ankusharora/Katalon
https://github.com/rudreshtrivedi/Katalon-Studio-Advanced
https://github.com/KrisztianBatori/katalon
https://github.com/pallianil/katalon


https://github.com/Divshiv/KatalonProject/blob/master/Test%20Listeners/TestListener1.groovy


https://github.com/Divshiv/KatalonProject/blob/master/Test%20Suites/SampleTestSuite.groovy


https://github.com/Divshiv/KatalonProject/tree/master/Test%20Suites

