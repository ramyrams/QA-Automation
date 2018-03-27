

# Explicit Waits

https://seleniumjavadotcom.files.wordpress.com/2016/04/explicit-wait-flow1.jpg

```java

//create the id locator for the searchBox element
By searchBoxId = By.id("search-box");

//create the wait object
WebDriverWait wait = new WebDriverWait(driver, 10);

//find the searchBox element and save it in the WebElement variable
WebElement searchBoxElement = wait.until(
                                ExpectedConditions.
                                  elementToBeClickable
                                     (searchBoxId));

//type in the searchBox element
searchBoxElement.click();
searchBoxElement.clear();
searchBoxElement.sendKeys("java");
```


[Read complete](https://seleniumjava.com/2016/04/05/the-beginners-guide-to-explicit-waits/)
