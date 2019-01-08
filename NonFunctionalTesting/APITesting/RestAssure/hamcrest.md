
What is Hamcrest?
Hamcrest is a framework for creating matcher objects. These matcher objects are predicates and are used to write rules which can be satisfied under certain conditions. They are most often used in automated testing, though the can be used in other scenarios such as data validation. Hamcrest lets us step beyond simple JUnit asserts and enables us to craft very specific, readable verification code.

Hamcrest is designed to make tests very readable. It makes liberal use of static methods to create an assertion grammar which is easy to write and to understand. When used in conjunction with JUnit and Mockito it allows us to write clear, concise tests which satisfy the property of good unit testing which is to ‘test one thing’.



# Defining a Hamcrest dependency for Maven
```xml
<dependency>
	<groupId>org.hamcrest</groupId>
	<artifactId>hamcrest-library</artifactId>
	<version>1.3</version>
	<scope>test</scope>
</dependency>
```

# Defining a Hamcrest dependency for Gradle
```java
dependencies {
    testCompile "org.hamcrest:hamcrest-all:1.3"
}
```


# Static import
```java
import static org.hamcrest.MatcherAssert.assertThat;
import static org.hamcrest.Matchers.*;
import static org.hamcrest.MatcherAssert.assertThat;
import static org.hamcrest.Matchers.is;
import static org.hamcrest.Matchers.equalTo;

```

# An Example Test
```java
public class StringMatcherTest {
    
    @Test
	public void test_failed() throws Exception {
	// Given
	Integer number = 7;
	// Then
	assertThat(number, greaterThan(10));
	}


    @Test
	public void given2Strings_whenIsEqual_thenCorrect() {
	    String str1 = "text";
	    String str2 = "text";
	    assertThat(str1, is(str2));
	}

    @Test
    public void given2Strings_whenEqual_thenCorrect() {
        String a = "foo";
        String b = "FOO";
        assertThat(a, equalToIgnoringCase(b));
    }
}
```

# Hamcrest 1.3 Quick Reference
https://www.marcphilipp.de/downloads/posts/2013-01-02-hamcrest-quick-reference/Hamcrest-1.3.pdf

# Hamcrest matchers
* XML matchers [Examples](https://www.leveluplunch.com/java/examples/hamcrest-xml-matchers-junit-testing/)
  * Has xpath
* Bean matchers [Examples](https://www.leveluplunch.com/java/examples/hamcrest-bean-matchers-junit-testing/)
  * Object has property
  * Object has property with value
  * Object has same property as
* Collection matchers [Examples](https://www.leveluplunch.com/java/examples/hamcrest-collection-matchers-junit-testing/)
  * Iterables - With size
  * Iterables - Has order
  * Iterables - Matches order
  * Array - With size
  * Array - Contains all
  * Array - Contains in any order
  * Array - Elements equal
  * Collection - Has size
  * Collection - In order
  * Collection - In any order
  * Collection - Has item
  * Collection - Has items
  * Collection - Element in
  * Collection - Element is one of
  * Collection - Is empty
  * Collection - Is not empty
  * Collection - Each element ends with
  * Map - Has entry
  * Map - Has key
  * Map - Has value
* Core matchers [Examples](https://www.leveluplunch.com/java/examples/hamcrest-core-matchers-junit-testing/)
  * allOf
  * anyOf
  * anyThing
  * Combine matchers
  * containString
  * describedAs
  * everyItem
  * hasItems
  * hasItems w/ matchers
  * is equalTo
  * is notNullValue
  * is nullValue
  * isSameInstance
  * isA
  * equalTo
  * instanceOf
  * is sameInstance
  * endsWith
  * startsWith
* Number matchers [Examples](https://www.leveluplunch.com/java/examples/hamcrest-number-matchers-junit-testing/)
  * Is closeTo
  * greaterThan
  * Every item greaterThan
  * Every item greaterThanOrEqualTo
  * Every item lessthan
  * Every item lessThanOrEqualTo
  * Is closeTo
* Object matchers [Examples](https://www.leveluplunch.com/java/examples/hamcrest-object-matchers-junit-testing/)
  * Has toString
  * EqualsTo
  * Instance of
  * Type compatiable with
  * Not null value
  * Null value
* Text matchers [Examples](https://www.leveluplunch.com/java/examples/hamcrest-text-matchers-junit-testing/)
  * Is Empty
  * Is empty or null string
  * Equal to
  * Equal to ignore case
  * Equal to ignore whitespace
  * Contains string
  * Ends with
  * Starts with
  * String contains in order


# Hamcrest XML matchers
## Has xpath
```java
@Test
public void test_xml_path () throws Exception {

    String aListApartXML = "<daily-values> " +
             "  <total-fat units=\"g\">65</total-fat> " +
             "  <saturated-fat units=\"g\">20</saturated-fat> " +
             "  <cholesterol units=\"mg\">300</cholesterol> " +
             "  <sodium units=\"mg\">2400</sodium> " +
             "  <carb units=\"g\">300</carb> " +
             "  <fiber units=\"g\">25</fiber> " +
             "  <protein units=\"g\">50</protein> " +
             "</daily-values> ";

    Document xml = parse(aListApartXML);

    assertThat(xml, hasXPath("/daily-values/saturated-fat", equalTo("20")));
}

private static Document parse(String xml) throws Exception {
    DocumentBuilderFactory documentBuilderFactory = DocumentBuilderFactory.newInstance();
    documentBuilderFactory.setNamespaceAware(false);
    DocumentBuilder documentBuilder = documentBuilderFactory.newDocumentBuilder();
    return documentBuilder.parse(new ByteArrayInputStream(xml.getBytes()));
}
```

# Hamcrest bean matchers
## Setup
```java
class Truck {

    private String model;
    private String make;
    private int year;

    public Truck(String model, String make, int year) {
        super();
        this.model = model;
        this.make = make;
        this.year = year;
    }

    // getters/setters
}
```

## Object has property
```java
@Test
public void object_has_property () {
    Truck pickupTruck = new Truck("Ram", "Dodge", 1965);
    assertThat(pickupTruck, hasProperty("model"));
} 
```


## Object has property with value
```java
@Test
public void object_has_property_with_value () {
    Truck pickupTruck = new Truck("Big 10", "Chevy", 1976);
    assertThat(pickupTruck, hasProperty("model", equalTo("Big 10")));
}  
```
  
## Object has same property as
```java
@Test
public void object_has_property_values_as () {
    Truck pickupTruck1 = new Truck("Big 10", "Chevy", 1976);
    Truck pickupTruck2 = new Truck("Big 10", "Chevy", 1976);
    assertThat(pickupTruck1, samePropertyValuesAs(pickupTruck2));
}    
```


https://www.javacodegeeks.com/2015/11/hamcrest-matchers-tutorial.html
https://www.baeldung.com/java-junit-hamcrest-guide
https://www.programcreek.com/java-api-examples/org.hamcrest.Matchers
https://objectpartners.com/2013/09/18/the-benefits-of-using-assertthat-over-other-assert-methods-in-unit-tests/
