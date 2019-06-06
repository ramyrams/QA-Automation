

```groovy
import com.kms.katalon.core.configuration.RunConfiguration as RC
import com.kms.katalon.core.testdata.TestDataFactory as TestDataFactory

if (RC.getExecutionProfile()=='default'){
    def data = TestDataFactory.findTestData("excel_file_1")
    } else {
    def data = TestDataFactory.findTestData("excel_file_2")
}
```



#Web UI
* Alert
  * Accept Alert
  * Dismiss Alert
  * Get Alert Text
  * Set Alert Text
  * Verify Alert Not Present
  * Verify Alert Present
  * Wait For Alert
* Browser
  * Authenticate
  * Back
  * Close Browser
  * Close Window Index
  * Close Window Title
  * Close Window Url
  * Delete All Cookies
  * Execute JavaScript
  * Forward
  * Get Page Height
  * Get Page Width
  * Get Url
  * Get Viewport Height
  * Get Viewport Left Position
  * Get Viewport Top Position
  * Get Viewport Width
  * Get Window Index
  * Get Window Title
  * Maximize Window
  * Navigate to Url
  * Open Browser
  * Refresh
  * Scroll To Position
  * Set View Port Size
  * Switch To Window Index
* Checkbox
	[Web UI] Verify Element Not Checked
  * Check
  * Un-check
  * Verify Element Checked
* Combo box
  * Deselect All Option
  * Deselect Option By Index
  * Deselect Option By Label
  * Deselect Option By Value
  * Get Number Of Selected Option
  * Get Number Of Total Option
  * Select All Option
  * Select Option By Index
  * Select Option By Label
  * Select Option By Value
  * Verify Option Not Present By Label
  * Verify Option Not Present By Value
  * Verify Option Not Selected By Index
  * Verify Option Not Selected By Label
  * Verify Option Not Selected By Value
  * Verify Option Present By Label
  * Verify Option Present By Value
  * Verify Option Selected By Index
  * Verify Option Selected By Label
  * Verify Option Selected By Value
  * Verify Options Present
* Element
  * Click
  * Click Offset
  * Double Click
  * Drag And Drop By Offset
  * Drag And Drop To Object
  * Focus
  * Get All Links On Current Page
  * Get Attribute
  * Get CSS Value
  * Get Element Height
  * Get Element Left Position
  * Get Element Width
  * Mouse Over
  * Mouse Over Offset
  * Right Click
  * Right Click Offset
  * Scroll To Element
  * Verify All Links On Current Page Accessible
  * Verify Element Attribute Value
  * Verify Element Clickable
  * Verify Element Has Attribute
  * Verify Element Not Clickable
  * Verify Element Not Has Attribute
  * Verify Element Present
  * Verify Element Not Present
  * Verify Element Visible
  * Verify Element Not Visible
  * Form
  * Submit
* Frame
  * Switch To Default Content
  * Switch To Frame
* Image
  * Click Image
  * Type On Image
  * Verify Image Present
  * Wait For Image Present
* Text
  * Get Text
  * Send Keys
  * Set Encrypted Text
  * Set Masked Text
  * Set Text
  * Verify Text Not Present
  * Verify Text Present
* Upload File
* Test Object API
  * Modify Object Property
  * Remove Object Property

Utilities
  * Call Test Case
  * Comment
  * Concatenate
  * Delay
 
