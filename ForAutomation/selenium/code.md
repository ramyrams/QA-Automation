

# Explicit Waits

https://seleniumjavadotcom.files.wordpress.com/2016/04/explicit-wait-flow1.jpg

https://seleniumjavadotcom.files.wordpress.com/2016/04/explicit-wait.jpg

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


# What can we do with explicit waits?
Explicit waits can be used for:

1. finding single web element

  WebDriverWait wait = new WebDriverWait(driver, 15);
  wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//input[@id='text3']")));
  
  driver.findElement(By.xpath("//input[@id='text3']")).sendKeys("Text box is visible now");
  System.out.print("Text box text3 is now visible");
  
  

2. finding multiple web elements

3. checking the web page title and url

4. checking the element’s status

5. interacting with frames



public WebElement findVisibleElement(By locator) {
   WebElement element = new WebDriverWait(driver(), timeout)
                .until( visibilityOfElementLocated (locator));
   return element;
}

public WebElement findClickableElement(By locator) {
   WebElement element = new WebDriverWait(driver(), timeout)
               .until( elementToBeClickable (locator));
   return element;
}

public WebElement findHiddenElement(By locator) {
   WebElement element = new WebDriverWait(driver(), timeout)
              .until( presenceOfElementLocated (locator));
   return element;
}


[Read complete](https://seleniumjava.com/2016/04/05/the-beginners-guide-to-explicit-waits/)
