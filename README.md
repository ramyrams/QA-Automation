

As a good first guess, Google often suggests a 70/20/10 split: 70% unit tests, 20% integration tests, and 10% end-to-end tests.

![1](https://res.infoq.com/articles/contract-testing-spring-cloud-contract/en/resources/1image14-contract-testing-spring-cloud-1532762674022.png)

![1](https://toyerm.files.wordpress.com/2018/10/slide13.jpg)

# QA
* [A real-world guide to continuous testing](http://techbeacon.com/real-world-guide-continuous-testing)
* [Career Path of a Tester!](https://essenceoftesting.blogspot.sg/2016/12/career-path-of-tester.html)
* [AUTOMATED TEST CLASSIFICATION](http://www.jamkey.fr/automated-test-classification/)
* [TECHNICAL TEST STRATEGY](http://www.jamkey.fr/technical-test-strategy/)
* [Continuous Testing](http://www.awesome-testing.com/2016/10/testops-3-continuous-testing.html)
* [What Tools Should I Learn? ](https://dojo.ministryoftesting.com/lessons/what-tools-should-i-learn)

7 Quick Steps To Become a Great Automation Testing Engineer 
https://dzone.com/articles/7-quick-steps-to-become-a-great-automation-testing?

# ROI
https://abstracta.us/2015/08/31/the-true-roi-of-test-automation/
https://dzone.com/articles/the-roi-of-automated-testing
https://dzone.com/articles/additional-considerations-for-automated-testing

The following types of testing can be automated
* **Functional** – testing that operations perform as expected. 
* **Regression** – testing that the behavior of the system has not changed. 
* **Exception or Negative** – forcing error conditions in the system. 
* **Stress** – determining the absolute capacities of the application and operational infrastructure. 
* **Performance** – providing assurance that the performance of the system will be adequate for both batch runs and online transactions in relation to business projections and requirements. 
* **Load** – determining the points at which the capacity and performance of the system become degraded to the situation that hardware or software upgrades would be required. 


Automated testers must follow the following guidelines to get the benefits of automation:
* **Concise:** As simple as possible and no simpler. 
* **Self-Checking:** Test reports its own results; needs no human interpretation. 
* **Repeatable:** Test can be run many times in a row without human intervention. 
* **Robust:** Test produces same result now and forever. Tests are not affected by changes in the external environment. 
* **Sufficient:** Tests verify all the requirements of the software being tested. 
* **Necessary:** Everything in each test contributes to the specification of desired behavior. 
* **Clear:** Every statement is easy to understand. 
* **Efficient:** Tests run in a reasonable amount of time. 
* **Specific:** Each test failure points to a specific piece of broken functionality; unit test failures provide "defect triangulation". 
* **Independent:** Each test can be run by itself or in a suite with an arbitrary set of other tests in any order. 
* **Maintainable:** Tests should be easy to understand and modify and extend. 
* **Traceable:** To and from the code it tests and to and from the requirements. 

# Selenium-Grid-Extras
https://github.com/groupon/Selenium-Grid-Extras


http://www.nalashaa.com/7-key-best-practices-of-software-test-automation/

Podcast: The Testing Show
https://www.qualitestgroup.com/resources/the-testing-show/


Patterns in Automation
https://www.automatetheplanet.com/failed-tests-analysis-decorator/
https://www.automatetheplanet.com/strategy-design-pattern/
https://seleniumcamp.com/talk/design-patterns-in-test-automation/
https://blog.aspiresys.com/testing/design-patterns-in-test-automation-world/





# Benefits of Automated Testing
* **Reliable:** Tests perform precisely the same operations each time they are run, thereby eliminating human error 
* **Repeatable:** You can test how the software reacts under repeated execution of the same operations. 
* **Programmable:** You can program sophisticated tests that bring out hidden information from the application. 
* **Comprehensive:** You can build a suite of tests that covers every feature in your application. 
* **Reusable:** You can reuse tests on different versions of an application, even if the user interface changes. 
* **Better Quality Software:** Because you can run more tests in less time with fewer resources 
* **Fast:** Automated Tools run tests significantly faster than human users. 
* **Cost Reduction:** As the number of resources for regression test are reduced.

The following areas must be automated first
1. Highly redundant tasks or scenarios 
2. Repetitive tasks that are boring or tend to cause human error 
3. Well-developed and well-understood use cases or scenarios first 
4. Relatively stable areas of the application over volatile ones must be automated. 

What Is Regression Testing? Best Practices, Tutorials, and More 
https://dzone.com/articles/what-is-regression-testing-best-practices-tutorial?

# Test Types

* **Unit tests** are written by the programmers for the programmers to ensure that the code is working at the deepest/lowest level. They should execute in milliseconds and target a 100% code coverage (at least 90%).
* **Component tests** are a part of the acceptance tests and check the behavior of individual component. A component encapsulate a specific set of business rules. These kind of tests should be very quick as well because they are decoupled from the other components and should cover about half the system.
* **Integration tests** are required to check the communication between components in order to verify that the “plumbing” has been done correctly. They ensure that the architectural structure of the system is correct. About 20% of the system is covered by integration tests.
* **System tests** are executed at the highest level of the system, from the UI to check the whole application and its construction (load tests are in this category for instance). They check about 10% of the system.
* **Manual/exploratory tests** are done by humans to explore the application for unexpected behaviors. They need the human creativity to hunt possible hidden bugs.

The main idea is that you want more unit tests than any other level of test because they:
* test the behaviour of the class / component rather than its implementation
* have no dependencies on other classes / components
* are easy to write & maintain (due to their independence)
* quick to run

Integrationn tests which:
* test the integration between components / features / external 3rd party services
* are dependant on the other components / features / external 3rd party services being available & stable enough to execute tests against.
* ensure dependencies of the system being developed continue to work as expected
* are slower than unit tests to run, but faster than acceptance tests to run

Acceptance tests are:
* a tool for conversing with business stakeholders (as they are generally written in human-readable language)
* a means of knowing when we’re done (developing a component / feature)
* checking the UI by actually clicking buttons on that UI
* High dependency on other components / features
* Brittle – easily broken if the UI changes
* Slowest of the 3 automated test levels to run

# Certification
http://abstracta.academy/software-test-analyst-certification

# Test Pyramid
* [Test Automation Pyramid](https://www.slideshare.net/TAlexanderLystad/test-automation-pyramid)

# Mindmap
http://apps.testinsane.com/mindmaps/Page/1/date_desc

# Tools
* **Bug Tracking:**  Eventum, JIRA
* **Test Case Management:**  MS Excel
* **Task Management:** Trello , KanbanFlow, MS Excel
* **Collaboration Software:** Confluence,MS Excel
* **Website Redirect & HTTP Headers:** Redirects Checker
* **Google Analytics Analyzer:** Google Chrome Add-on Tag Assistant, Google Analytics Debugger
* **SSL/TLS Certification Checker:** Symantec SSL Checker, SSL Shopper Checker, Qualys SSL Server Test
* **Broken Links Checker:** My Links, 
* **Developer Tools:** Browser Developer Tools, FireBug, Chris pederick Web Developer
* **Screen Capture:** qSnap, Jing, Awesome Screenshot, Screencastify, Snipping Tool
* **Responsive Design Testing:**  Responsinator, Troy Responsinator, 
* **Visual Regression Testing:** applitools.com, PhantomCSS
* **API Functional Testing:**  SoapUI OpenSource, PostMan
* **Code Viewer:** JSON Viewer
* **Fonts Identify:** WhatFont
* **Performance Testing:** BlazeMeter Recorder, Page Speed Insights, YSlow, GTMetrix
* **Print Friendly:**  CleanPrint
* **Save for Later:**  Pocket, Basket
* **Server-side automation testing tools:** JMeter, Selenium, QTP, and FitNesse
* **Unit testing tools:** OCUnit, TestNG 
* **Custom test harness:** C#, JS, Java, and C++
* **Mobile Application Testing:** Appium
* **Reporting:** Allure

Test Automation Equipments:
Watir|Microfocus Test Partner|Microfocus Silk TestTM | Empirix e-Tester|Selenium|AutomatedQA TestComplete|IBM Rational Functional TesterTM | HP Unified Functional TestingTM ,
Performance test Equipments:
Apache Jmeter|Microfocus Silk PerformerTM |OpenSTA|HP Load RunnerTM|Microfocus QALoad|Emprix’s e-Load
Test Management Equipments:
Microfocus SilkCentral Testmanager| IBM Rational Quality Manager| TestLink |HP Quality Center
Defect Management Equipments:
JIRA|PVCS Tracker|Bugzilla|TestTrack|TestDirector|SpiraTest
Memory Leak Equipments:
Wily Introscope|Repro|Coverity Prevent|Purify|Quest Jprobe|Zone Ranger
Code Coverage Equipments:
Borland Optimizelt|Koalog Code Coverage|Cenqua Clover|Rational Pure Coverage
Configuration Management Equipments:
IBM Rational Clearcase|Perforce|Visual Source Safe|CVS


* [A Comparison of Automated Testing Tools](https://dzone.com/articles/a-comparison-of-automated-testing-tools)


# Tests
* Website testing
* Web Application Functional Testing 
* Mobile Application Functional Testing 
* Visual Regression Testing 
* Application Security Testing 
* Performance testing
* API Testing
* Penetration Testing
* Database testing
* Reponsive Design Testing	

* INITIATION
  * Statement of Work
  * Requirement Gathering

* TEST REQUIREMENT & PLANNING
  * Estimation
  * Traceability Matrix
  * Test Plan
  * Risk Assessment

* ENVIRONMENT SETUP & TEST DECISION
  * Software / Hardware Configuration
  * Vendor
  * Test Scenarios & Cases
  * Test Data Preparation

* EXECUTION & DEFECT TRACKING
  * Test Execution
  * Capture Results
  * Reviews  & Analysis
  * Share Insights

* CLOSURE REPORTING / MAINTENANCE
  * Summary Reports
  * Recommendations Report
  * Client Acceptance
  * Project Closure

# Test plan
* [Test plan questions](http://erik.brickarp.se/2016/11/test-plan-questions.html)
* [Web Test Automation Test plan ]()
* [Mobile Test Automation Test plan ]()
* [Performence Test plan ]()

http://www.zarantech.com/blog/quality-assurance-project-management/

https://abstracta.us/2015/09/21/how-to-plan-test-case-automation-with-development-2/



# Test Case Writing Best Practices
http://www.seapine.com/papers/test-case-writing-best-practices
http://quicksoftwaretesting.com/test-case-writing-tips/
http://www.testandtry.com/2010/02/24/8-tips-to-create-complete-test-cases/
How to Write a Test Case for Your Project and Your Team
https://dzone.com/articles/how-to-write-a-test-case-for-your-project-and-your

# Software Testing Wheels
![1](https://abstracta.us/wp-content/uploads/2015/12/Testing-Wheel-Design-rgb_Gene%C2%A6u%CC%88rico-967x1024.jpg)
https://abstracta.us/2015/12/15/the-software-testing-wheel/

# Test Case
* [Best Practices for Test Case Creation and Maintenance](https://dzone.com/articles/best-practices-for-test-case-creation-and-maintena)




# Sample of a Test Case

* **Title:** Login Page – Authenticate Successfully on gmail.com
* **Description:** A registered user should be able to successfully login at gmail.com.
* **Precondition:** the user must already be registered with an email address and password.
* **Assumption:** a supported browser is being used.
* **Test Steps:**
1. Navigate to gmail.com
2. In the ’email’ field, enter the email of the registered user.
3. Click the ‘Next’ button.
4. Enter the password of the registered user
5. Click ‘Sign In’
* **Expected Result:** A page displaying the gmail user’s inbox should load, showing any new message at the top of the page.


# QA services portfolio
* General mobile application quality assurance
* Mobile automation testing
* Mobile games testing
* Cross-platform testing
* OEM package validation
* Device-specific validation
* Performance testing
* Compliance testing: PCI and HIPPA
* Carrier-specific validation testing
* Publisher validation testing: OEM HIG and publisher conformance
* Usability testing
* Security testing
* Energy profiling
* Field simulation testing
* Manual functional testing
* Compatibility testing
* Usability testing
* Test automation
* Performance testing
* Security testing

# Testing
* Smoke testing
* Localization testing
* Usability testing
* Reliability testing

# Regression Testing
* Some strategies and factors to consider during this process include the following: 
* Test fixed bugs promptly. The programmer might have handled the symptoms but not have gotten to the underlying cause.
* Watch for side effects of fixes. The bug itself might be fixed but the fix might create other bugs.
* Write a regression test for each bug fixed.
* If two or more tests are similar, determine which is less effective and get rid of it.
* Identify tests that the program consistently passes and archive them.
* Focus on functional issues, not those related to design.
* Make changes (small and large) to data and find any resulting corruption.
* Trace the effects of the changes on program memory.

# Integration Testing
* You can do integration testing in a variety of ways but the following are three common strategies: 
* The top-down approach to integration testing requires the highest-level modules be test and integrated first. This allows high-level logic and data flow to be tested early in the process and it tends to minimize the need for drivers. However, the need for stubs complicates test management and low-level utilities are tested relatively late in the development cycle. Another disadvantage of top-down integration testing is its poor support for early release of limited functionality.
* The bottom-up approach requires the lowest-level units be tested and integrated first. These units are frequently referred to as utility modules. By using this approach, utility modules are tested early in the development process and the need for stubs is minimized. The downside, however, is that the need for drivers complicates test management and high-level logic and data flow are tested late. Like the top-down approach, the bottom-up approach also provides poor support for early release of limited functionality.
* The third approach, sometimes referred to as the umbrella approach, requires testing along functional data and control-flow paths. First, the inputs for functions are integrated in the bottom-up pattern discussed above. The outputs for each function are then integrated in the top-down manner. The primary advantage of this approach is the degree of support for early release of limited functionality. It also helps minimize the need for stubs and drivers. The potential weaknesses of this approach are significant, however, in that it can be less systematic than the other two approaches, leading to the need for more regression testing.

# Unit Testing
* Is the error due to a defect in unit 1?
* Is the error due to a defect in unit 2?
* Is the error due to defects in both units?
* Is the error due to a defect in the interface between the units?
* Is the error due to a defect in the test?


The benefits of automated unit testing
https://www.codeproject.com/articles/5404/the-benefits-of-automated-unit-testing

Better Unit Tests through Design Patterns: Repository, Adapter, Mocks, and more…
http://www.benday.com/wp-content/uploads/2014/08/benday-agile-2014-unit-testing-v2.pdf

# Course

Selenium & Java Training - WeekEnd Batch
http://www.naveenautomationlabs.com/2017/12/selenium-java-training-course-content_29.html

Sample Resume - Automation QA Engineer - 2-7 Years
http://www.naveenautomationlabs.com/2017/12/sample-resume-automation-qa-engineer-2.html

# Test Pyramid
* [1](https://martinfowler.com/bliki/images/testPyramid/test-pyramid.png)
* [1](http://www.360logica.com/blog/wp-content/uploads/2014/07/A-sneak-peek-into-test-framework-test-pyramid-testing-pyramid.png)
* [1](https://abstracta.us/wp-content/uploads/2015/10/Screen-Shot-2017-03-27-at-6.21.09-PM-min-1.png)
* [1](https://abstracta.us/wp-content/uploads/2015/10/Agile-Pyramid-comic.png)

* [Test Pyramid - Martin Flower](https://martinfowler.com/bliki/TestPyramid.html)

# Continuous Testing
1. Continuos Integration (CI) and unit tests
2. Code coverage and static analysis 
3. Continuous Delivery / Automated deployment
4. Integration / E2E / Visual testing
5. Performance testing
6. Security testing (DevSecOps)
7. Exploratory testing
8. Testing in Production (TiP)

# Testing in Production (TiP)
* [Testing in Production](http://www.awesome-testing.com/2016/09/testops-2-testing-in-production.html)



# Podcost
https://joecolantonio.com/testtalks/

# Videos

![1](https://image.slidesharecdn.com/ourmaturitymodelabstracta2-160826194431/95/software-testing-maturity-model-and-assessment-by-abstracta-3-638.jpg?cb=1472240912)
![1](https://image.slidesharecdn.com/ourmaturitymodelabstracta2-160826194431/95/software-testing-maturity-model-and-assessment-by-abstracta-4-638.jpg?cb=1472240912)

![1](https://jfiaffe.files.wordpress.com/2014/09/tests-pyramid.png?w=300&h=180)
![1](http://www.duncannisbet.co.uk/wp-content/uploads/2012/07/test_pyramid-300x218.gif)
![1](http://agilefaqs.com/images/consulting/image08.png)
![1](https://www.researchgate.net/profile/Michael_Bruyneel/publication/263660941/figure/fig1/AS:296386974240773@1447675569499/Figure-1-The-pyramid-of-tests-divided-in-physical-and-virtual-testing-at-each-stage.png)
![1](http://www.duncannisbet.co.uk/wp-content/uploads/2012/07/idealautomatedtestingpyramid-300x244.png)
![1](http://www.duncannisbet.co.uk/wp-content/uploads/2012/07/businesstechnologyautomatedtestingpyramid-300x214.png)
![1](http://www.duncannisbet.co.uk/wp-content/uploads/2012/07/softwaretestingicecreamconeantipattern-243x300.png)
![1](http://fabiopereira.me/blog/wp-content/uploads/2012/03/testing-pyramid-fabio-pereira.png)
![1](https://image.slidesharecdn.com/testpyramid-agilepuneconference-141124063730-conversion-gate02/95/inverting-test-pyramid-a-first-hand-experience-report-27-638.jpg?cb=1416812050)
![1](https://image.slidesharecdn.com/testpyramid-agilepuneconference-141124063730-conversion-gate02/95/inverting-test-pyramid-a-first-hand-experience-report-28-638.jpg?cb=1416812050)
![1](https://image.slidesharecdn.com/testpyramid-agilepuneconference-141124063730-conversion-gate02/95/inverting-test-pyramid-a-first-hand-experience-report-42-638.jpg?cb=1416812050)
![1](https://image.slidesharecdn.com/anandbagmar-behaviordriventestingbdtinagile-120716204509-phpapp01/95/anand-bagmar-behavior-driven-testing-bdt-in-agile-7-728.jpg?cb=1342471601)
![1](https://www.coveros.com/wp-content/uploads/2015/08/test-pyramid.png)
![1](https://pbs.twimg.com/media/Bm_by_ICMAACjkI.png)
![1](https://www.symbio.com/wp-content/uploads/2014/08/agile_pyramid2.jpg)
![1](https://msdnshared.blob.core.windows.net/media/2016/03/image97.png)

![1](http://4.bp.blogspot.com/-UQHE29u7SEw/VT8KCb47gsI/AAAAAAAAAbY/4goJHGgP8ks/s1600/Agile%2BTest%2BQuadrants_2.png)
![1](http://3.bp.blogspot.com/-HN-CbUAAASA/VT8KQwIIIKI/AAAAAAAAAbw/iiqgQv3Ulmg/s1600/Agile%2BTest%2BQuadrants%2B-%2BV%26V.png)
![1](http://1.bp.blogspot.com/-zzSElbkJMCo/VT8KQzsZZyI/AAAAAAAAAbg/I8f-DFqFspk/s1600/Agile%2BTest%2BQuadrants_2_with_Pyramid.png)
![1](http://1.bp.blogspot.com/-_aIqlp3yxj4/VT8KQ0SJdTI/AAAAAAAAAbk/-K932lVzigE/s1600/Agile%2BTest%2BQuadrants_2_with_Pyramid_and_comments.png)


http://adventuresinqa.com/2017/04/24/how-to-get-started-in-software-testing/

* [QA Academy](https://github.com/TelerikAcademy/QA-Academy)
* [What is Testing](https://fasteningcode.com/2016/09/06/what-is-testing-an-overview-day1/)

# QA Basic
* [6 Basic Skills That Every Tester (Mainly Fresher) Should Have](http://www.softwaretestinghelp.com/basic-skills-that-every-tester-fresher-should-have/)
* [Types of Performance Testing](http://www.softwaretestingclub.com/profiles/blogs/types-of-performance-testing)

# Tools
* [Web Site Test Tools and Site Management Tools](http://www.softwareqatest.com/qatweb1.html)
* [Software Testing Tools for Your QA Team](http://sauceio.com/index.php/2016/09/software-testing-tools-for-your-qa-team/?)

# Web App Baisc Testing
* [auditing and performance metrics for Progressive Web Apps](https://github.com/GoogleChrome/lighthouse)
* [Analyze your site performance](https://developers.google.com/speed/pagespeed/)
* [Website Speed Test](https://tools.pingdom.com/)
* [Web Page Analyzer](http://www.websiteoptimization.com/services/analyze/)
* [WebSitePulse](http://www.websitepulse.com/)
* [Test a website's performance](https://www.webpagetest.org/)
* [YSlow](http://yslow.org/)
* [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
* [gtmetrix.com](https://gtmetrix.com/)


# How Functional Testing Works
Functional testing is typically conducted by providing an appropriate input to the function being tested (in line with the typical inputs expected in real-world use cases), and then verifying the result by comparing it to the expected result. This type of testing can answer questions about the capabilities of a software application, such as what actions users are able to perform.

It’s typically approached from one of two perspectives:

* **Requirements-focused testing**, which prioritizes requirements based on risk criteria in order to evaluate the most critical and important features and functions first.
* **Business-process-focused testing**, which relies on knowledge of end-user business requirements to evaluate an application’s performance in the context of typical use cases.

There are several specific functional testing techniques. The two primary techniques include white box testing and black box testing, although there are additional techniques including:

* Smoke testing.
* Unit testing.
* User acceptance testing.
* Integration testing.
* Interface testing.
* System testing.
* Localization testing.
* Regression testing.
* Globalization testing.


# Non-functional Testing
* Security testing.
* Usability testing.
* Operational readiness testing.
* Endurance testing.
* Interoperability testing.
* Maintainability testing.
* Ergonomics testing.
* Availability testing.
* Recoverability testing.
* And others!


# Testing Quadrants
![1](http://istqbexamcertification.com/wp-content/uploads/2014/12/Agile_Testing_Quadrants.jpg)

The four quadrants are described below:

Quadrant Q1 – At unit level contains unit Tests, technology facing, tests subject to full automation and continuous integration.
Quadrant Q2 – At system level, business facing, these are functional tests, examples, story tests, user experience prototypes, and simulations based on the acceptance criteria, be manual or automated. Created as a part of definition of done for a story
Quadrant Q3 – At system or user acceptance level, business facing, contains tests exploratory testing, scenarios, process flows, usability testing, user acceptance testing, alpha testing, and beta testing. These tests are often manual and are user-oriented.
Quadrant Q4 – At system or operational acceptance level, technology facing performance, load, stress, and scalability tests, security tests, maintainability, memory management, compatibility and interoperability, data migration, infrastructure, and recovery testing. These tests are often automated.


# What Are the Differences between Sanity and Regression Testing?
* Sanity Testing is a surface-level testing, meaning that a tester checks whether whole functionality of the software works in a proper way. Regression Testing does not imply a surface-level testing.
* Sanity Testing is a part of Regression Testing.
* Testers carry out Sanity Testing if they have limited time for performing testing. Regression Testing is carried out when there is enough time for it.
* Testers perform Sanity Testing manually. Testers can perform Regression Testing manually or with the help of different automated tools.
* Sanity Testing does not influence the product cost. Since Regression Testing takes much time and efforts, it increases the product cost.
* Non-complete test cases are conducted in the software in the course of Sanity Testing. In the course of Regression Testing complete test cases are conducted in the software.
* Testers should not know many details on the software while performing Sanity Testing. Regression Testing is more extended.
* Script is used for Regression Testing, but for Sanity Testing it is not.

# Test Automation
* [How to start learning test automation](http://awesome-testing.blogspot.com/2016/08/how-to-start-learning-test-automation.html?)
* [QA Automation](https://essenceoftesting.blogspot.com/2016/08/vodqa-pune-less-talk-only-action-agenda.html)
* [Selenium Test Automation: From the ground up](http://www.softwaretestingclub.com/profiles/blogs/selenium-test-automation-from-the-ground-up)


# Appium

#  Exploratory Testing 
https://applause-prodmktg.s3.amazonaws.com/2016/01/11/12/16/34/8ce8b2b4-b2d7-416c-80c9-acc064cc7cea/123.png

* [How to Make Software Better With Exploratory Testing](https://dzone.com/articles/how-to-make-software-better-with-exploratory-testi)


* [The Exploratory Testing Chrome Plugin](https://www.simple-talk.com/dotnet/net-development/exploratory-testing-chrome-plugin/)
* [What is Exploratory Testing](http://www.slideshare.net/QualiTest-Group/what-is-exploratory-testing?next_slideshow=1)
* [Exploratory Automated Testing
](https://www.qualitestgroup.com/documents/articles/Automated_Exploratory_Testing.pdf)
* [8 Steps for Successful Automated Exploratory Testing with Selenium HQ](http://www.itexico.com/blog/bid/97670/8-Steps-for-Successful-Automated-Exploratory-Testing-with-Selenium-HQ)

* [A retrospective critique of an exploratory testing session](http://blog.eviltester.com/2016/11/a-retrospective-critique-of-exploratory.html)


### Tool for Exploratory Testing 
https://github.com/Cognifide/aet




# Visual Regression Testing tool
* [Go to Visual Regression Testing Page](https://github.com/ramyrams/QA/blob/master/VisualRegressionTesting.md)



# Cross-Browser Web App Testing

# Cross-Device Web App Testing

# Exploratory Testing
# Accessibility Testing
# Localization Testing

# Integrating Smoke Tests
* [Integrating Smoke Tests into your Continuous Delivery Pipeline](https://blogs.msdn.microsoft.com/visualstudioalm/2017/04/04/integrating-smoke-tests-into-your-continuous-delivery-pipeline/)

# AB Testing
* [How to implement feature flags and A|B testing](https://blogs.msdn.microsoft.com/visualstudioalmrangers/2017/04/04/how-to-implement-feature-flags-and-ab-testing/)

# Exploratory Testing
* [How to Make Software Better With Exploratory Testing](https://dzone.com/articles/how-to-make-software-better-with-exploratory-testi)


# Free Ethical Hacking Course
* http://techean.com/certified-ethical-hacker-full-course/
* https://www.mediafire.com/folder/vkjc94ocqx386/EC-Council_-_Certified_Ethical_Hacker_%28CEH%29_v9#vkjc94ocqx386



# Web Analytics Automation Testing Framework 
* [Web Analytics Automation Testing Framework](https://essenceoftesting.blogspot.com/2011/04/waat-web-analytics-automation-testing.html)
* [WAAT](https://github.com/anandbagmar/WAAT)
* Web Analytics Automation Testing Framework
https://essenceoftesting.blogspot.sg/2016/07/any-waat-users-out-there.html
https://github.com/anandbagmar/WAAT

https://essenceoftesting.blogspot.com/2011/04/waat-web-analytics-automation-testing.html
https://www.slideshare.net/abagmar/the-what-why-and-how-of-web-analytics-testing-web-iot-big-data
http://mrselenium.blogspot.com/2014/12/automated-analytics-testing-published.html

# REST API Testing
* [REST-Assured framework overview](http://testdetective.com/rest-assured-framework-overview/)
* [REST-Assured: going deeper](http://testdetective.com/rest-assured-going-deeper/)
* [Restful API Testing](https://github.com/stekycz/restful-api-testing)
* [Testing RESTful APIs](https://github.com/chitamoor/Rester)
* [apickli - REST API integration testing framework with cucumber.js](https://github.com/apickli/apickli)
* [Cucumber steps to easily test REST-based XML and JSON APIs](https://github.com/jayzes/cucumber-api-steps)
* [JSON driven test runner for REST APIs](https://github.com/peter/jsonapitest)
* [Behat](https://github.com/deminy/behat-rest-testing)

# BDD through cucumber 



# TFS for Testers


# Database testing


# Performance testing 
* [Performance Testing Guidance for Web Applications](https://msdn.microsoft.com/en-us/library/bb924375.aspx)

# Load Testing

# Headless Testing

# Reponsive Design Testing
* [Galen Framework - Automated testing of look and feel for your responsive websites](http://galenframework.com/)
https://www.sitepoint.com/5-mobile-app-testing-tools/

# Practice Website
* [Damn Vulnerable Web Services](https://github.com/snoopysecurity/dvws) (http://www.dvwa.co.uk/)- Damn Vulnerable Web Services is an insecure web application with multiple vulnerable web service components that can be used to learn real world web service vulnerabilities.

# Testing
* [MOBILE APP OR MOBILE WEB?](http://magenic.com/Blog/Post/172/Mobile-App-or-Mobile-Web)
* [SDLC vs STLC](https://fasteningcode.com/2016/08/03/sdlc-vs-stlc/)
* [Agile, DevOps, and What They Mean for Testers](https://www.stickyminds.com/interview/agile-devops-and-what-they-mean-testers-interview-
jeff-payne)
* [Ideas On How To Succeed As A Tester](https://dojo.ministryoftesting.com/lessons/ideas-on-how-to-succeed-as-a-tester)
* [How to come up with test ideas](http://erik.brickarp.se/2016/08/how-to-come-up-with-test-ideas.html)

http://www.altencalsoftlabs.com/blogs/2016/05/12/mobile-application-security-testing-importance-and-how-it-works/
 
 https://dzone.com/articles/load-testing-and-stress-testing
 https://dzone.com/articles/the-software-tester-modern-vs-traditional
 http://angiejones.tech/test-automation-for-machine-learning/?
 http://www.getzephyr.com/insights/benefits-automated-test-management
 
 How to Plan an Effective Test Automation in Agile Project
https://dzone.com/articles/how-to-plan-an-effective-test-automation-in-agile

http://blogs.agilefaqs.com/2011/02/01/inverting-the-testing-pyramid/


http://istqbexamcertification.com/what-is-definition-of-done-test-levels-in-agile-software/
http://istqbexamcertification.com/what-are-testing-techniques-in-agile-development/
http://istqbexamcertification.com/difference-between-regression-testing-and-retesting/
http://istqbexamcertification.com/mobile-application-development-and-testing-checklist/
http://istqbexamcertification.com/what-is-release-and-iteration-planning-in-agile-methodology/
http://istqbexamcertification.com/what-is-continuous-integration-in-agile-methodology/
http://istqbexamcertification.com/what-are-test-levels-in-agile-methodology/
http://istqbexamcertification.com/what-is-testing-and-configuration-management-in-agile-development/
http://istqbexamcertification.com/communicating-test-status-progress-and-product-quality-in-agile-methodology/
http://istqbexamcertification.com/what-is-the-role-of-a-tester-in-agile-methodology/
http://istqbexamcertification.com/what-is-planning-poker-effort-estimation-in-agile-methodology/
http://istqbexamcertification.com/what-are-testing-techniques-in-agile-development/
http://istqbexamcertification.com/what-is-exploratory-testing-in-agile-methodology/
http://istqbexamcertification.com/what-are-the-tools-in-agile-projects/
http://istqbexamcertification.com/what-are-build-and-distribution-tools-in-agile-software-testing/

# Allure
* [Allure GitHub](https://github.com/allure-framework/allure1)
* [Sample Allure Report](http://ci.qatools.ru/job/allure1_master-deploy/Allure_report/)
https://github.com/allure-framework/
# Images
![1](http://3.bp.blogspot.com/-rRnawvE1ncM/WSPPs6aS3WI/AAAAAAAAHTM/90jjt7TkX4ErXFNrhrVHQOe5N4NHjGTEwCK4B/s1600/testearly.png)

![1](http://www.zarantech.com/blog/wp-content/uploads/2017/05/Cost-to-fix-a-bug-in-software-development.png)
![Tool](https://www.perfectomobile.com/sites/default/files/images/diagrams/automation-tools-comparison-lrg_0.png)
![The Use of Tradition and Dogma in Testing](http://testerstories.com/files/combine-triangle-with-quadrant.png)
![1](http://moolya.com/wp-content/uploads/2016/02/Upgrade-version_Mobile-App-Test-Model_1.png)
![2](http://moolya.com/wp-content/uploads/2015/12/Mobile-app-testing.png)
![3](http://moolya.com/wp-content/uploads/2015/12/Tested-by-Moolya.png)
![4](http://moolya.com/wp-content/uploads/2015/12/Tested-by-Moolya_2.png)
![51](https://cloud.githubusercontent.com/assets/659851/18248163/191e6a2e-734d-11e6-979e-d7f9e9ccebce.png)
![](http://www.ministryoftesting.com/wp-content/uploads/2016/06/30-Day-Challenge.png)
![](http://i1.wp.com/adventuresinqa.com/wp-content/uploads/2016/09/30_days_of_mobile_testing-Adventures-in-QA.png)
