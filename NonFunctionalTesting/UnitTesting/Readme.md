# Unit Testing

* Unit testing helps you discover bugs before they become bugs. The act of thinking through how to test your code will uncover silly and stupid programming errors.
* Unit testing forces you to think through edge cases that are difficult for some to think through when you're just trying to get something to work.
* Unit tests are the* best documentation you could write. When well written, a unit test describes how code works. It also requires update when behavior changes, so it'll never be out of date; when it's not accurate, it'll break your build.
* Unit testing encourages better design. Knowing you need to write a unit test will force design considerations that otherwise take years of experience to realize. This can be a double-edge sword though, as I've seen bad design lead to worse design when unit tests are forced onto terrible existing code (i.e.: "I'll just make this thing public so I can access it from my test.")
* Most importantly, unit testing provides a very important safety net for you. If you want to add a feature, refactor some code or hand your app off to another maintainer, there's a very clear signal if something breaks and the broken unit test will tell you where it's broken and how it's supposed to work.

# 8 Benefits of Unit Testing

**1. Makes the Process Agile**
One of the main benefits of unit testing is that it makes the coding process more Agile. When you add more and more features to a software, you sometimes need to change old design and code. However, changing already-tested code is both risky and costly. If we have unit tests in place, then we can proceed for refactoring confidently.

Unit testing really goes hand-in-hand with agile programming of all flavors because it builds in tests that allow you to make changes more easily. In other words, unit tests facilitate safe refactoring. 

**2. Quality of Code**
Unit testing improves the quality of the code. It identifies every defect that may have come up before code is sent further for integration testing. Writing tests before actual coding makes you think harder about the problem. It exposes the edge cases and makes you write better code. 

**3. Finds Software Bugs Early**
Issues are found at an early stage. Since unit testing is carried out by developers who test individual code before integration, issues can be found very early and can be resolved then and there without impacting the other pieces of the code. This includes both bugs in the programmer’s implementation and flaws or missing parts of the specification for the unit.

**4. Facilitates Changes and Simplifies Integration**
Unit testing allows the programmer to refactor code or upgrade system libraries at a later date and make sure the module still works correctly. Unit tests detect changes that may break a design contract. They help with maintaining and changing the code.

Unit testing reduces defects in the newly developed features or reduces bugs when changing the existing functionality. 

Unit testing verifies the accuracy of the each unit. Afterward, the units are integrated into an application by testing parts of the application via unit testing. Later testing of the application during the integration process is easier due to the verification of the individual units.

**5. Provides Documentation**
Unit testing provides documentation of the system. Developers looking to learn what functionality is provided by a unit and how to use it can look at the unit tests to gain a basic understanding of the unit’s interface (API).

**6. Debugging Process**
Unit testing helps simplify the debugging process. If a test fails, then only the latest changes made in the code need to be debugged.

**7. Design**
Writing the test first forces you to think through your design and what it must accomplish before you write the code. This not only keeps you focused; it makes you create better designs. Testing a piece of code forces you to define what that code is responsible for. If you can do this easily, that means the code’s responsibility is well-defined and therefore that it has high cohesion.

**8. Reduce Costs**
Since the bugs are found early, unit testing helps reduce the cost of bug fixes. Just imagine the cost of a bug found during the later stages of development, like during system testing or during acceptance testing. Of course, bugs detected earlier are easier to fix because bugs detected later are usually the result of many changes, and you don’t really know which one caused the bug. 

# Unit Testing Anti-Patterns — Full List

