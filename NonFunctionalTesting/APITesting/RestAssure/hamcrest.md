
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

# Hamcrest collection matchers

## Object has property
```java
@Test
public void object_has_property () {
    Truck pickupTruck = new Truck("Ram", "Dodge", 1965);
    assertThat(pickupTruck, hasProperty("model"));
} 
```

## Iterables - With size
```java
@Test
public void check_size_of_iterable () {

    List<String> cloths = Lists.newArrayList(
            "shirts", "shoes", "pants", "socks");

    assertThat(cloths, IsIterableWithSize.<String>iterableWithSize(4));
}
```

## Has order
```java
@Test
public void iterable_has_any_order () {

    List<String> cloths = Lists.newArrayList(
            "shirts", "shoes", "pants", "socks");

    assertThat(cloths, IsIterableContainingInAnyOrder.
            <String>containsInAnyOrder("shoes", "pants", "shirts", "socks"));

}
```

## Matches order
```java
@Test
public void iterable_matches_order () {

    List<String> cloths = Lists.newArrayList(
            "shirts", "shoes", "pants", "socks");

    assertThat(cloths, IsIterableContainingInOrder.
            <String>contains("shirts", "shoes", "pants", "socks"));

}
```

## Array - With size
```java
@Test
public void check_size_of_array () {

    Integer[] numbers = new Integer[] {10, 15, 20};
    assertThat(numbers, arrayWithSize(3));
}
```

## Contains all
```java
@Test
public void array_contains_all_elements () {

    Integer[] numbers = new Integer[] {10, 15, 20};
    assertThat(numbers, arrayContaining(10, 15, 20));
}
```

## Contains in any order
```java
@Test
public void array_contains_all_elements_in_any_order () {

    Integer[] numbers = new Integer[] {10, 15, 20};
    assertThat(numbers, arrayContainingInAnyOrder(20, 10, 15));
}
```

## Elements equal
```java
@Test
public void check_array_elements_equal() {

    Integer[] numbers = new Integer[] {10, 15, 20};
    assertThat(numbers,
            is(array(equalTo(10), equalTo(15), equalTo(20))));
}
```

## Collection - Has size
```java
@Test
public void check_size_of_collection () {

    List<String> fruit = Lists.newArrayList(
            "apple", "banana", "pear", "blackberry", "grape");

    assertThat(fruit, hasSize(5));
}
```

## In order
```java
@Test
public void collection_contains_elements_in_order () {

    List<String> fruit = Lists.newArrayList(
            "apple", "banana", "pear", "blackberry", "grape");

    assertThat(fruit, contains(
            "apple", "banana", "pear", "blackberry", "grape"));
}
```

## In any order
```java
@Test
public void collection_contains_elements_in_any_order () {

    List<String> fruit = Lists.newArrayList(
            "apple", "banana", "pear", "blackberry", "grape");

    assertThat(fruit, containsInAnyOrder(
            "banana", "apple", "blackberry", "grape", "pear"));
}
```

## Has item
```java
@Test
public void collection_contains_element () {

    List<String> fruit = Lists.newArrayList(
            "apple", "banana", "pear", "blackberry", "grape");

    assertThat(fruit, hasItem("apple"));
}
```

## Has items
```java
@Test
public void collection_contains_elements () {

    List<String> fruit = Lists.newArrayList(
            "apple", "banana", "pear", "blackberry", "grape");

    assertThat(fruit, hasItems("apple", "pear"));
}
```

## Element in
```java
@Test
public void element_in_collection () {

    List<String> fruit = Lists.newArrayList(
            "apple", "banana", "pear", "blackberry", "grape");

    assertThat("apple", isIn(fruit));
}
```

## Element is one of
```java
@Test
public void element_in_one_of () {

    List<String> fruit = Lists.newArrayList(
            "apple", "banana", "pear", "blackberry", "grape");

    assertThat("apple", isOneOf(fruit.toArray()));
}
```

## Is empty
```java
@Test
public void collection_is_empty () {

    List<String> fruit = Lists.newArrayList();
    assertThat(fruit, empty());
}
```

## Is not empty
```java
@Test
public void collection_is_not_empty () {

    List<String> fruit = Lists.newArrayList(
            "apple", "banana", "pear", "blackberry", "grape");
    assertThat(fruit, not(empty()));
}
```

## Each element ends with
```java
@Test
public void each_element_ends_with () {

    List<String> cereal = Lists.newArrayList(
            "mini wheats", "corn flakes",
            "honey smacks", "apple jacks",
            "lucky charms");

    assertThat(cereal, hasItem(endsWith("s")));
}
```

## Map - Has entry
```java
@Test
public void map_has_entry () {

    Map<String, String> breeds = Maps.newHashMap();
    breeds.put("labrador", "buzz");
    breeds.put("dachshund", "gypsy");
    breeds.put("boxer", "buddy");

    assertThat(breeds, hasEntry("labrador", "buzz"));
}
```

## Has key
```java
@Test
public void map_has_key () {

    Map<String, String> breeds = Maps.newHashMap();
    breeds.put("labrador", "buzz");
    breeds.put("dachshund", "gypsy");
    breeds.put("boxer", "buddy");

    assertThat(breeds, hasKey("labrador"));
}
```

