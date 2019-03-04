
https://thaygivietnay.files.wordpress.com/2017/02/selenium-tutorial.pdf
https://www.joecolantonio.com/selenium-ide/
http://www.absofttrainings.com/selenium-training-v3-selenium-ide-in-depth-for-your-job/
http://seleniummaster.com/sitecontent/index.php/introduction-to-selenium-automation/selenium-ide/114-selenium-ide-complete-list-of-commands
https://a9t9.com/kantu/docs/selenium-ide
http://www.inviul.com/selenese-relation-selenium-ide/
https://docs.katalon.com/katalon-recorder/docs/selenese-selenium-ide-commands-reference.html
https://www.joecolantonio.com/selenium-ide-guide/
https://www.seleniumhq.org/docs/02_selenium_ide.jsp


A command refers to what Selenium has to do and commands in selenium are of three types. Click on each one of them to know more about the commands.

Actions https://www.tutorialspoint.com/selenium/selenium_commands_actions.htm

Accessors https://www.tutorialspoint.com/selenium/selenium_commands_accessors.htm

Assertions  https://www.tutorialspoint.com/selenium/selenium_commands_assertions.htm


https://docs.katalon.com/katalon-recorder/docs/selenese-selenium-ide-commands-reference.html

https://www.subjectcoach.com/tutorials/detail/contents/getting-started-with-selenium/chapter/selenese-commands

http://www.inviul.com/selenese-relation-selenium-ide/

https://a9t9.com/kantu/docs/selenium-ide
http://seleniummaster.com/sitecontent/index.php/introduction-to-selenium-automation/selenium-ide/114-selenium-ide-complete-list-of-commands
# Assertions
These commands are like accessors, but they verify that the state of the application conforms to what is expected.
Now the Selenium Assertions can also be categorized into three categories:

Assert: When an ‘Assert’ fails, the test is aborted.
Verify: When a ‘Verify’ fails, the test will continue execution, logging the failure.
WaitFor: Wait for some condition to become true. They will succeed immediately if the condition is already true. However, they will fail and halt the test if the condition does not become true within the current timeout setting.
 

# Commonly used Selenium IDE commands:
type: Sets the value of an input field, as though you typed it in.
open: Opens a page using a URL.
click: Clicks on a link, button, checkbox or radio button.
clickAndWait: Clicks on a link, button, checkbox or radio button. If the click action causes a new page to load (like a link usually does), call waitForPageToLoad.
select: Select an option from a drop-down using an option locator.
selectFrame: Selects a frame within the current window.
verifyTitle/assertTitle: Verifies an expected page title.
verifyTextPresent: Verifies that the specified text pattern appears somewhere on the rendered page shown to the user.
verifyElementPresent: Verifies that the specified element is somewhere on the page.
waitForPageToLoad: Waits for a new page to load. You can use this command instead of the “AndWait” suffixes, “clickAndWait”, “selectAndWait”, “typeAndWait” etc.
highlight: Briefly changes the backgroundColor of the specified element yellow. Useful for debugging.
pause: Wait for the specified amount of time (in milliseconds)
store: The name of a variable in which the result is to be stored. This command is a synonym for storeExpression.
echo: Prints the specified message into the third table cell in your Selenese tables. Useful for debugging.
refresh: Simulates the user clicking the “Refresh” button on their browser


http://www.absofttrainings.com/selenium-training-v3-selenium-ide-in-depth-for-your-job/

https://www.joecolantonio.com/selenium-ide/

https://thaygivietnay.files.wordpress.com/2017/02/selenium-tutorial.pdf

https://examples.javacodegeeks.com/enterprise-java/selenium/selenium-ide-commands-example/
https://www.seleniumhq.org/docs/02_selenium_ide.jsp