**Cuckoo1 (aka Stranger 3).** This is a test method that sits in the same unit test but doesn't really belong there.
**Test-per-Method1.** Although a one-to-one relationship between test and production classes is a reasonable starting point, a one-to-one relationship between test and production method is almost always a bad idea.
**Anal Probe2.** A test that has to use unhealthy ways to perform its task, such as reading private fields using reflection.
**Conjoined Twins2.** Tests that are called unit tests but are really integration tests since there is no isolation between the system-under-test and the tests.
**Happy Path (aka Success Against All Odds 3, Liar 3).** The tests stay on happy paths (i.e. expected results) without testing for boundaries and exceptions.
**Slow Poke3.** A unit test that runs incredibly slow. When developers kick it off, they have time to go to the bathroom, grab a smoke, or worse, kick the test off before they go home at the end of the day.
**Giant3.** A unit test that, although it is validly testing the object under test, can span thousands of lines and contain many many test cases. This can be an indicator that the system-under-test is a God Object.
**Mockery3.** Sometimes mocking can be good, and handy. But sometimes developers can lose themselves in their effort to mock out what isn't being tested. In this case, a unit test contains so many mocks, stubs, and/or fakes that the system under test isn't even being tested at all, instead data returned from mocks is what is being tested.
**Inspector3.** A unit test that violates encapsulation in an effort to achieve 100% code coverage, but knows so much about what is going on in the object that any attempt to refactor will break the existing test and require any change to be reflected in the unit test.
**Generous Leftovers3** (aka Chain Gang, Wet Floor).** An instance where one unit test creates data that is persisted somewhere and another test reuses the data for its own devious purposes. If the "generator" is ran afterward, or not at all, the test using that data will outright fail.
**Local Hero3 **(aka Hidden Dependency, Operating System Evangelist, Wait and See, Environmental Vandal).** A test case that is dependent on something specific to the development environment it was written on, in order to run. The result is that the test passes on development boxes, but fails when someone attempts to run it elsewhere.
**Nitpicker3.** A unit test which compares a complete output when it's really only interested in small parts of it, so the test has to continually be kept in line with otherwise unimportant details.
**Secret Catcher3.** A test that at first glance appears to be doing no testing due to the absence of assertions, but as they say, "the devil is in the details." The test is really relying on an exception to be thrown when a mishap occurs, and is expecting the testing framework to capture the exception and report it to the user as a failure.
**Dodger3.** A unit test which has lots of tests for minor (and presumably easy to test) side effects, but never tests the core desired behavior. Sometimes you may find this in database access related tests, where a method is called, then the test selects from the database and runs assertions against the result.
**Loudmouth3.** A unit test (or test suite) that clutters up the console with diagnostic messages, logging, and other miscellaneous chatter, even when tests are passing.
**Greedy Catcher3**. A unit test which catches exceptions and swallows the stack trace, sometimes replacing it with a less informative failure message, but sometimes even just logging (cf. Loudmouth) and letting the test pass.
**Sequencer3.** A unit test that depends on items in an unordered list appearing in the same order during assertions.
**Enumerator3 (aka Test With No Name).** Unit tests where each test case method name is only an enumeration, e.g. test1, test2, test3. As a result, the intention of the test case is unclear, and the only way to be sure is to read the test case code and pray for clarity.
**Free Ride3 (aka Piggyback).** Rather than write a new test case method to test another feature or functionality, a new assertion rides along in an existing test case.
**Excessive Setup3 (aka Mother Hen).** A test that requires a lot of work to set up in order to even begin testing. Sometimes several hundred lines of code are used to set up the environment for one test, with several objects involved, which can make it difficult to really ascertain what is being tested due to the "noise" of all of the setup.
**Line hitter.** At first glance, the tests cover everything and code coverage tools confirm it with 100%, but in reality, the tests merely hit the code, without doing any output analysis.
**Forty-Foot Pole Test (see)**. Afraid of getting too close to the class they are trying to test, these tests act at a distance, separated by countless layers of abstraction and thousands of lines of code from the logic they are checking.


* [How to use Sinon.JS, a mocking library for testing](https://www.youtube.com/watch?v=SvudHPTEsIk)
https://www.packtpub.com/books/content/unit-testing-and-end-end-testing

https://engineering.linkedin.com/blog/2016/11/ios--test-pyramid

GOTO 2013 • JS Unit Testing Good Practices & Horrible Mistakes • Roy Osherove
https://www.youtube.com/watch?v=iP0Vl-vU3XM


6. Writing Testable JavaScript
https://www.youtube.com/watch?v=OzjogCFO4Zo

GTAC 2013 Day 2 Keynote: Testable JavaScript - Architecting Your Application for Testability
https://www.youtube.com/watch?v=JjqKQ8ezwKQ

Breaking the Matrix - Android Testing at Scale
https://www.youtube.com/watch?v=uHoB0KzQGRg

Android UI Automation
https://www.youtube.com/watch?v=O1u8iBLUFL0

Appium: Automation for Mobile Apps
https://www.youtube.com/watch?v=1J0aXDbjiUE


How Facebook Tests Facebook on Android
https://www.youtube.com/watch?v=HUE_yrd8tl0

Evolution from Quality Assurance to Test Engineering
https://www.youtube.com/watch?v=nyOHJ4GR4iU
