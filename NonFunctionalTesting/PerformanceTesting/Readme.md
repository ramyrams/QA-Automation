

Performance testing is a type of testing intended to determine the responsiveness, throughput, reliability, and/or scalability of a system under a given workload. 

Performance testing is commonly conducted to accomplish the following:
* Assess production readiness
* Evaluate against performance criteria
* Compare performance characteristics of multiple systems or system configurations
* Find the source of performance problems
* Support system tuning
* Find throughput levels

Performance testing is typically done to help identify bottlenecks in a system, establish a baseline for future testing, support a performance tuning effort, determine compliance with performance goals and requirements, and/or collect other performance-related data to help stakeholders make informed decisions related to the overall quality of the application being tested. In addition, the results from performance testing and analysis can help you to estimate the hardware configuration required to support the application(s) when you “go live” to production operation.

# Core Activities of Performance Testing
https://docs.microsoft.com/en-us/previous-versions/msp-n-p/images/bb924375.image001%28en-us%2cpandp.10%29.gif

The performance testing approach used in this guide consists of the following activities:

* Activity 1. Identify the Test Environment. Identify the physical test environment and the production environment as well as the tools and resources available to the test team. The physical environment includes hardware, software, and network configurations. Having a thorough understanding of the entire test environment at the outset enables more efficient test design and planning and helps you identify testing challenges early in the project. In some situations, this process must be revisited periodically throughout the project’s life cycle.
* Activity 2. Identify Performance Acceptance Criteria. Identify the response time, throughput, and resource utilization goals and constraints. In general, response time is a user concern, throughput is a business concern, and resource utilization is a system concern. Additionally, identify project success criteria that may not be captured by those goals and constraints; for example, using performance tests to evaluate what combination of configuration settings will result in the most desirable performance characteristics.
* Activity 3. Plan and Design Tests. Identify key scenarios, determine variability among representative users and how to simulate that variability, define test data, and establish metrics to be collected. Consolidate this information into one or more models of system usage to be implemented, executed, and analyzed.
* Activity 4. Configure the Test Environment. Prepare the test environment, tools, and resources necessary to execute each strategy as features and components become available for test. Ensure that the test environment is instrumented for resource monitoring as necessary.
* Activity 5. Implement the Test Design. Develop the performance tests in accordance with the test design.
* Activity 6. Execute the Test. Run and monitor your tests. Validate the tests, test data, and results collection. Execute validated tests for analysis while monitoring the test and the test environment.
* Activity 7. Analyze Results, Report, and Retest. Consolidate and share results data. Analyze the data both individually and as a cross-functional team. Reprioritize the remaining tests and re-execute them as needed. When all of the metric values are within accepted limits, none of the set thresholds have been violated, and all of the desired information has been collected, you have finished testing that particular scenario on that particular configuration.


# Why Do Performance Testing?
At the highest level, performance testing is almost always conducted to address one or more risks related to expense, opportunity costs, continuity, and/or corporate reputation. Some more specific reasons for conducting performance testing include:

## Assessing release readiness by:
* Enabling you to predict or estimate the performance characteristics of an application in production and evaluate whether or not to address performance concerns based on those predictions. These predictions are also valuable to the stakeholders who make decisions about whether an application is ready for release or capable of handling future growth, or whether it requires a performance improvement/hardware upgrade prior to release.
* Providing data indicating the likelihood of user dissatisfaction with the performance characteristics of the system.
* Providing data to aid in the prediction of revenue losses or damaged brand credibility due to scalability or stability issues, or due to users being dissatisfied with application response time.

## Assessing infrastructure adequacy by:
* Evaluating the adequacy of current capacity.
* Determining the acceptability of stability.
* Determining the capacity of the application’s infrastructure, as well as determining the future resources required to deliver acceptable application performance.
* Comparing different system configurations to determine which works best for both the application and the business.
* Verifying that the application exhibits the desired performance characteristics, within budgeted resource utilization constraints.

## Assessing adequacy of developed software performance by:
* Determining the application’s desired performance characteristics before and after changes to the software.
* Providing comparisons between the application’s current and desired performance characteristics.

