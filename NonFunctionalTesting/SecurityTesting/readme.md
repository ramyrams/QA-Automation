


Some tools include:

* **BDD Security.** A security testing automation framework. This uses a natural language syntax to describe security functions as features.
* **Microsoft Azure Advisor.** A configuration scanner that will identify whether cloud infrastructure tools are using the right software best practices.
* **Mittn.** An open source test automation framework, which is ideal for those accustomed to Python.
* **GauntIT.** A test automation framework, which is ideal for those accustomed to Ruby development.
* **Burp Intruder.** A commercial application and infrastructure scanner, which can be used to ensure applications are interacting properly with the environment.
* **OWASP Scanner.** An open source application and infrastructure scanner, similar to Burp Intruder.
* **Veracode.** Veracode is a Code Analysis tool that can be used to find vulnerabilities within your application structure.
Contrast Security. A runtime application security tool, Contrast Security will run inside of your application to identify any potential faults.


Security Testing Test Scenarios - By Naveen AutomationLabs
http://www.naveenautomationlabs.com/2018/01/security-testing-test-scenarios-by.html


13 Steps to Learn & Perfect Security Testing in your Org
https://www.atlassian.com/blog/archives/13-steps-to-learn-perfect-security-testing-in-your-org


https://blog.box.com/blog/a-baseline-approach-to-security-testing/

# Web Application Security
* [WEB APPLICATION SECURITY TESTS](http://www.amanhardikar.com/mindmaps/webapptest.html)
* [Four Things You Shouldn't Forget About Web Application Security](http://www.ehacking.net/2016/05/4-things-not-to-forget-web-application-security.html)
* [Web Application Security Testing Cheat Sheet](https://www.owasp.org/index.php/Web_Application_Security_Testing_Cheat_Sheet)
* [APPROACHES, TOOLS AND TECHNIQUES FOR SECURITY TESTING](http://www.3pillarglobal.com/insights/approaches-tools-techniques-for-security-testing)
* [OWASP TESTING GUIDE](https://www.owasp.org/images/5/56/OWASP_Testing_Guide_v3.pdf)

# Penetration Testing
* [Penetration Testing Framework 0.59](http://www.vulnerabilityassessment.co.uk/Penetration%20Test.html)
* [Automated Security Testing in a Continuous Delivery Pipeline](http://devops.com/2015/04/06/automated-security-testing-continuous-delivery-pipeline/)
* [Network Security Auditing Tools and Techniques](http://www.ciscopress.com/articles/article.asp?p=1606900&seqNum=4)
* [PENETRATION TESTING PRACTICE LAB](https://www.amanhardikar.com/mindmaps/Practice.html)
* 
# Web Application Penetration Testing
* [Getting Started with Web Application Penetration Testing](http://www.softwaretestinghelp.com/getting-started-with-web-application-penetration-testing/)

http://resources.infosecinstitute.com/penetration-testing-benefits/#gref

# Security Test Automation

The processes would be slightly varied from the original TDD process
* Perform a Static Security Scan on the code written
* Add a Test
* Run all tests and trigger Dynamic Security scan in the background
* See if the new one fails
* See if any security flaw identified on the newly developed code
* Write some code as per the security guidelines without affecting functional behavior
* Run tests and Refactor code
* Repeat

# Advantages of STDD over TDD
Along with the TDD advantages we would have some additional advantages using STDD process
* Much less debug time
* Code proven to meet requirements
* Tests become Safety Net
* Near zero defects
* Shorter development cycles
* Faster security certifications for the application
* Reduced Security Flaws


# Security Test Automation Tools 

Security Testing Tools

## SAST (Static Analysis)

As specified earlier we could use tools like Lint (Android), SonarCube (Java), Clang Static Analyzer (iOS) and Brakeman (Ruby).

## DAST (Dynamic Analysis)

Dynamic analysis needed to be run in background of your tests execution in the TDD process, which means we need a proxy enabled security tool which could be acting as a listener.

We could think about tools like OWASP ZAP/BURP which could do the monitoring as well enables their user to attack the application on the local development environment.

![1](https://media.licdn.com/mpr/mpr/AAEAAQAAAAAAAAeDAAAAJGRmYmFkNGUxLWQwZjktNGViNS1hYThmLTNlZTY3ZDFlNzNmMw.png)
![1](https://media.licdn.com/mpr/mpr/AAEAAQAAAAAAAAdEAAAAJDYzNzI4NjJhLTJlYmQtNDM1Mi04NjM2LTgxMjkyZmY2OTEwOA.png)
![1](https://media.licdn.com/mpr/mpr/AAEAAQAAAAAAAAlhAAAAJGUxOTIzYmJiLTMyOWQtNDQyNi1iNWFlLTk4MTMzZjA3ODZkNg.png)

https://www.techworm.net/2016/08/top-10-websites-refresh-hacking-skills.html

[Notes From](https://www.linkedin.com/pulse/security-test-driven-development-stdd-surendran-ethiraj)

