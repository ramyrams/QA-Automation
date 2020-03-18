'Get full directory\'s path of android application'
def appPath = PathUtil.relativeToAbsolutePath(GlobalVariable.G_AndroidApp, RunConfiguration.getProjectDir())


'Start application on current selected android\'s device'
Mobile.startApplication(GlobalVariable.G_AndroidApp, false)
Mobile.startExistingApplication(appId)

Mobile.tap(findTestObject('Application/android.widget.TextView - App'), 10)


'Get displayed message on the dialog'
def message = Mobile.getText(findTestObject('Application/App/Activity/Custom Dialog/android.widget.TextViewCustomDialog'), 10)

'Verify if displayed message is correct'
Mobile.verifyEqual(message, 'Example of how you can use a custom Theme.Dialog theme to make an activity that looks like a customized dialog, here with an ugly frame.')

'Clear displayed text on the dialog'
Mobile.clearText(findTestObject('Application/App/Activity/Custom Dialog/android.widget.TextViewCustomDialog'), 10)

'Close any sudden notifications'
Mobile.closeNotifications()


'Check on subscribe checkbox'
Mobile.checkElement(findTestObject('Application/App/Activity/android.widget.Check - Subscribe'), 10)

'Drag and drop a button into another frame'
Mobile.dragAndDrop(findTestObject('Application/App/Activity/android.widget.Button'),findTestObject('Application/App/Activity/android.widget.Frame 1'), 10)

Mobile.doubleTap(findTestObject('android.widget.Button0 - NEXT'), 0)

WebElement element = Mobile.findImageElement("/Users/myaccount/Desktop/image.png")
println "Element found at: (" + element.getPosition().x + ", " + element.getPosition().y + ")"

List<WebElement> elements = Mobile.findImageElements("/Users/myaccount/Desktop/image.png")
println "Number of elements found: " + elements.size()

'Get text of android.widget.TextView - App'
Mobile.getAttribute(findTestObject('Application/android.widget.TextView - App'), 'text', 5)

'Drag and drop a button into another frame'
Mobile.getElementHeight(findTestObject('Application/App/Activity/android.widget.Button'), 10)

'Get left position of android.widget.TextView - App'
left_position = Mobile.getElementLeftPosition(findTestObject('android.widget.TextView - App'), 5)

'Get top position of android.widget.TextView - App'
top_position = Mobile.getElementTopPosition(findTestObject('android.widget.TextView - App'), 5)

'Drag and drop a button into another frame'
Mobile.getElementWidth(findTestObject('Application/App/Activity/android.widget.Button'), 10)


'Get current orientation of selected android device'
orientation = Mobile.getCurrentOrientation()

'Get device\'s physical height'
height = Mobile.getDeviceHeight()

'Get device manufacturer'
manufacturer = Mobile.getDeviceManufacturer()

'Get current device OS'
os = Mobile.getDeviceOS()

'Get current device OS version'
version = Mobile.getDeviceOSVersion()

'Get device\'s physical width'
width = Mobile.getDeviceWidth()

'Hide keyboard'
Mobile.hideKeyboard()

Mobile.longPress(findTestObject('android.widget.Button0 - NEXT'), 0)

'Open any sudden notifications'
Mobile.openNotifications()

'Back to previous screen'
Mobile.pressBack()

'Back to home screen'
Mobile.pressHome()


'Pinch to zoom in at position 200,300'
Mobile.pinchToZoomInAtPosition(200, 300, 20)

'Pinch to zoom in at position 200,300'
Mobile.pinchToZoomInAtPosition(200, 300, 20)

'Run the appication in background and wait for 10 seconds'
Mobile.runIOSAppInBackgroundAndWait(10)

'Scroll to element which displayed text is Xfermodes'
Mobile.scrollToText('Xfermodes')

'Get item\'s label'
def itemText = Mobile.getText(findTestObject('Application/Graphics/android.widget.TextView - Xfermodes'), GlobalVariable.G_Timeout)

'Verify if item\'s label is equal to \"Xfermodes\"'
Mobile.verifyEqual(itemText, 'Xfermodes')

Mobile.sendKeys('Katalon Studio')

Mobile.scrollToText('Xfermodes')

'Select the third item in the list'
Mobile.selectListItemByIndex(findTestObject('Object Repository/Application/App/android.widget.TextView-Activity'), 3, 10)

'Select \'Record 1\' item in the list'
Mobile.selectListItemByLabel(findTestObject('android.widget.Button1 - Go to List'), 'Record 1', 10)

Mobile.setEncryptedText(findTestObject('New One/android.widget.EditText0 (1)'), 'IEW1vyGbESL6h22Ztkgy5Q==', 0)

