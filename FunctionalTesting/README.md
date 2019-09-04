
Types of Functional testing are
* Unit Testing
* Smoke Testing
* Sanity Testing
* Integration Testing
* White box testing
* Black Box testing
* User Acceptance testing
* Regression Testing
* User Acceptance Testing
* Localization Testing
* Interface Testing
* Usability Testing
* System Testing
* Globalization Testing

![1](https://www.tutorialspoint.com/software_testing_dictionary/images/functional_testing.jpg)


* Functional
* Non-functional
* Change related testing


After making the necessary changes, such as fixing the bug / defect, the software must be re-tested to confirm the fact that the problem was actually solved. The following are the types of testing that need to be done after installing the software to confirm the application’s performance or correct rectification of defects:

* Smoke Testing
* Regression Testing
* Build Verification Test
* Sanity Testing


# Smoke Testing
![1](https://newline.tech/wp-content/uploads/2018/03/Illustration_for_nlt_blog_smoked_test_pass.jpg)

* The concept of smoke testing came from the engineering environment:
* “When the commissioning of the new equipment (” hardware “), it was considered that the test is successful, if there is no smoke from the plant.”
* In the area of software, smoke testing is viewed as a short cycle of tests performed to confirm that, after the code is assembled (new or revised), the installed application starts and performs basic functions.
* The conclusion about the operability of the main functions is made on the basis of the surface testing results of the most important modules of the application for the ability to perform the required tasks and the presence of rapidly occurring critical and blocking defects. In the absence of such defects, smoke testing is declared passed, and the application is sent for a full test cycle, otherwise, smoke testing is declared failed, and the application is retired.
* The analogs of Smoke Testing are Build Verification Testing and Acceptance Testing performed at the functional level by the testing team, which results in the conclusion whether or not the installed version of the software is accepted for testing, operation or delivery to the customer.
* To facilitate the work, save time and human resources, it is recommended to implement the automation of test scenarios for smoke testing.

# Regression Testing
![1](https://newline.tech/wp-content/uploads/2018/03/Illustration_for_nlt_blog_testing_analisis.jpg)

Regression testing is a type of testing aimed at checking changes made in an application or the environment (fixing a defect, merging code, migrating to another operating system, database, web server or application server) to confirm the fact that the existing functionality is working as before. Regression can be both functional and non-functional tests.

Typically, test cases written in the early stages of development and testing are used for regression testing. This gives a guarantee that changes in the new version of the application did not damage the already existing functionality. It is recommended to automate regression tests to speed up the subsequent testing process and detect defects in the early stages of software development.

Software Testing Education & Research, described 3 basic types of regression testing:
* Bug regression – an attempt to prove that the corrected error is not actually corrected
* Old bugs regression – an attempt to prove that a recent change in code or data broke the correction of old bugs, i.e. old bugs began to be reproduced again.
* Side effect regression is an attempt to prove that a recent change in code or data has broken other parts of the application being developed

# Build Verification Test
![1](https://newline.tech/wp-content/uploads/2018/03/Illustration_for_nlt_blog_Thorough.jpg)

Testing aimed at determining the compliance of the released version with the quality criteria for the start of testing. For its purposes is the analogue of Smoke Testing, aimed at accepting a new version for further testing or operation. In depth, it can penetrate further, depending on the requirements for the quality of the released version.


Sanity Testing
Sanitary testing is a narrowly targeted test sufficient to prove that a particular function works according to the requirements stated in the specification. It is a subset of regression testing. It is used to determine the operability of a certain part of the application after changes made in it or the environment. It is usually done manually.


# Sanity vs Smoke testing
![1](https://newline.tech/wp-content/uploads/2018/03/Illustration_for_nlt_blog_regression_testing.jpg)

Some sources mistakenly believe that Sanitary and Smoke testing is the same thing. We believe that these types of testing have “motion vectors” with different directions. Unlike Smoke testing, Sanity testing is directed deep into the function being tested, while smoke is directed in breadth, to cover the tests with as much functionality as possible in the shortest possible time.
