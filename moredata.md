

CRITICAL PATH TEST - https://newline.tech/blog/critical-path-test/
https://newline.tech/wp-content/uploads/2018/07/Illustration_for_nlt_blog_test_process.jpg

https://newline.tech/blog/practical-application-of-test-design-techniques-when-developing-test-cases/

https://newline.tech/blog/test-design-techniques/


https://newline.tech/blog/test-design-test-coverage/


Types of Test Cases
Test cases are divided according to the expected result into positive and negative ones:

A positive test case uses only the correct data and verifies that the application has correctly performed the called function.
A negative test case operates both correct and incorrect data (at least 1 incorrect parameter) and aims to check for exceptional situations (activation of validators), and also checks that the function called by the application is not executed when the validator is triggered.



Test Case Structure
On the Internet, you can find a lot of information about the structure of the test cases, the level of their details and the number of checks in them, I’m going to talk about the approach I use, and I want to suggest using it to you.

Each test case must have 3 parts:


https://newline.tech/wp-content/uploads/2018/06/Illustration_for_nlt_blog_Test-artifacts_cases_suits_2.jpg

Note: Post Conditions is optional. This is most likely a rule of good form: “messed up – clean up”. This is especially true for automated testing, when in one run you can fill a database with hundreds or even thousands of incorrect documents.

Case study example:

do A1, verify B1

do A2, verify B2

do A3, verify B3

In this example, the final test is B3. This means that it is the key one. Hence, A1 and A2 are actions leading the system into a testable state. A B1 and B2 – the conditions that the system is in a condition suitable for testing. Thus we have:


https://newline.tech/wp-content/uploads/2018/06/Illustration_for_nlt_blog_Test-artifacts_cases_suits_4.jpg


PostConditions in this example were not described, but according to the logic of things, you need to perform steps that would return the system to its original state. (for example, delete the created record, or cancel the changes made in the document)

Now we answer the question: “Why is this partition convenient to use?”

Answer: the final check is one, i.е. In case the test fails, it will be immediately c
There are many different opinions about the level of detail when writing test cases, as well as the number of checks in one test case. All of them are correct in their own way. My opinion is that the level of detail of the test cases should be such as to ensure a reasonable ratio of the passage time to the test coverage. Those. As long as the coverage of tests of certain functional does not change, you can reduce the detail of the test case.
https://newline.tech/wp-content/uploads/2018/06/Illustration_for_nlt_blog_Test-artifacts_cases_suits_1.jpg


# INSTALLATION TESTING
https://newline.tech/wp-content/uploads/2018/03/Illustration_for_nlt_blog_Installation_testing.jpg
https://newline.tech/blog/installation-testing/

# Relation of design and testing processes
https://newline.tech/wp-content/uploads/2018/04/Illustration_for_nlt_blog_proecting_test.jpg