## Has value
```java
@Test
public void map_has_hasValue () {

    Map<String, String> breeds = Maps.newHashMap();
    breeds.put("labrador", "buzz");
    breeds.put("dachshund", "gypsy");
    breeds.put("boxer", "buddy");

    assertThat(breeds, hasValue("gypsy"));
}
```

# Hamcrest core matchers

## allOf
```java
@Test
public void hamcrest_core_allof () {

    String microBrew = "Lake Louie Brewery Company";

    assertThat(microBrew, allOf(startsWith("Lake"), containsString("Brew")));
}
```

## anyOf
```java
@Test
public void hamcrest_core_anyOf () {

    String microBrew = "Grumpy Troll Brewery";

    assertThat(microBrew, anyOf(startsWith("brew"), containsString("Troll")));
}
```

## anyThing
```java
@Test
public void hamcrest_core_anything () {

    assertThat("", anything());
}
```

## Combine matchers
```java
@Test
public void hamcrest_core_combinableMatcher () {

    String isLite = "Miller Lite";

    assertThat(isLite, both(containsString("Miller")).and(containsString("Lite")));
}
```

## containString
```java
@Test
public void hamcrest_core_containsString () {

    String brewery = "Pabst Brewing Company";

    assertThat(brewery, containsString("Brew"));
}
```

## describedAs
@Test
public void hamcrest_core_describedAs () {

    BigDecimal myBigDecimal = new BigDecimal("0");

    assertThat(myBigDecimal,
            describedAs("a big decimal equal to %0",
                    equalTo(myBigDecimal),
                    myBigDecimal.toPlainString()));
}
```

## everyItem
@Test
public void hamcrest_core_every () {

    List<Integer> ages = Lists.newArrayList(21, 25, 30, 18);
    assertThat(ages, everyItem(greaterThanOrEqualTo(18)));
}

```
## hasItems
```java
@Test
public void hamcrest_core_hasItems () {

    List<String> regionalBreweries = Lists.newArrayList(
            "Capital Brewery",
            "City Brewing Company ",
            "Jacob Leinenkugel Brewing Company",
            "Lakefront Brewery, Inc.",
            "New Glarus Brewing Company",
            "Stevens Point Brewery");

    assertThat(regionalBreweries, hasItems(
            "Capital Brewery",
            "City Brewing Company ",
            "Jacob Leinenkugel Brewing Company",
            "Lakefront Brewery, Inc.",
            "New Glarus Brewing Company",
            "Stevens Point Brewery"));
}
```

## hasItems w/ matchers
```java
@Test
@SuppressWarnings("unchecked")
public void hamcrest_core_hasItems_matchers () {

    List<String> regionalBreweries = Lists.newArrayList(
            "Capital Brewery",
            "City Brewing Company ",
            "Jacob Leinenkugel Brewing Company",
            "Lakefront Brewery",
            "New Glarus Brewing Company",
            "Stevens Point Brewery");

    assertThat(regionalBreweries, hasItems(
            containsString("Brew"),
            endsWith("y")));
}
```

## is equalTo
```java
@Test
public void hamcrest_core_is() {

    String isLite = "Miller Brewing Company";

    assertThat("Miller Brewing Company", is(equalTo(isLite)));
}
```

## is notNullValue
```java
@Test
public void hamcrest_core_is_notNullValue () {

    Set<String> daNull = new HashSet<String>();

    assertThat(daNull, is(notNullValue()));
}
```

## is nullValue
```java
@Test
public void hamcrest_core_is_nullValue () {

    Set<String> daNull = null;

    assertThat(daNull, is(nullValue()));
}
```

## isSameInstance
```java
@Test
public void hamcrest_core_is_same_list () {

    List<String> someList = new ArrayList<String>();

    assertThat(someList, IsSame.<List<String>>sameInstance(someList));
}
```

## isA
```java
@Test
public void hamcrest_core_isA() {

    Map<Integer, String> map = new HashMap<Integer, String>();

    assertThat(map, isA(Map.class));
}
```

## equalTo
```java
@Test
public void hamcrest_core_isEqual () {

    String spottedCreator = "New Glarus Brewing Company";

    assertThat(spottedCreator, equalTo("New Glarus Brewing Company"));
}
```

## instanceOf
@Test
public void hamcrest_core_isInstanceOf () {

    Calendar cal = Calendar.getInstance();

    assertThat(cal, instanceOf(Calendar.class));
}

```
## is sameInstance
```java
@Test
public void hamcrest_core_isSame_string () {

    String wiBrewery = "Capital Brewery";
    String wiRegionalBrewery = "Capital Brewery";

    assertThat(wiRegionalBrewery, IsSame.<String>sameInstance(wiBrewery));
}

```
## endsWith
```java
@Test
public void hamcrest_core_string_endsWith () {

    String baseBallTeam = "Milwaukee brewers";

    assertThat(baseBallTeam, endsWith("brewers"));
}
```

## startsWith
```java
@Test
public void hamcrest_core_string_startsWith () {

    String highSchool = "Tarpon spring spongers";

    assertThat(highSchool, startsWith("Tarpon"));
}
```


https://www.javacodegeeks.com/2015/11/hamcrest-matchers-tutorial.html
https://www.baeldung.com/java-junit-hamcrest-guide
https://www.programcreek.com/java-api-examples/org.hamcrest.Matchers
https://objectpartners.com/2013/09/18/the-benefits-of-using-assertthat-over-other-assert-methods-in-unit-tests/