## Improving the efficiency of performance tuning by:
* Analyzing the behavior of the application at various load levels.
* Identifying bottlenecks in the application.
* Providing information related to the speed, scalability, and stability of a product prior to production release, thus enabling you to make informed decisions about whether and when to tune the system.


# Modeling Performance Tests
https://docs.microsoft.com/en-us/previous-versions/msp-n-p/bb924367(v=pandp.10)
https://www.neotys.com/blog/modeling-performance-tests/
https://techbeacon.com/how-define-right-workload-model-your-performance-tests
https://dzone.com/articles/modeling-performance-tests
http://www.agileload.com/agileload/blog/2013/06/12/performance-test-workload-modeling
https://smartbear.com/blog/test-and-monitor/workload-modeling-and-profiles-for-load-testing/
https://www.cs.auckland.ac.nz/~christof/publications/LutterothWeber2008-LoadTesting.pdf

![1](https://qph.fs.quoracdn.net/main-qimg-7d320fdbfe44f5ef1c1b7ef974bdc988.webp)

Considerations while designing Workload Model :

* Some users will complete more than one activity during a visit to your site.
* Some users will complete the same activity more than once per visit.
* Some users may not actually complete any activities during a visit to your site.
* Navigation paths are often easiest to capture by using page titles.
* If page titles do not work or are not intuitive for your application, the navigation path may be easily defined by steps the user takes to complete the activity.
* First-time users frequently follow a different path to accomplish a task than users experienced with the application. Consider this difference and what percentage of new versus return user navigation paths you should represent in your model.
* Different users will spend different amounts of time on the site. Some will log out, some will close their browser, and others will leave their session to time out. Take these factors into account when determining or estimating session durations.
* When discussing navigation paths with your team or others, it is frequently valuable to use visual representations.


# Statergy

1. Determine the Scope of Testing/Nonfunctional Requirements: This includes basic check on what all requirements are agreed upon under what deadlines, Resources,Identified performance targets, tools, skills, and appropriate licenses for the performance test(if required). Adequate training for all team members in the tools to be used.
 
 2. Performance Test Environment Build: Take into account the load models(server monitoring/load test) and deploying,configuring performance testing tools correctly so that build/env is ready to work since we strive to make test environment as close as that of production Test Page for the Apache HTTP Server & InterWorx-CP also involves identifying acceptance criteria.
 
 3. Scripting/Use-Case Scripting: Now once above 2 things are handles,here comes in major approach/line item to be followed i.e scripting of all the business scenarios,for which following steps will be required:
 a. Identifying the sessions data requirement and then Confirm and apply input data.
 b. Checkpoint coverage at appropriate places which provides first-level analysis of potential problem areas within the use case.
 c. Identify the changes required and apply them in use cases so as to get correct results/output.[Note: Use cases should work correctly in both cases whether for Single or Multi-user ]
 
 4. Performance Test Scenario Build: It includes making use of the load model created which was captured as part of NFR/scope defining approach.Focus is on below areas:
 a. Type of test to be run: Whether pipe-clean, Spike,Volume,Soak, or Stress? Mostly, we use pipe-clean tests for each use case initially as a single user to establish a performance baseline, and then target throughput for the use case.
 b. For each use case, decision on how many load injector deployments are required and virtual users to be assigned to each point of presence
 c. Put required think time and pacing as business flow demands
 
 5. Performance Test Execution and Analysis: Last and the important approach is to Run and monitor test results. Final check/dress rehearsals are performed so that there are no problems accessing the application or with the test configuration.
 a. Ensuring that we haven’t omitted anything fundamental in performance test configuration.
 b. Execute volume tests once performance baselines are established.
 c. Execute isolation tests to explore any problems revealed by volume testing and stress tests, which are crucial from a capacity perspective.
 
 6. Post-Test Analysis and Reporting: Final and important step is after running/executing ,make sure to have clean and precise analysis of the task and the best way is to prepare the reports after each run performed and a closure report for same.
 a. Determine success or failure by comparing test results to performance targets set as part of project requirements.
 b. Document the results using your preferred reporting template
 c. A closure report containing Key business scenario,Scopes,Bottlenecks Identified(database configuration, coding errors, hardware issues etc) and vulnerable areas being identified shall prove good.
 A conclusion with recommendation ideas is always treated good & interactive way to Report.
 
 
 At a minimum, a performance testing plan needs to address the following:

Overall approach
Focus on mitigating the performance risks for this new implementation.
Make basic working assumptions on which parts of the implementation need to be performance-tested.
Reach consensus on these working assumptions and determine the appropriate level of performance and stress testing that shall be completed within this compressed time schedule.
Dependencies and baseline assumptions
Components to be performance tested shall be completely functional.
Components to be performance tested shall be housed in hardware/firmware components that are representative or scaleable to the intended production systems.
Data repositories shall be representative or scaleable to the intended production systems.
Performance objectives shall be agreed upon, including working assumptions and testing scenarios.
Performance testing tools and supporting technologies shall be installed and fully licensed.
Pre-performance testing actions
Create a "stubs" or "utilities" to push transactions through the QA environment -– using projected peak loads.
Create a "stubs" or "utilities" to replace business-to-business transactions that are not going to be tested or will undergo limited performance. This would remove any dependencies on B2B transactions.
Create a "stubs" or "utilities" to replace internal components that will not be available during performance testing. This would remove any dependencies on these components.
Implement appropriate performance monitors on all high-volume servers.
Performance testing approach
Focus on mitigating the performance risks for this new implementation.
Make basic working assumptions on which parts of the implementation need to be performance-tested.
Reach consensus on these working assumptions and determine the appropriate level of performance that shall be completed.
Use a tier 1 performance testing tool that can replicate the expected production volumes.
Use an environment that replicates the components (as they will exist in production) that will be performance-tested -– noting all exceptions.
Use both production and non-production (testing) monitors to measure the performance of the system during performance testing.
Performance testing activities
Performance test shall create appropriate loads against the system following agreed-upon scenarios that include:User actions (workflow)Agreed-upon loads (transactions per minute)Agreed-upon metrics (response times)
Manual testing and automated functional tests shall be conducted during performance testing to ensure that user activities are not impacted by the current load.
System monitors shall be used to observe the performance of all servers involved in the test to ensure they meet predefined performance requirements.
Post-implementation support teams shall be represented during performance testing to observe and support the performance testing efforts.
In-scope business processes
Out-of-scope business processes
Performance testing scenarios
Business scenario
Expected throughput (peak)
Acceptance performance criteria (acceptable response times under various loads)
Data requirements (scenario and implementation specific)
Performance test execution
Performance test metrics
In-short a good approach organises "CCD IS EARI" into a flow that fits your project

Context - the overall vision or intent of the project, performance testing objectives, performance success criteria, the development life cycle, the project schedule, the project budget, the available tools and environments, the skill set of the performance tester and the team, the priority of detected performance concerns, and the business impact of deploying an application that performs poorly

Criteria - criteria include requirements, goals, targets, thresholds and objectives related to both the application's performance and the performance testing sub-project

Design - A significant component of performance test design is determining, designing and creating data associated with the natural variances of application users

Install - This heuristic is actually short for "Install and Configure or Update Tools and the Load Generation Environment

Script - It is most likely that your test design will be implemented using a load generation tool that requires some degree of scripting.

Execute - The fact is that test execution involves continually validating the tests and test environment, running new tests and archiving all of the data associated with test execution.

Analyse - Analysing test results and collected data, whether to determine requirement compliance, track trends, detect bottlenecks or evaluate the effectiveness of tuning efforts, is crucial to the success of a performance testing project

Report - Reporting on the results and analysis is just as significant as the collection and analysis of the data

Iterate - Iterating is virtually a given for any type of testing. Sometimes we iterate based on builds, defect resolutions or environment changes.


# Performance Testing Strategy
https://www.360logica.com/blog/mobile-app-performance-testing-strategy/


Cloud Performance Testing: How to Build an Effective Strategy?

http://bento.cdn.pbs.org/hostedbento-qa/filer_public/smoke/load_testing.pdf


Technical Skills of a Performance Test Engineer
https://dzone.com/articles/technical-skills-of-performance-test-engineer

# Load Testing Strategy
1. Baseline Profile
2. Peak Profile
3. Stress Profile
4. Soak Profile
https://www.soapui.org/learn/load-testing/load-testing-strategies-apis.html


API Load Testing
Mobile Load Testing
Web Load Testing

http://www.performance-workshop.org/documents/Perf_Testing_Strategy_Collard.pdf

http://www.perftestplus.com/resources/Performance_Engineering_Strategy_Template.pdf



https://www.akamai.com/us/en/multimedia/documents/white-paper/the-complete-guide-to-performance-testing-your-retail-websites-and-apps.pdf

https://smartbear.com/blog/test-and-monitor/7-types-of-web-performance-tests-and-how-they-fit/

Measuring Performance With Gatling
https://dzone.com/articles/let-measure-performance-with-gatling


![1](https://dzone.com/storage/temp/10719722-types-of-performance-testing.png)

Top 10 Open Source Performance Testing Tools
https://www.testingexcellence.com/top-10-open-source-performance-testing-tools/

https://docs.microsoft.com/en-us/vsts/test/load-test/overview?view=vsts

Performance Testing Guidance for Web Applications
https://docs.microsoft.com/en-us/previous-versions/msp-n-p/bb924375(v=pandp.10)


https://dzone.com/articles/jmeter-how-to-distribute-user-load-in-the-test-pla




https://www.techwell.com/techwell-insights/2018/11/new-approach-load-testing-browser-level-users


http://www.guidanceshare.com/wiki/Chapter_3_%E2%80%93_Risks_Addressed_Through_Performance_Testing

https://www.safaribooksonline.com/library/view/performance-testing-guidance/9780735625709/ch03s04.html

(Must Read)[https://www.slideshare.net/jvenet/performance-testing-overview-75018229]
https://www.slideshare.net/SpringCentral/performance-testing-crashcourse
https://www.slideshare.net/atulpant20/jmeter-performance-testing


* 57% of users will abandon a site after 3 seconds if it doesn’t load -Kissmetrics
* The average large US corporation experiences 87 hours of network downtime a year -Gartner



According to Microsoft, the Core Performance Testing Activities are:

1. **Identify Test Environment** – where it is important to have the exact replica of the production environment
2. **Identify Performance Acceptance Criteria** – predefine the benchmarks of expected performance
3. **Plan and Design Tests** – Identification of user test scenarios based on their importance, frequency and performance impact
4. **Configure Test Environment** – setting up the test environment as in the first step
5. **Implement Test Design** – scripting user scenarios with the help of performance testing tools
6. **Execute Tests** – testing on scripted user scenarios against different user sets with different configurations
7. **Analyze, Report and Retest** – Analyze test results with benchmarks, report results to stakeholders and Re-test if necessary


# PERFORMANCE TESTING PROCESS
* COLLECT
  * Assess Business Requirements
  * Review Application Features
  * Identify Key Elements to Setup Test Environment
* PLAN & STRATEGIZE
  * Identify Performance Test Matrices
  * Define Baseline Values
  * Define Timing, Tools & Types of Performance tests
  * Creation of Test Plans
* DEFINE & DESIGN
  * Creation of Test Scenarios
  * Define Test Data
  * Configure Testing Environment
* EXECUTE
  * Execute Test Scenarios
  * Validate Results
  * Record Outcomes
* DELIVER
  * Analyze Results
  * Make Recommendations
  
  
# Services Offered

Our offers load/stress testing services to identify below:
* Identify Performance leaks in the application by doing a performance testing on the applications
* Identify Key areas where performance need to be improved

Our Load Testing model has 3 stages as described below

# Stage 1 – Test Planning Phase

The following activities will be carried out as part of the Test Planning phase:
* Identify performance goals and objectives
* Identify the SLA’s for performance testing
* Define phases for performance testing
* Define Infrastructure
* Identify Load Models
* Identify Volumetrics (Load Mix)
* Identify project support requirements
* Determine the Acceptable test Conditions
* Identify Performance Metrics
* Identify Risks
* Create Performance Test Plan
 

# Stage 2 – Test Preparation Phase
The following activities will be carried out as part of the Test Preparation phase:

* Design Test Data Strategy
* Identify requirements for test data
* Identify Tools for Test data
* Test Environment Setup
* Test environment readiness check [Application deployment and configuration on the dedicated performance test environment ]
* Test Data preparation & pre-requisites validation check
* Test artifacts creation (automated test scripts preparation)
* Dry tests / Validation tests will be carried out for go-ahead on actual tests
 

# Stage 3 – Test Execution and Reporting Phase
The following activities will be carried out as part of the Test Preparation phase:
* Create Performance Test Scenarios
* Execute Environment shakeout
* Execute Baseline/Benchmark tests
* Execute the performance tests
* Analyze test results
* Create Performance test execution report
* Create Performance Test summary repor twith possible recommendations for performance optimization


![1](http://www.abstracta.us/wp-content/uploads/2015/03/why-perf-testing-is-nec-chart-768x463.png)

An Explanation of the Different Types of Performance Testing 
https://dzone.com/articles/performance-testing-vs-load-testing-vs-stress-test

JMeter Ramp-Up: The Ultimate Guide
https://dzone.com/articles/jmeter-ramp-up-the-ultimate-guide


* [What Is Performance Testing? An Explanation for Business People](https://dzone.com/articles/what-is-performance-testing-an-explanation-for-bus)

# Key Performance Indicators (KPIs)
https://www.nd.gov/itd/services/performance-testing


LoadView Hands-on Review Tutorial: Load Testing from the Cloud
http://www.softwaretestinghelp.com/loadview-tutorial/?


https://abstracta.us/tools/introduction-to-taurus-an-alternative-to-jmeter/
https://www.blazemeter.com/blog/taurus-new-star-test-automation-tools-constellation
https://www.theseus.fi/bitstream/handle/10024/118673/Web%20Application%20Performance%20Requirements%20Deriving%20Methodology.pdf?sequence=1
https://www.slideshare.net/ATASlides/continuous-performance-testing-with-taurus-and-jmeter
http://zenq.com/Portals/0/PerformanceTestingWhitePaperrevisedV1.1.pdf


https://abstracta.us/2017/03/24/how-to-make-a-performance-test-plan/
https://abstracta.us/2015/10/12/why-performance-testing-is-necessary/
https://abstracta.us/2017/02/24/best-time-start-performance-testing/
https://abstracta.us/2016/10/17/shutterfly-continuous-performance-testing/
https://abstracta.us/2015/09/14/performance-testing-in-production/
https://abstracta.us/2015/07/30/top-10-factors-that-impact-application-performance/
https://abstracta.us/2015/03/30/free-tools-to-process-logs-for-performance-analysis/
https://abstracta.us/2015/03/30/types-of-performance-tests/
https://abstracta.us/2015/03/30/system-performance-problems/

http://www.abstracta.us/2017/03/16/how-to-make-performance-test-plan/
http://www.abstracta.us/2017/02/24/best-time-start-performance-testing/
http://www.abstracta.us/2017/01/06/gatling-vs-jmeter-findings/
http://www.abstracta.us/2016/10/17/shutterfly-continuous-performance-testing/
http://www.abstracta.us/2016/03/09/why-should-i-become-performance-tester/
http://www.abstracta.us/2016/02/19/jmeter-response-assertions-how/
http://www.abstracta.us/2015/10/12/why-performance-testing-is-necessary/
http://www.abstracta.us/2015/09/14/performance-testing-in-production/
http://www.abstracta.us/2015/09/14/performance-testing-in-production/
http://www.abstracta.us/2016/03/07/checklist-8-ways-to-improve-jmeter-scripts/
http://www.abstracta.us/2015/08/10/software-performance-testing-fallacies-part-1/
http://www.abstracta.us/2015/08/17/software-performance-testing-fallacies-part-2/
http://www.abstracta.us/2015/03/30/free-tools-to-process-logs-for-performance-analysis/
http://www.abstracta.us/2015/05/24/whats-more-important-the-tool-or-the-tester/
http://www.abstracta.us/2015/03/30/types-of-performance-tests/
http://www.abstracta.us/2015/05/18/how-importantnecessary-is-it-for-performance-testers-to-understand-the-architecture-of-systems-and-the-details-on-each-component/

![1](http://fbrnc.net/images/1/2/4/1/6/124165079b019ed1a96340a4e82a9522fe0cfb3e-01cloudwatch.png)