'Set slider value at 50% of the slider'
Mobile.setSliderValue(findTestObject('/Application/App/android.widget.SeekBar0'), 50, 10)
 
 
'Set text on textbox control'
Mobile.setText(findTestObject('Application/Graphics/android.widget.TextView - Xfermodes'),'Your text here', GlobalVariable.G_Timeout)

'Switch the current device to landscape mode'
Mobile.switchToLandscape()

'Switch the current device to native context'
Mobile.switchToNative()

'Swipe from 200,300 to 400,600 posisition on screen'
Mobile.swipe(200, 300, 400, 600)
 
'Since 5.1.0.2, endX and endY will be relative position of (startX, startY) position
Mobile.swipe(200, 300, 200, 300)

'Switch the current device to portrait mode'
Mobile.switchToPortrait()

'Switch the current device to web view context'
Mobile.switchToWebView()

'Take screenshot of current device screen'
Mobile.takeScreenshot("D:\\screenshot.png")


'Tap at 200,300 position'
Mobile.tapAtPosition(200, 300)

'Tap at 200,400 position and hold it for 10 seconds'
Mobile.tapAndHoldAtPosition(200, 400, 10)

Mobile.tapOnImage("/Users/myaccount/Desktop/image.png")

'Uncheck subscribe checkbox'
Mobile.uncheckElement(findTestObject('Application/App/Activity/android.widget.Check - Subscribe'), 10)


boolean isPresent = Mobile.verifyImagePresent("/Users/myaccount/Desktop/image.png")

'Verify if the current device is in landscape mode'
Mobile.verifyIsLandscape()



'Verify if the current device is in portrait mode'
Mobile.verifyIsPortrait()


'Turn on airplane mode'
Mobile.toggleAirplaneMode('yes')


'Wait until the device is locked'
Mobile.delay(60)

'Unlock screen'
Mobile.unlockScreen()


'Check on subscribe checkbox'
Mobile.checkElement(findTestObject('Application/App/Activity/android.widget.Check - Subscribe'), 10)


'Verify App control has attribute class with value android.widget.TextView'
Mobile.verifyElementAttributeValue(findTestObject('Application/android.widget.TextView - App'),'class','android.widget.TextView', 10)

'Verify subscribe checkbox is checked or not'
Mobile.verifyElementChecked(findTestObject('Application/App/Activity/android.widget.Check - Subscribe'), 10)

'Verify App control is presented in 10 seconds timeout'
Mobile.verifyElementExist(findTestObject('Application/android.widget.TextView - App'), 10)

'Verify App control has class attribute in 10 seconds timeout'
Mobile.verifyElementExist(findTestObject('Application/android.widget.TextView - App'),'class', 10)

Mobile.verifyElementNotChecked(findTestObject('SampleApp.apk/android.widget.CheckBox - Checkbox0'), 10)

'Verify App control is presented in 10 seconds timeout'
Mobile.verifyElementNotExist(findTestObject('Application/android.widget.TextView - App'), 10)

'Verify graphics control doesn\'t have \'package\' attribute'
Mobile.verifyElementNotHasAttribute(findTestObject('Application/android.widget.TextView - Graphics'), 'package', 12)

Mobile.verifyElementNotExist(findTestObject('android.widget.Button5 - Go to TimePicker'), 10)

'Verify app control is visible'
Mobile.verifyElementVisible(findTestObject(findTestObject('Object Repository/Application/android.widget.TextView - App')), 20)

'Wait until app control has class atribute with value android.widget.TextView'
Mobile.waitForElementAttributeValue(findTestObject(findTestObject('Object Repository/Application/android.widget.TextView - App')), 'class', 'android.widget.TextView', 20)

'Wait until app control has class atribute'
Mobile.waitForElementHasAttribute(findTestObject(findTestObject('Object Repository/Application/android.widget.TextView - App')), 'class', 20)

'Wait until app control does NOT has class atribute'
Mobile.waitForElementNotHasAttribute(findTestObject(findTestObject('Object Repository/Application/android.widget.TextView - App')), 'class', 20)


'Wait for app control to be present in 10 seconds timeout'
Mobile.waitForElementHasAttribute(findTestObject(findTestObject('Object Repository/Application/android.widget.TextView - App')), 'class', 10)

    
 
'Close application on current selected android\'s device'
Mobile.closeApplication()



-------------------
Mobile.startApplication('C:\\Users\\katalon\\Sample Apps\\APIDemos.apk',  true)

-----------------------

import com.google.common.collect.ImmutableMap as ImmutableMap;

Mobile.startApplication('C:\\Users\\katalon\\Sample Apps\\APIDemos.apk', 
  true)

String command = "mobile:changePermissions"
Map args = ImmutableMap.of("action", "grant", "appPackage","com.hmh.api",  "permissions", "android.permission.READ_CONTACTS")
Object result = Mobile.executeMobileCommand(command, args)

print result

Mobile.closeApplication()

